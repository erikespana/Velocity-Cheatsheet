# Relationships

- [Files](#file)
- [Pages](#pages)

Velocity
```velocity
#set( $file = $_.locateFile("/path/to/file.pdf", "site" )
$_PropertyTool.outputProperties( $file )
```
## Outputs
data definition
```Properties:
- linkingAssets: List
```
