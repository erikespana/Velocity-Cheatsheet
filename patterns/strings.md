# Table of Contents

- [indexOf](#indexOf)
- [Substring](#substring)

## .contains()

## indexOf
int indexOf (String str, int fromIndex)
Returns the index within this string of the first occurrence of the specified substring, starting at the specified index.
https://docs.oracle.com/javase/8/docs/api/java/lang/String.html

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
