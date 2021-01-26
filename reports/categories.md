##set ( $page = $_.locatePage("/takefive/accident-caused-by-other-driver", "TDI") )
##$_PropertyTool.outputProperties( $page.metadata.getDynamicField("category") )
#*
Object type: com.hannonhill.cascade.api.adapters.DynamicMetadataFieldImpl
Properties:
 List: possibleFieldItems, selectedFieldItems
 String: name, label
 String[]: values
 boolean: multiselect, radio, dropdown, datetime, checkbox
 - class: Class
*#

##$_PropertyTool.outputProperties( $page.metadata.getDynamicField("category").selectedFieldItems.get(0).value )
#*
#set ($categories = $page.metadata.getDynamicField("category"))
#set ($categories = $_ListTool.toList( $categories.values ))
$categories.contains("Auto / vehicle")
*#

#*
#set ( $page = $_.locatePage("/takefive/accident-caused-by-other-driver", "TDI") )
$_PropertyTool.outputProperties( $page.metadata.getDynamicField("category").selectedFieldItems )
$_PropertyTool.outputProperties( $page.metadata.getDynamicField("category").selectedFieldItems.get(0).value )
$page.metadata.getDynamicField("category").selectedFieldItems.get(1).value

Auto / vehicle
General tips / other
*#
