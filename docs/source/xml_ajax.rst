Welcome to XML AJAX!
=====================   
As we started learning about **XML AJAX**, we discovered how **Asynchronous JavaScript and XML (AJAX)** helps web pages update content without needing a full reload. **AJAX** is not a programming language but a technique that combines **JavaScript**, the **HTML DOM**, and the 
***`XMLHttpRequest`*** object to communicate with a web server in the background. This process allows websites to retrieve and send data more efficiently, making web applications more interactive and responsive.  

One of the first things we learned about **AJAX** was the *`XMLHttpRequest`* object, which plays a key role in exchanging data with a server. We practiced creating an *`XMLHttpRequest`* using *`var xhttp = new XMLHttpRequest();`* and explored how to use methods like *`open()`* and *`send()`* to make requests. We also studied the difference between **GET** and **POST** requests—**GET** is faster but might retrieve cached data, while **POST** is better for sending sensitive or larger data.  

As we progressed, we learned how **AJAX** responses work. The *`onreadystatechange`* property helps track the request’s progress, and `readyState` shows its current status. We used *`responseText`* to get plain text responses and *`responseXML`* to process XML data. By applying these concepts, we were able to change webpage content dynamically without refreshing the page.  

We also started working with **AJAX** and server-side technologies like **PHP** and **ASP**. For example, we built a simple user suggestion feature where a text input triggered an **AJAX** request to *`gethint.php`*. This PHP script searched for matching names in a list and returned suggestions in real-time. We later applied the same concept using ASP with *`gethint.asp`*, showing us how **AJAX** can work with different backend environments.  

As we deepened our understanding, we experimented with retrieving **XML** data using **AJAX**. The *`loadDoc()`* function helped us load an XML file from a server and extract its content. Using JavaScript, we displayed information from the XML, such as *`TITLE`* and *`ARTIST`*, in an **HTML** table. This approach is useful for applications like online catalogs and databases.  

Another important lesson was learning how **AJAX** interacts with databases. We practiced sending requests to *`getcustomer.php`*, which retrieved customer details from a database and displayed them instantly on a webpage. This experience showed us how **AJAX** can make websites more dynamic by providing real-time updates. We also learned about request headers and callback functions, which help manage **AJAX** responses efficiently.  

We now understand how **AJAX** improves web performance by enabling data retrieval and updates without reloading pages. This knowledge gives us a foundation for building interactive web applications, and we look forward to exploring more advanced uses of **AJAX** in the future.

Example: AJAX-Based User Search with PHP and XML
-------------------------------------------------
**HTML Frontend (index.html)**

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

  <p><b>Start typing a name in the input field below:</b></p>

  <form>

  First name: <input type="text" onkeyup="showHint(this.value)">

  </form>

  <p>Suggestions: <span id="txtHint"></span></p>

  </body>

  </html>

**The PHP File - "gethint.php"**

  <?php

  // Array with names

  $a[] = "Anna";

  $a[] = "Brittany";

  $a[] = "Cinderella";

  $a[] = "Diana";

  $a[] = "Eva";

  $a[] = "Fiona";

  $a[] = "Gunda";

  $a[] = "Hege";

  $a[] = "Inga";

  $a[] = "Johanna";

  $a[] = "Kitty";

  $a[] = "Linda";

  $a[] = "Nina";

  $a[] = "Ophelia";

  $a[] = "Petunia";

  $a[] = "Amanda";

  $a[] = "Raquel";

  $a[] = "Cindy";

  $a[] = "Doris";

  $a[] = "Eve";

  $a[] = "Evita";

  $a[] = "Sunniva";

  $a[] = "Tove";

  $a[] = "Unni";

  $a[] = "Violet";

  $a[] = "Liza";

  $a[] = "Elizabeth";

  $a[] = "Ellen";

  $a[] = "Wenche";

  $a[] = "Vicky";


  // get the q parameter from URL

  $q = $_REQUEST["q"];


  $hint = "";


  // lookup all hints from array if $q is different from ""

  if ($q !== "") {

      $q = strtolower($q);

      $len=strlen($q);

      foreach($a as $name) {

          if (stristr($q, substr($name, 0, $len))) {

              if ($hint === "") {

                  $hint = $name;

              } else {

                  $hint .= ", $name";

              }

          }

      }

  }


  // Output "no suggestion" if no hint was found or output correct values
  echo $hint === "" ? "no suggestion" : $hint;

  ?>
