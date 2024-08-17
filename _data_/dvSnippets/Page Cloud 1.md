```dataviewjs
/*
    Snippet: Page Cloud - Version 1

    This snippet requires the Dataview Plugin
        https://github.com/blacksmithgu/obsidian-dataview

    View settings at:
        https://github.com/Aetherinox/obsidian-dataview-snippets/tree/main/Snippets/Page%20Cloud%201

    Creates a cloud which shows all of the pages that exist in your vault.
*/

/*
    Settings
*/

const QueryStr          = `""`;
const QueryFiles        = dv.pages( QueryStr );

const sortOption        = 1;
const weightBacklinks   = 0.1;
const weightWordCount   = 0.5;
const minFontSize       = 12;
const maxFontSize       = 32;
const arrColors         = [];

/*
    Generate 40 colors
*/

for ( let i = 0; i < 40; i++ )
{

    let R           = Math.floor( ( Math.random( ) * 100 ) + 100 );
    let G           = Math.floor( ( Math.random( ) * 100 ) + 100 );
    let B           = Math.floor( ( Math.random( ) * 100 ) + 100 );
    
    let rgb         = ( R << 16 ) + ( G << 8 ) + B;
    let itemColor   = `#${rgb.toString( 16 )}`;

    arrColors.push( itemColor );
}

/*
    Get all backlinks
*/

async function QueryBacklinks( q )
{
    const file = q.split( '/' ).pop( ).split( "." ).slice( 0, -1 ).join( "." );
    return dv.query(
    `
    LIST
    FROM [[${file}]] AND ${QueryStr}
    `
    );
}

/*
    Get number of words in each file
*/

async function QueryWordcount( q )
{
    const fs            = require( 'fs' );
    const path          = require( 'path' );
    const text          = fs.readFileSync( path.join( app.vault.adapter.basePath, q ), 'utf-8' );
    const pattern       = /---[\s\S]*?---|```[\s\S]*?```|\$[\s\S]*?\$|\$\$[\s\S]*?\$\$/g;
    const cleanedText   = text.replace( pattern, '' );
    const matchText     = cleanedText.match( /\S+/g );

    if ( !matchText )
        return 0;
    
    return matchText.length;
}

/*
    Calculate font text size which is determined by number of backlinks
    and number of words available.
*/

function Generate_FontSize( backlinks, wordCount )
{
    const calcFontSize = Math.sqrt( ( backlinks * weightBacklinks ) + ( wordCount * weightWordCount ) ) * 2.5;
    return Math.round( ( calcFontSize / 100 ) * ( maxFontSize - minFontSize ) + minFontSize );
}

/*
    Generate font color
*/

function Generate_Color( tagName )
{
    if ( tagName == null ) { return "#FFFFFF"; }

    const tagWords      = tagName.split( /\W+/g );
    const colorIndex    = tagWords.reduce( ( total, word ) => total + word.charCodeAt( 0 ), 0 ) % Object.keys( arrColors ).length;

    return arrColors[ Object.keys( arrColors )[ colorIndex ] ];
}

/*
    Sort > DESC / ASC

    alphabetize array results
*/

function Sort_DESC( arr )
{
    arr.sort( ( a, b ) => a.id.localeCompare( b.id ) )
    return arr;
}

function Sort_ASC( arr )
{
    arr.sort( ( a, b ) => b.id.localeCompare( a.id ) )
    return arr;
}

/*
    Sort > Shuffle

    randomized array results
*/

function Sort_Shuffle( arr )
{
    for ( let i = arr.length - 1; i > 0; i-- )
    {
        const j                 = Math.floor( Math.random( ) * ( i + 1 ) );
        [ arr[ i ], arr[ j ] ]  = [ arr[ j ], arr[ i ] ];
    }

    return arr;
}

/*
    Create page cloud
*/

const CreatePageCloud = async ( ) =>
{
    const files     = new Map( );

    /*
        Add all .md files to the tags map with their backlinks and word count
    */

    Promise.all( QueryFiles.map( async ( f ) =>
    {
        const file              = f.file
        const blq               = QueryBacklinks( file.path )
        const wcq               = QueryWordcount( file.path )

        const fileInfo          = { backlinks: 0, wordCount: 0 };
        const res               = await blq;
        fileInfo.backlinks      = res.value.values.length;
        const wc                = await wcq;
        fileInfo.wordCount      = wc;

        files.set( file, fileInfo );

    })).then( ( ) =>
    {
        const data = []

        /*
            Calculate font size and font color.
        */

        files.forEach( ( fileInfo, fileName ) =>
        {
            if ( fileName == null )
                return;

            var file_name_fm    = fileName.frontmatter.name || fileName.frontmatter.title || fileName.frontmatter.alias;
            var file_name       = fileName.name

            if (file_name_fm)
                file_name       = file_name_fm;

            const fontSize      = Generate_FontSize( fileInfo.backlinks, fileInfo.wordCount );
            const color         = Generate_Color( fileName.name );
            const length        = 0;

            data.push( { name: file_name, id: fileName.name, size: fileName.size, path: fileName.path, fontSize, color } );
        });

        /*
            Sorting functions
        */

        const sortOptions =
        {
            1: 'Sort_DESC',
            2: 'Sort_ASC',
            3: 'Sort_Shuffle',
        };

        let funcSort = sortOptions[ sortOption ]

        if ( funcSort === undefined )
            funcSort = sortOptions[ 1 ]

        /*
            Return results
        */

        return eval( funcSort )( data ).map( ( tag ) =>
        {
            return `<span class="page-cloud-v1-item"><a class="page-cloud-v1-link" href="obsidian://open?file=${encodeURIComponent(tag.id)}" style="font-size:${tag.fontSize}px; color: ${tag.color};">${tag.name}</a></span>`;
        }
    ).join( "" );
    } ).then( res => dv.paragraph( res ) )
    .catch( error =>
    {
        console.error( "Error: " + error );
    } );
}

CreatePageCloud( )
```