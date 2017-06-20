# Table of Contents

- [Substring](#substring)

## .contains()

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
