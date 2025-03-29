Welcome to XML AJAX!
=====================

**AJAX** (Asynchronous JavaScript and XML) is a web development technique that enables web pages to update content without reloading. It allows fetching, receiving, and sending data in the background, improving user experience. AJAX is not a programming language but combines JavaScript, HTML DOM, and the built-in XMLHttpRequest object for server communication. It can handle data as XML, plain text, or JSON. The process involves an event triggering a request, server processing, and JavaScript updating the webpage asynchronously.

**AJAX Example:**

  <!DOCTYPE html>
  <html>
  <body>

  <div id="demo">
    <h2>Let AJAX change this text</h2>
    <button type="button" onclick="loadDoc()">Change Content</button>
  </div>

  </body>
  </html>

**AJAX - The XMLHttpRequest Object**
------------------------------------
Its core component is the XMLHttpRequest object, which allows seamless data exchange with a server. All modern browsers support this object.

To create an XMLHttpRequest object, use:

  var xhttp = new XMLHttpRequest();

This object interacts with the server using methods such as open() (to set request parameters) and send() (to send the request). Requests can be GET or POST, and authentication details can be included if needed.

Security restrictions prevent cross-domain requests, meaning the web page and requested file must be on the same server.

**Key XMLHttpRequest properties include:**

- onreadystatechange: Defines a function to handle state changes.

- readyState: Tracks request status (0-4).

- responseText/responseXML: Retrieves server responses.

- status/statusText: Provides request status (e.g., 200: "OK", 404: "Not Found").

**AJAX - Send a Request To a Server**
-------------------------------------
The **XMLHttpRequest** object enables web pages to communicate with a server without reloading. To send a request, the **open()** method specifies the request type (GET or POST), the URL, and whether it is asynchronous, while the **send()** method transmits the request. **GET** requests are simpler and faster but may return cached data, whereas **POST** is used for larger data transfers, database updates, or secure user input handling. When using POST, an HTTP header must be set with **setRequestHeader()** before sending data. AJAX requests should typically be asynchronous (**async = true**) to prevent page freezing, allowing scripts to execute while waiting for a response. Synchronous requests (**async = false**) block script execution until the server responds and are discouraged due to performance issues. To handle server responses, the **onreadystatechange** property defines a function that executes when the request state changes. When **readyState** reaches 4 and **status** is 200, the response can be processed and displayed. AJAX is widely used in modern web development to create dynamic and interactive applications by enabling real-time data updates without requiring full page reloads.

  // Create an XMLHttpRequest object
  var xhttp = new XMLHttpRequest();

  // Define the function to execute when the response is received
  xhttp.onreadystatechange = function() {
    if (this.readyState == 4 && this.status == 200) {
      document.getElementById("demo").innerHTML = this.responseText;
    }
  };

  // Open a GET request to retrieve data from the server
  xhttp.open("GET", "data.txt", true);

  // Send the request
  xhttp.send();

**AJAX - Server Response**
-------------------------
The **onreadystatechange** property defines a function that executes when the **readyState** of an **XMLHttpRequest** changes. The **readyState** has five values (0-4), where 4 indicates the response is complete. The **status** property provides HTTP status codes, such as **200 (OK)** or **404 (Not Found)**. The **responseText** property retrieves data as a string, while **responseXML** returns it as an XML DOM object. Callback functions can handle multiple AJAX tasks efficiently. Methods like **getResponseHeader()** and **getAllResponseHeaders()** retrieve server response headers. These features allow AJAX to fetch and display data dynamically, enhancing web application interactivity without page reloads.

**Example: Handling AJAX Response Efficiently**
  
  function loadDoc(url, callback) {
    var xhttp = new XMLHttpRequest();
    
    xhttp.onreadystatechange = function() {
        if (this.readyState == 4 && this.status == 200) {
            callback(this); // Calls the specified callback function
        }
    };

    xhttp.open("GET", url, true);
    xhttp.send();
}

// Callback function to handle responseText
function handleTextResponse(xhttp) {
    document.getElementById("demo").innerHTML = xhttp.responseText;
}

// Callback function to handle responseXML
  function handleXMLResponse(xhttp) {
      var xmlDoc = xhttp.responseXML;
      var txt = "";
      var elements = xmlDoc.getElementsByTagName("ARTIST");
    
      for (var i = 0; i < elements.length; i++) {
          txt += elements[i].childNodes[0].nodeValue + "<br>";
      }

      document.getElementById("demo").innerHTML = txt;
  }

  // Load a text response
  loadDoc("ajax_info.txt", handleTextResponse);

  // Load an XML response
  loadDoc("cd_catalog.xml", handleXMLResponse);

**The XML File**
----------------
AJAX enables web pages to fetch and display XML data dynamically without reloading. The loadDoc() function creates an XMLHttpRequest object, retrieves the XML file, and triggers a callback function when the response is ready. The myFunction() function processes the XML data, extracts elements like TITLE and ARTIST, and updates the HTML table dynamically.

**example:**

  function loadDoc() {
      var xhttp = new XMLHttpRequest();
      xhttp.onreadystatechange = function() {
          if (this.readyState == 4 && this.status == 200) {
              myFunction(this);
          }
      };
      xhttp.open("GET", "cd_catalog.xml", true);
      xhttp.send();
  }

  function myFunction(xml) {
      var i;
      var xmlDoc = xml.responseXML;
      var table = "<tr><th>Title</th><th>Artist</th></tr>";
      var x = xmlDoc.getElementsByTagName("CD");

      for (i = 0; i < x.length; i++) {
          table += "<tr><td>" +
          x[i].getElementsByTagName("TITLE")[0].childNodes[0].nodeValue +
          "</td><td>" +
          x[i].getElementsByTagName("ARTIST")[0].childNodes[0].nodeValue +
          "</td></tr>";
      }

      document.getElementById("demo").innerHTML = table;
  }

**AJAX PHP**
------------
AJAX with PHP enhances interactivity by dynamically retrieving data from the server without page reloads. When a user types in an input field, the showHint() function sends an AJAX request to a PHP file (gethint.php), which searches an array for matching names and returns suggestions in real-time.

**example**

  <!DOCTYPE html>
  <html>
  <head>
  <script>
  function showHint(str) {
      if (str.length == 0) {
          document.getElementById("txtHint").innerHTML = "";
          return;
      } else {
          var xmlhttp = new XMLHttpRequest();
          xmlhttp.onreadystatechange = function() {
              if (this.readyState == 4 && this.status == 200) {
                  document.getElementById("txtHint").innerHTML = this.responseText;
              }
          };
          xmlhttp.open("GET", "gethint.php?q=" + str, true);
          xmlhttp.send();
      }
  }
  </script>
  </head>
  <body>
  <p><b>Start typing a name:</b></p>
  <form>
      First name: <input type="text" onkeyup="showHint(this.value)">
  </form>
  <p>Suggestions: <span id="txtHint"></span></p>
  </body>
  </html>

**AJAX ASP**
------------
AJAX with ASP enables real-time communication between a web page and a server without refreshing. When a user types in an input field, the **showHint()** function sends an AJAX request to **gethint.asp**, which searches a predefined array for matching names and returns suggestions dynamically, improving user experience and interactivity.

**example:**

- html-front-end

  <html>
  <head>
  <script>
  function showHint(str) {
      if (str.length == 0) {
          document.getElementById("txtHint").innerHTML = "";
          return;
      } else {
          var xmlhttp = new XMLHttpRequest();
          xmlhttp.onreadystatechange = function() {
              if (this.readyState == 4 && this.status == 200) {
                  document.getElementById("txtHint").innerHTML = this.responseText;
              }
          };
          xmlhttp.open("GET", "gethint.asp?q=" + str, true);
          xmlhttp.send();
      }
  }
  </script>
  </head>
  <body>

  <p><b>Start typing a name in the input field below:</b></p>
  <form>
  First name: <input type="text" onkeyup="showHint(this.value)">
  </form>
  <p>Suggestions: <span id="txtHint"></span></p>
  </body>
  </html>
- **ASP Back-end (gethint.asp)**

  <%
  response.expires=-1
  dim a(10)
  a(1)="Anna"
  a(2)="Brittany"
  a(3)="Cinderella"
  a(4)="Diana"
  a(5)="Eva"
  a(6)="Fiona"
  a(7)="Gunda"
  a(8)="Hege"
  a(9)="Inga"
  a(10)="Johanna"

  ' Get the query parameter from the URL
  q=ucase(request.querystring("q"))

  ' Look up all hints from array if q is not empty
  if len(q) > 0 then
    hint=""
    for i=1 to 10
      if q=ucase(mid(a(i),1,len(q))) then
        if hint="" then
          hint=a(i)
        else
          hint=hint & ", " & a(i)
        end if
      end if
    next
  end if

  ' Output "no suggestion" if no hint was found
  if hint="" then
    response.write("No suggestion")
  else
    response.write(hint)
  end if
  %>

AJAX Database 
------------------
AJAX retrieves database data without page reloads. When a user selects a customer, showCustomer() sends an AJAX request to getcustomer.php, which queries the database and returns customer details dynamically in an HTML table, enhancing interactivity.

**example: AJAX Request**

  <!DOCTYPE html>
  <html>
  <head>
  <script>
  function showCustomer(str) {
      if (str == "") {
          document.getElementById("txtHint").innerHTML = "";
          return;
       }
      var xhttp = new XMLHttpRequest();
      xhttp.onreadystatechange = function() {
          if (this.readyState == 4 && this.status == 200) {
              document.getElementById("txtHint").innerHTML = this.responseText;
          }
      };
      xhttp.open("GET", "getcustomer.php?q=" + str, true);
      xhttp.send();
  }
  </script>
  </head>
  <body>

  <h2>Select a Customer:</h2>
  <select onchange="showCustomer(this.value)">
      <option value="">Select a customer</option>
      <option value="1">Customer 1</option>
      <option value="2">Customer 2</option>
      <option value="3">Customer 3</option>
  </select>

  <h3>Customer Info:</h3>
  <div id="txtHint">Customer details will be displayed here...</div>

  </body>
  </html>

