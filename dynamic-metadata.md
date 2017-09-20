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
