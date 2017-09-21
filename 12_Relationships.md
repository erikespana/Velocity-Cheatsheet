# Relationships

get a file using the Locator tool
```velocity
#set( $file = $_.locateFile("/path/to/file.pdf", "site" )
$_PropertyTool.outputProperties( $file )

## Output
#Object type: com.hannonhill.cascade.api.adapters.FileAPIAdapter
Properties:
- linkingAssets: List
...
```

get the file's Cascade relationships 
```
$_PropertyTool.outputProperties( $file.linkingAssets )

## Output
#Object type: java.util.ArrayList
Properties:
 - get(int): Object
 - empty: boolean
 - empty: boolean
 - get(int): Object
 - class: Class
```
