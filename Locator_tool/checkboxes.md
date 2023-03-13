## Checkboxes within a group
### data definition
```xml
<system-data-structure definition-path="System-outages">
    <outage>
      <websites>
        <value>https://www.helpinsure.com</value>
        <value>https://texashealthcarecosts.org/</value>
        <value>http://www.texashealthoptions.com/index.html</value>
        <value>https://www.texashealthplancompare.com/index.html</value>
      </websites>
    </outage>
</system-data-structure>
```

### Velocity

````
## Get all data definition groups
#set ( $outages = $currentPage.getStructuredDataNodes("outage") )

## Loop through each group
#foreach( $outage in $outages)

  ## Get the checkbox group
  #set ( $websites = $outage.getChild( "websites" ) )
  $_PropertyTool.outputProperties( $websites )
#*
#Object type: com.hannonhill.cascade.api.adapters.StructuredDataNodeAPIAdapter
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
```

