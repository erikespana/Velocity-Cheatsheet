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
