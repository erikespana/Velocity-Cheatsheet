There are few kinds of Date fields in Cascade.
Examples of how to read dates from them.

## Meta data fields

### Start, End and Review Date fields

## Data definitions

### Date-time

````
#set ( $dateDisplayFormat = "MMMMM d, yyyy")

## Date-time field is called "publication-date"
#set ( $publicationDate = $blog.getStructuredDataNode("publication-date").textValue )
#set ( $publicationDateDate = $_DateTool.getDate( $publicationDate) )

````

### Date
