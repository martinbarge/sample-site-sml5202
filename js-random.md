<h1>JavaScript Random Text Examples</h1>
<p>This page demonstrates how you can use JavaScript to display randomised text.</p>

<h2>Example 1</h2>
<p>This example demonstrates a simple random(ish) sentence generator, using subject + verb + adverb patterns.</p>
<p>Clicking the button below will display a list of subjects (names and pronouns) followed by a verb and adverb. Each time you click the button, the verbs and adverbs will vary for each subject (within the limit of the number of available verbs (5)). </p>
<p>Examine the code below to see how it's done:</p>

<button onclick="makeSentence()">Make sentences</button>
<p>Random sentences will appear below here:</p>
<p id="demo"></p>

<script>
function makeSentence() {

var person = {
    names: [ "Brian", "Betty", "Fiona", "Freddy", "Mini", "Marvin", "Alice", "Bob", "Jane", "Arthur", "Vincent", "Amy", "He", "She" ],
    verbs: [ "speaks", "eats", "runs", "walks", "drinks" ],
    adverbs: ["slowly", "quickly", "nicely", "noisily", "a lot", "a little", "rarely" ]
   
};
  
var i;
var text = "";
for (i = 0; i < person.names.length; i++) {

  name = person.names[i];
  verb = person.verbs[Math.floor(Math.random() * person.verbs.length)];
  adv = person.adverbs[Math.floor(Math.random() * person.adverbs.length)]; 
  text += name + " " + verb + " " + adv + "<br>";
  document.getElementById("demo").innerHTML = text;
 }  
}
</script>

<h3>The Code</h3>

```
<script>
function makeSentence() {

var person = {
    names: [ "Brian", "Betty", "Fiona", "Freddy", "Mini", "Marvin", "Alice", "Bob", "Jane", "Arthur", "Vincent", "Amy", "He", "She" ],
    verbs: [ "speaks", "eats", "runs", "walks", "drinks" ],
    adverbs: ["slowly", "quickly", "nicely", "noisily", "a lot", "a little", "rarely" ]
   
};
  
var i;
var text = "";
for (i = 0; i < person.names.length; i++) {

  name = person.names[i];
  verb = person.verbs[Math.floor(Math.random() * person.verbs.length)];
  adv = person.adverbs[Math.floor(Math.random() * person.adverbs.length)]; 
  text += name + " " + verb + " " + adv + "<br>";
  document.getElementById("demo").innerHTML = text;
 }  
}
</script>
```

<hr>

<h2>Example 2</h2>
<p>In this example the random text is again drawn from a list of text items (in this case idioms) and displayed on the page.</p>
<p>In JavaScript the list of items is a special type of variable known as an 'array'. JavaScript can then access the items in the array, and depending how it's coded, can manipulate the items as you wish.</p>
<p>Click the button or refresh the page to see another sentence displayed.</p>

<h2>Random colour idiom</h2>
<dl id="quote"></dl>
<!--<script src="script.js"></script>-->
<button onclick="loadQuote()">See another random idiom</button>
<hr>

<script>
var idioms = [ 
'Once in a blue moon = very rarely.', 
'Tickled pink = to be extremely pleased.', 
'Caught red-handed = to catch someone in the act of doing something.',    
'White lie = a small lie that is told to be polite or avoid hurting someone’s feelings.',
'Feel blue = Be depressed or sad. The use of blue to mean “sad” dates from the late 1300s.',
'See red = Become very angry suddenly.'
];

var examples = [
'Example: <i>Once in a blue moon you will see that mean professor smile.</i>', 
'Example: <i>Your grandma was tickled pink that you called on her birthday!</i>', 
'Example: <i>He was caught red-handed while stealing those biscuits.</i>',
'Example: <i>I didn’t like her dress, but I told a white lie because I didn’t want to offend her.</i>',
'Example: <i>I was really feeling blue after she told me she was leaving.</i>',
'Example: <i>The thought of Piers with Nicole made her see red.</i>'

];

var quoteNo;
var idiomNo;
function loadQuote() {
    idiomNo = Math.floor(Math.random() * (idioms.length));
    if(idiomNo !== quoteNo) {
    //alert(quotes[quoteNo]);
    	document.getElementById("quote").innerHTML = "<dt>" + idioms[idiomNo] + "</dt>" + "<dd>" + examples[idiomNo] + "</dd>";
   	quoteNo = idiomNo;
    	return quoteNo;
    	}
    	else {
    	loadQuote();
    	}
	}
loadQuote();
</script>

<h3>The code:</h3>

```
<script>
var idioms = [ 
'Once in a blue moon = very rarely.', 
'Tickled pink = to be extremely pleased.', 
'Caught red-handed = to catch someone in the act of doing something.',    
'White lie = a small lie that is told to be polite or avoid hurting someone’s feelings.',
'Feel blue = Be depressed or sad. The use of blue to mean “sad” dates from the late 1300s.',
'See red = Become very angry suddenly.'
];

var examples = [
'Example: <i>Once in a blue moon you will see that mean professor smile.</i>', 
'Example: <i>Your grandma was tickled pink that you called on her birthday!</i>', 
'Example: <i>He was caught red-handed while stealing those biscuits.</i>',
'Example: <i>I didn’t like her dress, but I told a white lie because I didn’t want to offend her.</i>',
'Example: <i>I was really feeling blue after she told me she was leaving.</i>',
'Example: <i>The thought of Piers with Nicole made her see red.</i>'

];

var quoteNo;
var idiomNo;
function loadQuote() {
    idiomNo = Math.floor(Math.random() * (idioms.length));
    if(idiomNo !== quoteNo) {
    //alert(quotes[quoteNo]);
    	document.getElementById("quote").innerHTML = "<dt>" + idioms[idiomNo] + "</dt>" + "<dd>" + examples[idiomNo] + "</dd>";
   	quoteNo = idiomNo;
    	return quoteNo;
    	}
    	else {
    	loadQuote();
    	}
	}
loadQuote();
</script>

```

<hr>
<p>That's it for this demonstration of JavaScript Arrays, loops and math functions</p>
