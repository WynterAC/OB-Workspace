```dataviewjs
let pageCurr            = dv.current( );
let file                = app.workspace.getActiveFile( );
let i_total             = 0;
const minRequired       = 0;
const link_filter       = ( a ) => a.toUpperCase( ).replace( /[\s/\\]+/, '' )
const categories        = { 'Full Mode': 'mode-full', 'Compact Mode': 'mode-compact' }

dv.container.className += ' atx-blv1-dataview'

/*
    elements
*/

const divRoot       = dv.el( 'div', '', { container: dv.container, cls: 'atx-blv1-bg' } );
const divSub        = dv.el( 'div', '', { container: divRoot, cls: 'atx-blv1-root' } );
const divHdr        = dv.el( 'div', '', { cls: 'atx-blv1-header', container: divSub } );
const divHdrL       = dv.el( 'div', '', { cls: 'atx-blv1-header-left', container: divHdr } );
const divHdrR       = dv.el( 'div', '', { cls: 'atx-blv1-header-right', container: divHdr } );
const divClear      = dv.el( 'div', '', { cls: 'atx-blv1-ct-clear', container: divHdr } );
const cboModes      = dv.el( 'select', '', { container: divHdrR } );
const hdrTitle      = dv.header( 2, 'Unresolved Links', { container: divHdrL } );
const divBody       = dv.el( 'div', '', { container: divSub, cls: 'atx-blv1-body' } );

/*
    populate select box
*/

for ( const key of Object.keys( categories ) )
{
    const option = dv.el( 'option', key, { container: cboModes } )
    cboModes.appendChild( option )
}

/*
    func > set select box value
*/

async function CboSetValue( obj, set )
{
    for ( var i = 0; i < obj.options.length; i++ )
    {
        if ( obj.options[ i ].text == set )
        {
            obj.options[ i ].selected = true;
            return;
        }
    }
}

CboSetValue( cboModes, dv.current( ).mode );

/*
    func > load ui
*/

async function LoadUI( renderMode )
{
    divBody.innerHTML = '';

    const arr = Object.entries( dv.app.metadataCache.unresolvedLinks )
    .filter( ( [ k, v ] )=> Object.keys( v ).length ) 
    .flatMap( ( [ k, v ] ) => 
        Object.keys( v ).map( x => 
        ({
                key: link_filter( x ),
                title: dv.fileLink( k ),
                title_path: k,
                link_orig: `${ dv.fileLink( x ) }`,
                link_src: `${ dv.fileLink( k ) }`,
                link_src_orig: `${ dv.fileLink( k ) } ( ${ dv.fileLink( x ) } )`,
                list: `${ dv.fileLink( x ) }`
        })
    ))
    .sort( ( a, b ) => dv.compare( a.key, b.key ) )

    if ( renderMode === 'Compact Mode' )
    {
        const elm_spacer            = dv.el( 'div', '<br />', { container: divBody, cls: 'atx-blv1-spacer-compact' } );
        hdrTitle.style.display      = 'none';
    }
    else
    {
        const elm_paragraph         = dv.paragraph( 'The following pages below contain unresolved links and should be fixed. Click each listed note below to create a new page.', { cls: 'atx-blv1-header-about', container: divBody } );
        const elm_spacer            = dv.el( 'div', '<br />', { container: divBody, cls: 'atx-blv1-spacer-full' } );
        hdrTitle.style.display      = 'block';
    }

    const data      = dv.array( arr ).groupBy( t => t.link_src ).where( t => t.rows.length > minRequired ).sort( t => t.rows.length, 'desc' )
    i_total         = data.length;
    let i_curr      = 0;

    dv.list(
        dv.array( data )
                .forEach( t =>
                {
                    const pageArr   = dv.pages( '"' + t.rows[ 0 ].title_path + '"' );
                    var i_items     = Object.keys( t.rows[ 0 ] ).length;
    
                    Promise.all( pageArr.map( async ( b ) =>
                    {
                        const file  = b.file
                        if ( file == null ) return;
    
                        i_curr++;
    
                        const file_name     = file.name || 'Unknown';
                        const file_path     = file.path || '';
                        const file_size     = file.size || 0;
                        const file_title    = file.frontmatter.name || file.frontmatter.title || file.frontmatter.alias || file_name;
                        const file_link     = dv.fileLink( file_path, false, file_title );
                        const file_list     = t.rows.list.join( '\n-  ' );
    
                        dv.el( 'div', file_link, { container: divBody, cls: 'atx-blv1-ct-left' } );
                        dv.el( 'div', t.rows.link_src.length, { container: divBody, cls: 'atx-blv1-ct-right atx-blv1-list-count' } );
                        dv.el( 'div', '', { container: divBody, cls: 'atx-blv1-ct-clear' } );

                        if ( renderMode === 'Full Mode' )
                            dv.el( 'div', file_path, { container: divBody, cls: 'atx-blv1-list-file-path' } );

                        dv.el( 'div', '  - ' + file_list, { container: divBody, cls: 'atx-blv1-list' } );
                        dv.el( 'div', '<br />', { container: divBody } );
            
                        if ( renderMode === 'Full Mode' && i_curr != i_total )
                            dv.el( 'div', '<br />', { container: divBody, cls: 'atx-blv1-spacer' } );
    
                    }))
    
                })
    )

    /*
        no results
    */
    
    if ( i_total === 0 )
    {
        const results = dv.el( 'div', 'No Broken Links Found 😊', { cls: 'atx-blv1-noresults' } );
        results.setAttribute( 'style', 'text-align:center;' );
    }

}

/*
    func > update data
*/

async function UpdateData( selected )
{
    let statusPage      = dv.current( ).mode;
    let setStatus       = 'Full Mode';

    if ( selected && selected != 'undefined' )
        setStatus       = selected;
    else if ( statusPage && statusPage != 'undefined' )
        setStatus       = statusPage;

    app.fileManager.processFrontMatter( file, fm =>
    {
        fm[ 'mode' ] = setStatus;
        LoadUI( setStatus );
    })
}

/*
    select box > on change
*/

cboModes.onchange = function( )
{
    const optSelected = cboModes.value;
    UpdateData( optSelected )
}

/*
    start
*/

UpdateData( );
```