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

Key XMLHttpRequest properties include:

onreadystatechange: Defines a function to handle state changes.

readyState: Tracks request status (0-4).

responseText/responseXML: Retrieves server responses.

status/statusText: Provides request status (e.g., 200: "OK", 404: "Not Found").

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

  
