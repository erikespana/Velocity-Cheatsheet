# Table of Contents

- [contains](#contains)
- [indexOf](#indexof)
- [replaceAll](replaceall)
- [stripTags](striptags)
- [Substring](#substring)
- [Parsing file extensions](#Parsing file extensions)
- [toLowerCase](#fileExtensions)

## contains

## indexOf
int indexOf (String str, int fromIndex)
Returns the index within this string of the first occurrence of the specified substring, starting at the specified index.
Excerpt from script that searches page WYSIWYG's for CSS classes:
```
#set ( $datadef = $a.dataDefinitionPath )
#if ( $datadef == "Standard Page" )
  #if (! $_PropertyTool.isNull( $a.getStructuredDataNode("content") ) )
    ## save WYSIWYG content to variable
    #set ( $wysiwyg = $a.getStructuredDataNode("content").textValue )
    ## $class = 0 (-1 + 1) if not found, 1 (0 + 1) if found in first position, etc
    #set ( $matchindexof = $wysiwyg.indexOf("class=${q}right${q}", 0) + 1 )
```
https://docs.oracle.com/javase/8/docs/api/java/lang/String.html

## replaceAll
Examples:
- [Read and merge css files](http://help-archives.hannonhill.com/discussions/velocity-formats/13573-read-and-merge-css-files)
- [Not sure how to read part of my XML feed.](http://help-archives.hannonhill.com/discussions/velocity-formats/11937-not-sure-how-to-read-part-of-my-xml-feed)

## stripTags

```
DisplayTool.stripTags($string)
```
- [How to strip HTML from dynamic metadata in a Velocity format](http://help-archives.hannonhill.com/discussions/velocity-formats/47-how-to-strip-html-from-dynamic-metadata-in-a-velocity-format)
- http://www.hannonhill.com/kb/Script-Formats/#display-tool

## Substring
Extract characters before the first space in a string
```
#set ($indexOfSpace = $str.indexOf(' '))
#if ($indexOfSpace > -1)
  #set($substr = $_DisplayTool.truncate($str, $indexOfSpace, ''))
#else
  ## string doesn't have a space
  #set($substr = $str)
#end
```

## Parsing file extensions
`#set ( $extension = $_StringTool.substringAfter( $asset.name, "." ).toLowerCase() )`
