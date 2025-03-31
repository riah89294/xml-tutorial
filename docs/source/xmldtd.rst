XML DTD LEARNING SUMMARY
 I learn DTD defines the structure, elements, and attributes allowed in an XML document and It ensures that XML data follows a specific format and is well-formed and valid.
This is a uses DTD
•	Validates XML documents.
•	Provides a formal structure for data exchange.
•	Defines element hierarchy, order, and attributes.

 This a 2 Types of DTD
1.	Internal DTD
Defined within the XML document.
xml
CopyEdit
<!DOCTYPE note [
  <!ELEMENT note (to, from, message)>
  <!ELEMENT to (#PCDATA)>
  <!ELEMENT from (#PCDATA)>
  <!ELEMENT message (#PCDATA)>
]>
<note>
  <to>John</to>
  <from>Mary</from>
  <message>Hello!</message>
</note>
2.	External DTD
Stored in a separate file and linked to the XML document.
o	note.xml
xml
CopyEdit
<!DOCTYPE note SYSTEM "note.dtd">
<note>
  <to>John</to>
  <from>Mary</from>
  <message>Hello!</message>
</note>
o	note.dtd
xml
CopyEdit
<!ELEMENT note (to, from, message)>
<!ELEMENT to (#PCDATA)>
<!ELEMENT from (#PCDATA)>
<!ELEMENT message (#PCDATA)>
This is a Basic DTD Concepts
1.	ELEMENT Declaration
Defines element names and order.
xml
CopyEdit
<!ELEMENT note (to, from, message)>
2.	ATTLIST Declaration
Defines attributes and their types.
xml
CopyEdit
<!ATTLIST note type CDATA #IMPLIED>
 The Data Types:
o	#PCDATA – Parsed character data (text).
o	CDATA – Unparsed text.
o	ID – Unique identifier.
o	IDREF – Refers to another element’s ID.

Advantages of DTD:
•	Simple and easy to learn.
•	Ensures document consistency.
Limitations of DTD:
•	No support for data types.
•	Cannot handle namespaces.
•	Less flexible than XML Schema (XSD).
•	
LEARNING 
 I learned XML  DTDis widely used to store and exchange structured data. To ensure that an XML document follows a specific format, Document Type Definition (DTD) is used. DTD defines the structure, elements, and attributes allowed in an XML document, making it easier to validate and maintain consistency across systems.
