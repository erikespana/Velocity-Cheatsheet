# Getting a File's Relationships

```
## get a file using the Locator tool
#set( $file = $_.locateFile("/path/to/file.pdf", "site" )

## if the file has relationships
#if ( $file.linkingAssets.size() > 0 )
    
    ## loop through each relationship
    #foreach ( $relationship in $file.linkingAssets )
        
        ## check if the relationship is a Page object
        #if ( $relationship.assetType == "page")
        
            ## and print out the page's link
            $relationship.link
            
        #else
        
            ## print assetType
            $relationship.assetType
            
        #end
    #end
#end
```

## How we got there
got a file using the Locator tool
```
#set( $file = $_.locateFile("/path/to/file.pdf", "site" )
$_PropertyTool.outputProperties( $file )

#Object type: com.hannonhill.cascade.api.adapters.FileAPIAdapter
Properties:
- linkingAssets: List
...
```

got the file's Cascade relationships 
```
$_PropertyTool.outputProperties( $file.linkingAssets )

#Object type: java.util.ArrayList
Properties:
 - get(int): Object
 - empty: boolean
 - empty: boolean
 - get(int): Object
 - class: Class
```
and saw that the relationship was a Page object with a "link" attribute
```
$_PropertyTool.outputProperties( $file.linkingAssets.get(0) )

#Object type: com.hannonhill.cascade.api.adapters.PageAPIAdapter
Properties:
 - dataDefinitionPath: String
 - siteId: String
 - shouldBeIndexed: boolean
 - siteId: String
 - currentUserCanRead: boolean
 - link: String
 - currentUserCanRead: boolean
 - getStructuredDataNode(String): StructuredDataNode
 - label: String
 - siteName: String
 - structuredData: StructuredDataNode[]
 - getStructuredDataNodes(String): StructuredDataNode[]
 - siteName: String
 - label: String
 - lastPublishedOn: Date
 - xHTMLAsXMLElement: Element
 - parentFolder: Folder
 - parentFolder: Folder
 - xHTML: String
 - assetType: String
 - lastPublishedOn: Date
 - isUserCanRead(String): boolean
 - hideSystemName: boolean
 - lastModifiedBy: String
 - folderOrder: int
 - hideSystemName: boolean
 - lastModifiedBy: String
 - folderOrder: int
 - lastModified: Date
 - isUserCanRead(String): boolean
 - persisted: boolean
 - metadata: Metadata
 - lastModified: Date
 - link: String
 - identifer: Identifier
 - metadata: Metadata
 - identifier: PathIdentifier
 - shouldBeIndexed: boolean
 - identifier: PathIdentifier
 - name: String
 - assetType: String
 - dataDefinitionPath: String
 - xHTMLAsXMLElement: Element
 - createdOn: Date
 - getStructuredDataNode(String): StructuredDataNode
 - createdOn: Date
 - createdBy: String
 - createdBy: String
 - identifer: Identifier
 - structuredData: StructuredDataNode[]
 - getStructuredDataNodes(String): StructuredDataNode[]
 - site: Site
 - site: Site
 - shouldBePublished: boolean
 - isUserCanWrite(String): boolean
 - currentUserCanWrite: boolean
 - isUserCanWrite(String): boolean
 - parentFolderIdentifier: PathIdentifier
 - parentFolderIdentifier: PathIdentifier
 - lastPublishedBy: String
 - currentUserCanWrite: boolean
 - lastPublishedBy: String
 - shouldBePublished: boolean
 - linkingAssets: List
 - path: String
 - path: String
 - name: String
 - class: Class
 - linkingAssets: List
 - xHTML: String
```
```
$_PropertyTool.outputProperties( $file.linkingAssets.get(0).link )

#Object type: java.lang.String
Properties:
 - empty: boolean
 - getChars(intintchar[]int): void
 - bytes: byte[]
 - getBytes(String): byte[]
 - getBytes(intintbyte[]int): void
 - getBytes(Charset): byte[]
 - class: Class
```

