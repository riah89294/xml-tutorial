Welcome to XML AJAX!
####################

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
