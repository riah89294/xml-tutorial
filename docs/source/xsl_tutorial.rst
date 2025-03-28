Welcome to XML TUTORIAL!
#########################

We learned that XML stands for **eXtensible Markup Language**. Designed to store and transport data and designed to be both human- and machine-
readable.
We learned that we need to study XML because it's plays an important role in many different IT systems, often used for distributing data
over the Internet and It is important (for all types of software developers!) to have a good understanding of XML. This time we will
learn, What is XML? How does XML work? How can I use XML? What can I use XML for?

XML is quite self-descriptive like It has sender information, It has receiver information, It has a heading, It has a message body. But
still, the XML above does not DO anything. XML Does Not Use Predefined Tags. XML is Extensible. XML simplifies data sharing, simplifies
data transport, simplifies platform changes, simplifies data availability. XML became a W3C Recommendation as early as in February 1998.

We also learned that XML is used in many aspects of web development, XML is often used to separate data from presentation. Thousands of
XML formats exist, in many different industries, to describe day-to-day data transactions: Stocks and Shares Financial transactions
Medical data Mathematical data Scientific measurements News information Weather services

Here's the example of XML:
<?xml version="1.0" encoding="UTF-8"?>
<note>
  <to>Tove</to>
  <from>Jani</from>
  <heading>Reminder</heading>
  <body>Don't forget me this weekend!</body>
</note>

Here's the example of XML News:
<?xml version="1.0" encoding="UTF-8"?>
<nitf>
  <head>
    <title>Colombia Earthquake</title>
  </head>
  <body>
    <headline>
      <hl1>143 Dead in Colombia Earthquake</hl1>
    </headline>
    <byline>
      <bytag>By Jared Kotler, Associated Press Writer</bytag>
    </byline>
    <dateline>
      <location>Bogota, Colombia</location>
      <date>Monday January 25 1999 7:28 ET</date>
    </dateline>
  </body>
</nitf>

XML documents form a tree structure that starts at "the root" and branches to "the leaves". XML documents are formed as element trees. An
XML tree starts at a root element and branches from the root to child elements. All elements can have sub elements (child elements).

<root>
  <child>
    <subchild>.....</subchild>
  </child>
</root>

XML uses a much self-describing syntax. A prolog defines the XML version and the character encoding. Prolog is must the first in the
document. The next line is the root element of the document. The syntax rules of XML are very simple and logical. The rules are easy to
learn, and easy to use. And XML documents must contain one root element that is the parent of all other elements. All elements must have a
closing tag, if no closing tag it will become illegal. We nlearned that XML is a case sentitive, all elements of XML must be properly
nested within each other. XML Attribute Values Must Always be Quoted. XML using Entity Reference, to avoid conflict with special
character. XML syntax error is similar to HTML and White-space is Preserved in XML. XML Stores New Line as LF Windows applications store a 
new line as: carriage return and line feed(CR+LF). XML documents that conform to the syntax rules above are said to be "Well Formed" XML
documents. An XML document contains XML Elements.An XML element is everything from (including) the element's start tag to (including) the
element's end tag. element can contain: text, attributes, other elements or a mix of the above. An element with no content is said to be
empty but Empty elements can have attributes.

<bookstore>
  <book category="children">
    <title>Harry Potter</title>
    <author>J K. Rowling</author>
    <year>2005</year>
    <price>29.99</price>
  </book>
  <book category="web">
    <title>Learning XML</title>
    <author>Erik T. Ray</author>
    <year>2003</year>
    <price>39.95</price>
  </book>
</bookstore>

We learned that XML elements must follow these naming rules: Element names are case-sensitive Element names must start with a letter or
underscore Element names cannot start with the letters xml (or XML, or Xml, etc) Element names can contain letters, digits, hyphens,
underscores, and periods Element names cannot contain spaces

We learned also about how to make a best naming in XML which we can use to make an XML. As the XML is extensible so XML elements can be
extended carry more information, it would not crash or break the application, and this is one of the beauty of XML. As XML can have
attributes like HTML, Attributes here are designed to contain data related to a specific element, but attributes must be qouted. But some
things to consider when using attributes such as attributes cannot contain multiple values (elements can), attributes cannot contain tree
structures (elements can, )attributes are not easily expandable (for future changes). Metadata (data about data) should be stored as
attributes, and the data itself should be stored as elements. Also XML Namespaces provide a method to avoid element name conflicts. We
learned that if our XML have a conflict in namespace we can use prefix to fix this. When using prefixes in XML, a namespace for the
prefix must be defined. The namespace can be defined by an xmlns attribute in the start tag of an element. The namespace declaration has
the following syntax. xmlns:prefix="URI". Uniform Resource Identifier (URI) A Uniform Resource Identifier (URI) is a string of characters
which identifies an Internet Resource. The most common URI is the Uniform Resource Locator (URL) which identifies an Internet domain
address. Another, not so common type of URI is the Uniform Resource Name (URN).

Here's the example if XML have conflict and fixed it by using prefix
<root>

<h:table xmlns:h="http://www.w3.org/TR/html4/">
  <h:tr>
    <h:td>Apples</h:td>
    <h:td>Bananas</h:td>
  </h:tr>
</h:table>

<f:table xmlns:f="https://www.w3schools.com/furniture">
  <f:name>African Coffee Table</f:name>
  <f:width>80</f:width>
  <f:length>120</f:length>
</f:table>

</root>

Raw XML files can be viewed in all major browsers. Don't expect XML files to be displayed as HTML pages. We learned about why XMl display
as XML, because XML documents do not carry information about how to display the data. Since XML tags are "invented" by the author of the
XML document, browsers do not know if a tag like

describes an HTML table or a dining table. Without any information about how to display the data, the browsers can just display the XML
document as it is. Additionally, All modern browsers have a built-in XMLHttpRequest object to request data from a server. The
XMLHttpRequest object is a developers dream, because you can: Update a web page without reloading the page Request data from a server -
after the page has loaded Receive data from a server - after the page has loaded Send data to a server - in the background

var xhttp = new XMLHttpRequest();
xhttp.onreadystatechange = function() {
    if (this.readyState == 4 && this.status == 200) {
       // Typical action to be performed when the document is ready:
       document.getElementById("demo").innerHTML = xhttp.responseText;
    }
};
xhttp.open("GET", "filename", true);
xhttp.send();

from the example above, The first line creates an XMLHttpRequest object. The onreadystatechange property specifies a function to be
executed every time the status of the XMLHttpRequest object changes. When readyState property is 4 and the status property is 200, the
response is ready. The responseText property returns the server response as a text string. The text string can be used to update a web
page.

All major browsers have a built-in XML parser to access and manipulate XML.

This example parses a text string into an XML DOM object, and extracts the info from it with JavaScript:

<html>
<body>

<p id="demo"></p>

<script>
var text, parser, xmlDoc;

text = "<bookstore><book>" +
"<title>Everyday Italian</title>" +
"<author>Giada De Laurentiis</author>" +
"<year>2005</year>" +
"</book></bookstore>";

parser = new DOMParser();
xmlDoc = parser.parseFromString(text,"text/xml");

document.getElementById("demo").innerHTML =
xmlDoc.getElementsByTagName("title")[0].childNodes[0].nodeValue;
</script>

</body>
</html>

Also the XMLHttpRequest Object The XMLHttpRequest Object has a built in XML Parser. The responseText property returns the response as a
string. The responseXML property returns the response as an XML DOM object. If you want to use the response as an XML DOM object, you can
use the responseXML property.

We learned also the XML DOM stands for Document Object Model, this defines a standard for accessing and manipulating documents. It is
also is a platform and language-neutral interface that allows programs and scripts to dynamically access and update the content,
structure, and style of a document. It presents an XML document as a tree-structure.

Here's the example of XML DOM

<?xml version="1.0" encoding="UTF-8"?>
<bookstore>

  <book category="cooking">
    <title lang="en">Everyday Italian</title>
    <author>Giada De Laurentiis</author>
    <year>2005</year>
    <price>30.00</price>
  </book>

  <book category="children">
    <title lang="en">Harry Potter</title>
    <author>J K. Rowling</author>
    <year>2005</year>
    <price>29.99</price>
  </book>

</bookstore>

XML has XPath, XPath is a major element in the XSLT standard and it can be used to navigate through elements and attributes in an XML
document. XPath is a syntax for defining parts of an XML document XPath uses path expressions to navigate in XML documents XPath contains
a library of standard functions XPath is a major element in XSLT and in XQuery XPath is a W3C recommendation XPath uses path expressions
to select nodes or node-sets in an XML document. These path expressions look very much like the expressions you see when you work with a
traditional computer file system. XPath is a major element in the XSLT standard. With XPath knowledge you will be able to take great
advantage of XSL.

Here's the example of XPath
<?xml version="1.0" encoding="UTF-8"?>

<bookstore>

<book category="cooking">
  <title lang="en">Everyday Italian</title>
  <author>Giada De Laurentiis</author>
  <year>2005</year>
  <price>30.00</price>
</book>

<book category="children">
  <title lang="en">Harry Potter</title>
  <author>J K. Rowling</author>
  <year>2005</year>
  <price>29.99</price>
</book>

<book category="web">
  <title lang="en">XQuery Kick Start</title>
  <author>James McGovern</author>
  <author>Per Bothner</author>
  <author>Kurt Cagle</author>
  <author>James Linn</author>
  <author>Vaidyanathan Nagarajan</author>
  <year>2003</year>
  <price>49.99</price>
</book>
<book category="web">
  <title lang="en">Learning XML</title>
  <author>Erik T. Ray</author>
  <year>2003</year>
  <price>39.95</price>
</book>

</bookstore>

Well, There's XSLT also. With XSLT you can transform an XML document into HTML. XSLT stands for eXtensible Stylesheet Language
Transformations, is the recommended style sheet language for XML. With XSLT you can add/remove elements and attributes to or from the
output file. You can also rearrange and sort elements, perform tests and make decisions about which elements to hide and display, and a
lot more. XSLT uses XPath to find information in an XML document.

Here's the example XSLT using XML document.
<?xml version="1.0" encoding="UTF-8"?>
<breakfast_menu>

<food>
<name>Belgian Waffles</name>
<price>$5.95</price>
<description>Two of our famous Belgian Waffles with plenty of real maple syrup</description>
<calories>650</calories>
</food>

<food>
<name>Strawberry Belgian Waffles</name>
<price>$7.95</price>
<description>Light Belgian waffles covered with strawberries and whipped cream</description>
<calories>900</calories>
</food>

<food>
<name>Berry-Berry Belgian Waffles</name>
<price>$8.95</price>
<description>Light Belgian waffles covered with an assortment of fresh berries and whipped cream</description>
<calories>900</calories>
</food>

<food>
<name>French Toast</name>
<price>$4.50</price>
<description>Thick slices made from our homemade sourdough bread</description>
<calories>600</calories>
</food>

<food>
<name>Homestyle Breakfast</name>
<price>$6.95</price>
<description>Two eggs, bacon or sausage, toast, and our ever-popular hash browns</description>
<calories>950</calories>
</food>

</breakfast_menu>

Also there's an XQuery. XQuery is to XML what SQL is to databases. XQuery was designed to query XML data. XQuery is the language for
querying XML data XQuery for XML is like SQL for databases XQuery is built on XPath expressions XQuery is supported by all major
databases XQuery is a W3C Recommendation

XQuery is a language for finding and extracting elements and attributes from XML documents. XQuery 1.0 and XPath 2.0 share the same data
model and support the same functions and operators. If you have already studied XPath you will have no problems with understanding
XQuery. Xquery also can be used in Extract information to use in a Web Service, Generate summary reports, Transform XML data to XHTML,
Search Web documents for relevant information. XQuery is compatible with several W3C standards, such as XML, Namespaces, XSLT, XPath, and
XML Schema. XQuery 1.0 became a W3C Recommendation in 2007.

Here also is an example of Xquery
for $x in doc("books.xml")/bookstore/book
where $x/price>30
order by $x/title
return $x/title

There's no end with X, because there's an Xlink. XLink is used to create hyperlinks in XML documents, any element in an XML document can
behave as a link, the links can be defined outside the linked files, XLink is a W3C Recommendation. But, there is no browser support for
XLink in XML documents. We also learned that Xlink has a attributes reference. Next with this is Xpoint, XPointer allows links to point
to specific parts of an XML document, XPointer uses XPath expressions to navigate in the XML document, XPointer is a W3C Recommendation.
Same with Xlinks, There is no browser support for XPointer. But XPointer is used in other XML languages.

Here's the example of Xlinks
<?xml version="1.0" encoding="UTF-8"?>

<bookstore xmlns:xlink="http://www.w3.org/1999/xlink">

<book title="Harry Potter">
  <description
  xlink:type="simple"
  xlink:href="/images/HPotter.gif"
  xlink:show="new">
  As his fifth year at Hogwarts School of Witchcraft and
  Wizardry approaches, 15-year-old Harry Potter is.......
  </description>
</book>

<book title="XQuery Kick Start">
  <description
  xlink:type="simple"
  xlink:href="/images/XQuery.gif"
  xlink:show="new">
  XQuery Kick Start delivers a concise introduction
  to the XQuery standard.......
  </description>
</book>

</bookstore>

And also an example of Xpoints
<?xml version="1.0" encoding="UTF-8"?>

<dogbreeds>

<dog breed="Rottweiler" id="Rottweiler">
  <picture url="https://dog.com/rottweiler.gif" />
  <history>The Rottweiler's ancestors were probably Roman
  drover dogs.....</history>
  <temperament>Confident, bold, alert and imposing, the Rottweiler
  is a popular choice for its ability to protect....</temperament>
</dog>

<dog breed="FCRetriever" id="FCRetriever">
  <picture url="https://dog.com/fcretriever.gif" />
  <history>One of the earliest uses of retrieving dogs was to
  help fishermen retrieve fish from the water....</history>
  <temperament>The flat-coated retriever is a sweet, exuberant,
  lively dog that loves to play and retrieve....</temperament>
</dog>

</dogbreeds>


for syntax checking, we learned that we used XML Validators. it's find the error, notice your error by using XML syntax rules. Because
errors in XML documents will stop your XML applications. A "well formed" XML document is not the same as a "valid" XML document. A
"valid" XML document must be well formed. In addition, it must conform to a document type definition. There are two type of document type
definition which is the DTD ( Document Type Definition ) and XML Schema. A document type definition defines the rules and the legal
elements and attributes for an XML document.

Additionally an XML Documents with correct syntax is called well-formed.

Finally, XML files are plain text files just like HTML files. XML can easily be stored and generated by a standard web server.








