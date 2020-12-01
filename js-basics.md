# JavaScript Basics

## Simple alert
<p>This example shows a simple alert box when a button is clicked</p>

<button onclick="test1()">Try it</button>
<script>
function test1() {
  alert("Hello! I am an alert box!");
}
</script>

<p>The code</p>



```
<button onclick="test1()">Try it</button>
<script>
function test1() {
  alert("Hello! I am an alert box!");
}
</script>
```


<p><a href="https://www.w3schools.com/jsref/met_win_alert.asp">Reference for this script</a></p>
  
## Write something into a document
<p>This example shows how JS can manipulate text on a document</p>

<p id="demo1">Click the button to change the text in this paragraph.</p>
<button onclick="test2()">Try it</button>

<script>
function test2() {
  document.getElementById("demo1").innerHTML = "Hello World! How are you today?";
}
</script>

<p>The script you need:</p>


<p><a href="https://www.w3schools.com/jsref/met_document_getelementbyid.asp">Reference for this script</a></p>


## Extend the above to get input and output it to the document
<p>This example shows how JS can take user input and join it to another text and output it.</p>

<p>Enter your name: <input type="text" id="inputName"> 
<button onclick="test3()">Try it</button>
<p id="output1"></p>

<script>
function test3() {
  var yourName = document.getElementById("inputName").value;
  document.getElementById("output1").innerHTML = "Hello " + yourName;
}
</script>

<p><strong>But what happens if the user doesn't enter a name?</strong></p>
<p>Yes, that's right, you get a message saying only 'Hello' with no name.</p>
<p>We can solve this by making sure the user enters a name:</p>

<p>Enter your name: <input type="text" id="inputName2"> 
<button onclick="test4()">Try it</button>
<p id="output2"></p>

<script>
function test4() {
  var yourName = document.getElementById("inputName2").value;
  if(!yourName){
  alert("Please enter your name!");
  }
  else {
  document.getElementById("output2").innerHTML = "Hello " + yourName;
  }
}
</script>


