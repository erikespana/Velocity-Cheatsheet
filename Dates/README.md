There are few kinds of Date fields in Cascade.
Examples of how to read dates from them.

## Meta data fields

### Start, End and Review Date fields

## Data definitions

### Date-time

Uses [$_DateTool.format](https://www.hannonhill.com/cascadecms/latest/developing-in-cascade/script-formats/velocity-tools.html#_DateTool_format) to format date according to Java's [date format pattern syntax](https://docs.oracle.com/javase/tutorial/i18n/format/simpleDateFormat.html). Some patterns have abbreviated and full forms. For example the between 1 and 3 M symbols returns Mar but four or more EEEE returns March. 
Java also has [predefined formats](https://docs.oracle.com/javase/tutorial/i18n/format/dateFormat.html)

````
#set ( $dateDisplayFormat = "MMMMM d, yyyy")

## Date-time field is called "publication-date"
#set ( $publicationDate = $blog.getStructuredDataNode("publication-date").textValue )
#set ( $publicationDateDate = $_DateTool.getDate( $publicationDate) )
#set ( $blogDateText = $_DateTool.format( $dateDisplayFormat, $publicationDateDate ) )

````

### Date
