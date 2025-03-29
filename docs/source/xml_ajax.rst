Welcome to XML AJAX!
####################
AJAX (Asynchronous JavaScript and XML) is a web development technique that enables web pages to update content without reloading. It allows fetching, receiving, and sending data in the background, improving user experience. AJAX is not a programming language but combines JavaScript, HTML DOM, and the built-in XMLHttpRequest object for server communication. It can handle data as XML, plain text, or JSON. The process involves an event triggering a request, server processing, and JavaScript updating the webpage asynchronously.
AJAX Example:
<!-- This is an example of using AJAX to change content dynamically -->
<!DOCTYPE html>
<html>
<body>

    <div id="demo">
        <h2>Let AJAX change this text</h2>
        <!-- Button triggers AJAX function -->
        <button type="button" onclick="loadDoc()">Change Content</button>
    </div>

</body>
</html>

AJAX - The XMLHttpRequest Object

The `XMLHttpRequest` object allows web pages to fetch and send data asynchronously without reloading. It is supported in all modern browsers and enables real-time content updates.  

To create an `XMLHttpRequest` object:  
```javascript
var xhttp = new XMLHttpRequest();
```  

   **Fetching Data Asynchronously  
   ```javascript
   var xhttp = new XMLHttpRequest();
   xhttp.onreadystatechange = function() {
     if (this.readyState == 4 && this.status == 200) {
         document.getElementById("demo").innerHTML = this.responseText;
     }
   };
xhttp.open("GET", "ajax_info.txt", true);
xhttp.send();
```  
This retrieves data from `ajax_info.txt` and updates the webpage dynamically.  

    **Methods of `XMLHttpRequest` ** 
    - `open(method, url, async)`: Initializes a request  
    - `send()`: Sends the request  
    - `setRequestHeader(header, value)`: Sets headers for requests  

    **Sending Data via POST** 
    ```javascript
    var xhttp = new XMLHttpRequest();
    xhttp.open("POST", "submit_data.php", true);
    xhttp.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
    xhttp.send("name=John&age=30");
    ```  

    Cross-domain AJAX requests require `Access-Control-Allow-Origin` in the server response:  
    ```php
    header("Access-Control-Allow-Origin: *");
    header("Content-Type: application/json");
    echo json_encode(["message" => "Hello from the server!"]);
    ```  
- **XMLHttpRequest: Sending Requests to a Server**
-----------------------------------------------------
  The `XMLHttpRequest` object is used to send and receive data from a server without reloading the page. The `open(method, url, async)` method initializes a request, specifying the request type (`GET` or `POST`), target URL, and whether it is asynchronous (`true`) or synchronous (`false`). The `send()` method then transmits the request.

**GET Requests**
- Faster and simpler but may return cached data.
- To prevent caching, append a unique identifier to the URL.
- Data can be sent via URL parameters.

**POST Requests**
- Used when caching is not an option, large data needs to be sent, or user input is involved.
- The `setRequestHeader()` method sets headers.
- Data is sent within the `send()` method.

**Asynchronous Requests (`async = true`)**
- Allows JavaScript to execute other tasks while waiting for a response.
- The `onreadystatechange` property defines a function to process the response when complete.

**Synchronous Requests (`async = false`)**
- Waits for the server response before executing further code.
- Discouraged as it may cause applications to freeze.
- Being phased out in modern web standards.

- **AJAX - Server Response**
-------------------------------
The `onreadystatechange` property in `XMLHttpRequest` defines a function that executes whenever the `readyState` changes. The `readyState` property indicates the request's status:

- **0**: Request not initialized
- **1**: Server connection established
- **2**: Request received
- **3**: Processing request
- **4**: Request finished and response is ready

The `status` property provides HTTP response codes:

- **200**: OK
- **403**: Forbidden
- **404**: Not Found

When `readyState` is `4` and `status` is `200`, the response is ready.

Callback Function Usage
-----------------------
A callback function efficiently handles multiple AJAX requests. The `loadDoc(url, cFunction)` function sends an AJAX request and calls a specified callback function when the response is ready.

Server Response Properties
--------------------------
- **responseText**: Returns the response as a string.
- **responseXML**: Parses the response as an XML DOM object.

Server Response Methods
-----------------------
- **getResponseHeader(header)**: Retrieves a specific response header.
- **getAllResponseHeaders()**: Retrieves all response headers.

These methods allow efficient data extraction from the server. The `onreadystatechange` event triggers multiple times, corresponding to changes in `readyState`.

Example Usage
-------------
Your provided example demonstrates these concepts:

.. code-block:: javascript

    var xhttp = new XMLHttpRequest();
    xhttp.onreadystatechange = function() {
        if (this.readyState == 4 && this.status == 200) {
            document.getElementById("demo").innerHTML = this.responseText;
        }
    };
    xhttp.open("GET", "ajax_info.txt", true);
    xhttp.send();
