Page XML
```
<system-page>
  ...
  <dynamic-metadata>
    <name>homepage</name>
    <value>Insurance</value>
  </dynamic-metadata>
```

Velocity
```
$page.metadata.getDynamicField("homepage").value
## Insurance
```

```
## Get dynamic metadata fields
#set ($linkStatus = $currPage.metadata.getDynamicField("HarveyLink").value )
#set ($language = $currPage.metadata.getDynamicField("Language").value )
```

Multiselect field

```
#set ($categories   = $_XPathTool.selectNodes($page, "dynamic-metadata[name='categories']/value"))
...
#if ( $categories.size() > 0)
    #foreach ( $category in $categories )
       #if ( $category.value == "Public Hearing")
           <p><strong>Notice of public hearing</strong></p>
       #end
    #end
#end
```
