# JavaScript Basics

## Simple alert
<p>This example shows a simple alert box when a button is clicked</p>

<button onclick="myFunction()">Try it</button>
<script>
function myFunction() {
  alert("Hello! I am an alert box!");
}
</script>

<p><a href="https://www.w3schools.com/jsref/met_win_alert.asp">Reference for this script</a></p>
  
## Write something into a document
<p>This example shows how JS can manipulate text on a document</p>

<p id="demo">Click the button to change the text in this paragraph.</p>
<button onclick="myFunction()">Try it</button>

<script>
function myFunction() {
  document.getElementById("demo").innerHTML = "Hello World";
}
</script>

<p>The script you need:</p>
<code>
<p id="demo">Click the button to change the text in this paragraph.</p>
<button onclick="myFunction()">Try it</button>

<script>
function myFunction() {
  document.getElementById("demo").innerHTML = "Hello World";
}
</script>

</code>

<p><a href="https://www.w3schools.com/jsref/met_document_getelementbyid.asp">Reference for this script</a></p>


## Extend the above to get input and output it to the document
<p>This example shows how JS can take user input and join it to another text and output it.</p>

<p>Enter your name: <input type="text" id="inputName"> 
<button onclick="myFunction()">Try it</button>
<p id="output"></p>

<script>
function myFunction() {
  var yourName = document.getElementById("inputName").value;
  document.getElementById("output").innerHTML = "Hello " + yourName;
}
</script>
