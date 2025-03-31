
  Types of XSD Data Types
XSD offers two main types of data types:
 The Simple Data Types
•	Used for elements and attributes that contain only text (no child elements or attributes).
EXAMPLE 
Common Simple Data Types:
Data Type	Description	Example
string	Text content	<name>John</name>
integer	Whole numbers	<age>25</age>
decimal	Decimal numbers	<price>19.99</price>
boolean	True/false values	<active>true</active>
date	Date in YYYY-MM-DD format	<dob>2024-03-30</dob>
time	Time in HH:MM:SS format	<start>12:30:00</start>
dateTime	Date and time together	<timestamp>2024-03-30T12:30:00</timestamp>
float	Floating-point numbers	<temp>36.6</temp>
double	Double-precision floating-point	<value>1.234567</value>

Complex Data Types
•	Used when elements can contain child elements, attributes, or a combination of both.
Types of Complex Data:
•	<xs:complexType> – Contains child elements.
•	<xs:sequence> – Child elements appear in order.
•	<xs:all> – Child elements can appear in any order.
•	<xs:choice> – Only one of the child elements can appear.
xml
CopyEdit
<xs:element name="person">
  <xs:complexType>
    <xs:sequence>
      <xs:element name="name" type="xs:string"/>
      <xs:element name="age" type="xs:integer"/>
      <xs:element name="email" type="xs:string"/>
    </xs:sequence>
  </xs:complexType>
</xs:element>
The Concept Data Types
1.	Defining Elements
xml
CopyEdit
<xs:element name="age" type="xs:integer"/>
2.	Defining Attributes
xml
CopyEdit
<xs:attribute name="id" type="xs:string" use="required"/>
3.	Complex Type with Attributes
xml
CopyEdit
<xs:complexType>
  <xs:attribute name="status" type="xs:string" use="optional"/>
</xs:complexType>


Advantages of XSD:
•	Supports data types and namespaces.
•	Enables strict validation and consistency.



LEARNING SUMMARY
 I learned the XSD data types is to ensure that the content of XML documents follows the correct data format. Data types in XSD define the kind of data an element or attribute can contain, such as text, numbers, dates, and more. By using data types, XML documents can be validated to ensure that they adhere to specific rules and constraints, preventing errors during data processing.



