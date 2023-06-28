# XML

- Extensible Markup Language
- Like HTML
- Hypertext Markup Language
- Used for creating websites
- XML can be used for any kind of structured data

XML has two ways of handling data called tags and attributes. 

## Tags

- Start tags have this format: <___>
- End tags have this format: </___>
- The start end end tags must match
- Tag names can only consist of letters, numbers, and underscores and must start
  with a letter

Example:

<artist>The instructors</artist>

- An empty tag can also end with />

Example:

<invitees/> the same as <invitees></invitees>

Content

What goes between the tags is called content

- Content is treated like a string, even though it doesn't have quotation marks
  around it
- You can also use it for numbers or true and false values. In that case, the software
  that reads the XML is responsible for converting it from a string into a number
  or a Boulean

Examples:

<city>New York</city>
<age>23</age>
<enabled>false</enabled>

Nested tags

- Putting tags inside other tags is how you create nested data

Examples:

<color>
    <red>205</red>
    <green>23</green>
    <blue>52</blue>
</color>

## Attributes

- In addition to content, tags can have attributes.
- Attributes are key/value pairs.
- Although both values are strings, the keys do not have quotes around them.
    - This means they must be letters, numbers, and underscores only. They must
      start with a letter. The values do have quotes around them.
- Attributes are placed inside of the start tag

Example:

<tag key="value">content</tag>

In the most common designs, attributes are not used for data, but are used to indicate
some property about the data (metadata).

The first line of an XML file

- XML declaration
- Indicates that it's an XML file, says what version, character encoding and so on.
- Optional
- As a writer, you can pretty much ignore this first line. It doesn't need to be documented.

Example:

<?xml version="1.0" encoding="UTF-8" standalone="no" ?>

Comments

- You can put comments into XML just like HTML.
- Comments start with <!-- end end with -->
- Everything it between is ignored  by the computer reading the XML

Example:

<!-- This element should be updated -->

Namespaces

- You might have a tag naming one thing in one context, and mean something else
  in a different context
- For this, you use namespaces to uniquely identify each tag
- The tag name has a "namespace:" prefix.

Example:

<education:onlineCourse>

White Space

- White space means spaces, new lines, tabs etc.

- White space doesn't matter. XML also pretty much ignores them when they're either
  before or after tags, or between tag names and attribute names
    - Unless it's inside quotation marks

Example:

<dog  breed="golden  retriever">

Good XML Formatting Guidelines

- In general, add an indent for every new level of tags
- Tags that do not contain other tags can have start and end tags on the same line.
- Use line breaks if the lines are getting too long
- Tags that contain other tags should be on their own line

Schemas

- A schema describes the structure of the XML file
- For XML, schema files are called XSD files which stands for XML Schema Definition
- Describes the tags, attributes and types
- The XSD files are in XML, so once you know XML, you'll find that they aren't that
  difficult to read
- They are extremely helpful in documenting XML because they contain all of the
  information that you need for your tables except the description

Example:

<?xml version="1.0" ?>
<dailyForecast>
	<date>2015-06-01</date>
	<description>sunny</description>
	<maxTemp unit="C">22</maxTemp>
	<minTemp unit="C">20</minTemp>
	<windSpeed unit="kph">12</windSpeed>
	<danger>false</danger>
</dailyForecast>

<?xml version="1.0" encoding="UTF-8"?>
<forecast>
	<dailyForecast>
		<date>2015-06-01</date>
		<description>sunny</description>
		<maxTemp unit="C">22</maxTemp>
		<minTemp unit="C">20</minTemp>
		<windSpeed unit="kph">12</windSpeed>
		<danger>false</danger>
	</dailyForecast>
	<dailyForecast>
		<date>2045-06-02</date>
		<description>windy</description>
		<maxTemp unit="C">22</maxTemp>
		<minTemp unit="C">20</minTemp>
		<windSpeed unit="kph">40</windSpeed>
		<danger>true</danger>
	</dailyForecast>
	<dailyForecast />
</forecast>

Documenting XML is like JSON

- Often in API will use both
- Elements now refer to tags and their content.

JSON and XML

- API requests can often use either JSON and XML
  - The request specifies which format to use
- In this case, you can try to create one table that documents both formats.
  - Table columns are the same
  - The key names in JSON and the tag names in XML should be the same
  - Types should be the identical (an element to be a string, a number or a Boolean
    in both JSON and XML)

There are two kinds of types in XML, simple and complex.

Simple Types

- In XML, technically all simple types are strings, but ...
- The software that reads the XML may convert that string into a number, Boolean,
  date, URL and so on
- So you should document the type.
  - Integer, float, Boolean, data ...
- This applies to both content and attribute values.

Complex Types

- Complex types are elements that contain other elements.
- List the element name in the type column.
- If you're documenting the XML file with multiple tables, then have a table for
  each element type.

Attributes

- The biggest structural difference between JSON and XML is that XML has attributes 
  and JSON doesn't.
    - If an API uses both JSON and XML, then typically the XML does not have attributes.
- If you're documenting XML with only a few small number of attributes, then put
  the attribute information into the notes column.
- If you're documenting XML with many attributes, then add a column for attributes.

