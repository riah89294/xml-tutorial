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
