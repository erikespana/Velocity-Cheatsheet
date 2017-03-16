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
