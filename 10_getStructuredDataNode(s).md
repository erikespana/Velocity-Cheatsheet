#Data Definition Fields
[Checkboxes](#checkboxes)
[Images](#images)
[Groups](#groups)
## Checkboxes
data definition
```xml
<system-data-structure>
	<contentTypes>
		<value>Ordered List</value>
	</contentTypes>
```
Velocity
```velocity
## $currentPage.getStructuredDataNodes("contentTypes").get(0).Class.Name
## com.hannonhill.cascade.api.adapters.StructuredDataNodeAPIAdapter

## $currentPage.getStructuredDataNodes("contentTypes").get(0).getIdentifier()
## contentTypes

$currentPage.getStructuredDataNodes("contentTypes").get(0).textValues.size()
## 2

$currentPage.getStructuredDataNodes("contentTypes").get(0).textValues[1]
## Ordered List

## $_PropertyTool.outputProperties( $currentPage.getStructuredDataNodes("contentTypes").get(0) )
 Object type: com.hannonhill.cascade.api.adapters.StructuredDataNodeAPIAdapter
Properties:
 - group: boolean
 - asset: FolderContainedAsset
 - asset: boolean
 - assetType: String
 - assetIdentifier: PathIdentifier
 - textValues: String[]
 - identifier: String
 - group: StructuredDataNode[]
 - getChildren(String): StructuredDataNode[]
 - children: StructuredDataNode[]
 - text: boolean
 - textValue: String
 - identifer: Identifier
 - textValueAsXMLElement: Element
 - textNodeOptions: TextNodeOptions
 - getChild(String): StructuredDataNode
 - allowCustomValues: boolean
 - children: StructuredDataNode[]
 - getChildren(String): StructuredDataNode[]
 - text: boolean
 - group: StructuredDataNode[]
 - identifier: String
 - assetIdentifier: PathIdentifier
 - textValues: String[]
 - asset: FolderContainedAsset
 - group: boolean
 - persisted: boolean
 - asset: boolean
 - allowCustomValues: boolean
 - textNodeOptions: TextNodeOptions
 - getChild(String): StructuredDataNode
 - textValueAsXMLElement: Element
 - class: Class
 - textValue: String
```
## Images
Data Definition
```
<system-data-structure>
	<group identifier="iconpic" label="Main Page Image" collapsed="true">
		<asset type="file" identifier="image" label="Image"/>
  </group>
</system-data-structure>
```
Velocity
```
$currentPage.getStructuredDataNode("iconpic/image").Asset.Link
## Output: site://TDI/takefive/artwork/newyearstips-index.jpg
```
## Groups
Data Definition
```
<system-data-structure>
  <group identifier="newsandevents" label="News and Events" restrict-to-groups="news">
      <group identifier="item" label="Headline" restrict-to-groups="news">
          <text identifier="headline" label="Headline" restrict-to-groups="news" required="true"/>
          <text identifier="link" label="Link" restrict-to-groups="news" required="true"/>
          <asset type="file" identifier="image" label="Thumbnail (247 x 98)" required="true" help-text="Photo must be resized to the correct dimensions in Photoshop"/>
      </group>
  </group>
</system-data-structure>
```

Multiple groups
```
#set ( $item = $currentPage.getStructuredDataNodes("newsandevents/item").get(0) )
<img src="${item.getChild("image").getAsset().link}" />
<a href="${item.getChild("link").textValue}">
    ${_EscapeTool.xml( $item.getChild("headline").textValue )}
</a>
```
