# Relationships

1. Use the locator tool to get a file
```velocity
#set( $file = $_.locateFile("/path/to/file.pdf", "site" )
$_PropertyTool.outputProperties( $file )
```
Output
```
Properties:
...
- linkingAssets: List
...
```
2. Get the file's relationships (Cascade)
```
$_PropertyTool.outputProperties( $file.linkingAssets )
```
Output
```Properties:
...
- linkingAssets: List
...
```
