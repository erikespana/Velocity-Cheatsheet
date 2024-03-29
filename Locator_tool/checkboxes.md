## Checkboxes within a group
- [Get all data definition groups](#get-all-data-definition-groups)
- [Loop through each group](#loop-through-each-group)
- [Use selectedFieldItems: List to get the selected checkboxes](#use-selectedfielditems-list-to-get-the-selected-checkboxes)
- [Combine two or more checkbox "selectedFieldItems" lists](#combine-two-or-more-checkbox-selectedfielditems-lists)
- [Sort a checklist `selectedFieldItems` list by label](#sort-a-checklist-selectedfielditems-list-by-label)
- [Display `selectedFieldItems` labels and values](#display-selectedfielditems-labels-and-values)

### data definition

```xml
<system-data-structure definition-path="System-outages">
    <outage>
      <websites>
        <value>https://downdetector.com/</value>
        <value>https://www.github.com</value>
        <value>https://www.hannonhill.com/</value>
        <value>https://www.youtube.com/</value>
      </websites>
    </outage>
</system-data-structure>
```

### Velocity
#### Get all data definition groups
````
#set ( $outages = $currentPage.getStructuredDataNodes("outage") )
````
#### Loop through each group
````
#foreach( $outage in $outages)

    ## Get the checkbox group
    #set ( $websites = $outage.getChild( "websites" ) )
    #*
    $_PropertyTool.outputProperties( $websites )
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
````
#### Use `selectedFieldItems: List` to get the selected checkboxes
````
## $websites.selectedFieldItems.size()
## 4
````
#### Combine two or more checkbox "selectedFieldItems" lists
````
    #set ( $multipleSelectedFieldItems = [] )
    #set ( $void = $multipleSelectedFieldItems.addAll( $websites.selectedFieldItems) )
    #set ( $void = $multipleSelectedFieldItems.addAll( $checkboxGroup2.selectedFieldItems ) )
    
    #*
    $_PropertyTool.outputProperties( $multipleSelectedFieldItems )
    
    Object type: java.util.ArrayList
    Properties:
     - class: Class
     - empty: boolean
     - get(int): Object
    *#
#end ## foreach
````
#### Sort a checklist `selectedFieldItems` list by label

`#set( $sortedCheckboxes = $_SortTool.sort( $multipleSelectedFieldItems, "label:asc") )`

#### Display `selectedFieldItems` labels and values

````
#foreach ( $checkbox in $sortedCheckboxes )
     #*
        $_PropertyTool.outputProperties( $checkbox )
        Object type: com.hannonhill.cascade.api.adapters.FieldItemImpl
        Properties:
         - class: Class
         - label: String
         - value: String
    *#
    $checkbox.label, $checkbox.value
#end
````

