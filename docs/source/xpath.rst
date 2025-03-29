Welcome to XPATH!
#################
XPath, a core component of XSLT, is a W3C-recommended language for navigating XML documents using path expressions. It includes over 200 built-in functions for string, numeric, and node manipulation. XPath is widely supported in languages like JavaScript, Python, and Java, enhancing XML processing across various applications.

XPath Nodes
------------
XPath defines XML documents as trees of nodes, including elements, attributes, text, and root nodes. Nodes have relationships like parent, child, sibling, ancestor, and descendant. XPath allows structured navigation of XML data, making it essential for XML querying and transformation in various applications.

**example: books.xml**

  <?xml version="1.0" encoding="UTF-8"?>

  <bookstore>

    <book>

      <title lang="en">Harry Potter</title>
      <author>J.K. Rowling</author>
      <year>2005</year>
      <price>29.99</price>

    </book>

    <book>

      <title lang="en">The Hobbit</title>
      <author>J.R.R. Tolkien</author>
      <year>1937</year>
      <price>19.99</price>

    </book>

  </bookstore>

XPath Syntax
-------------
XPath uses path expressions to navigate XML documents and select nodes efficiently. It allows selecting elements, attributes, and specific values using expressions like `/` for root selection, `//` for any matching nodes, and `@` for attributes. Predicates `[ ]` refine searches, enabling precise queries like selecting the first or last element. XPath supports wildcards (`*`, `@*`, `node()`) for flexible selection of unknown elements. The `|` operator allows combining multiple paths. XPath is crucial for XML querying and transformation, providing a structured approach to extracting and manipulating data across various applications, including JavaScript, Java, PHP, and databases.

**example:**

  <?xml version="1.0" encoding="UTF-8"?>

  <bookstore>

      <book>

          <title lang="en">Harry Potter</title>
          <author>J.K. Rowling</author>
          <price>29.99</price>

      </book>

      <book>

          <title lang="en">Learning XML</title>
          <author>Erik T. Ray</author>
          <price>39.95</price>

      </book>

  </bookstore>


  
