```
#foreach( $blog in $sortedBlogs )
    #set ( $blogCheckboxTags = $blog.getStructuredDataNodes("blog-tags") )
    $_PropertyTool.outputProperties( $blogCheckboxTags )
    #*
    Object type: [Lcom.hannonhill.cascade.api.asset.common.StructuredDataNode;
    Properties:
     - class: Class
    *#

    #set ( $blogCheckboxTags = $blog.getStructuredDataNodes("blog-tags").get(0) )
    $_PropertyTool.outputProperties( $blogCheckboxTags )
    #*
    Object type: com.hannonhill.cascade.api.adapters.StructuredDataNodeAPIAdapter
    Properties:
     - allowCustomValues: boolean
     - asset: FolderContainedAsset
     - asset: boolean
     - assetId: String
     - assetIdentifier: PathIdentifier
     - assetType: String
     - children: StructuredDataNode[]
     - class: Class
     - definitionFieldId: String
     - getChild(String): StructuredDataNode
     - getChildWithFieldId(String): StructuredDataNode
     - getChildren(String): StructuredDataNode[]
     - getChildrenWithFieldId(String): List
     - group: StructuredDataNode[]
     - group: boolean
     - identifer: Identifier
     - identifier: String
     - label: String
     - persisted: boolean
     - possibleFieldItems: List
     - selectedFieldItems: List
     - text: boolean
     - textNodeOptions: TextNodeOptions
     - textValue: String
     - textValueAsXMLElement: Element
     - textValues: String[]
    *#
    
    #set ( $blogCheckboxTags = $blog.getStructuredDataNodes("blog-tags").get(0).selectedFieldItems )
    $_PropertyTool.outputProperties( $blogCheckboxTags )
    *#
    Object type: java.util.ArrayList
    Properties:
     - class: Class
     - empty: boolean
     - get(int): Object
    *#
    
    ## $blogCheckboxTags now contains array of objects (checkbox name, checkbox value)
    
    ## Create array of checkbox values
    
    #set ( $cbeckboxValues = [] ) ## Initialize array
    ## Loop through array of objects
    #foreach ( $checkbox in $blogCheckboxTags )
        #set ( $void = $cbeckboxValues.add( $checkbox.value ) )
    #end
    $cbeckboxValues.size() ## Display array size
```
