<h1>JavaScript Random Text</h1>
<p>This page demonstrates how you can use JavaScript to display a random text.</p>
<p>The random text is drawn from a list of text items (in this case idioms) and displayed on the page.</p>
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

function loadQuote() {
    var idiomNo = Math.floor(Math.random() * (idioms.length));
    //alert(quotes[quoteNo]);
    document.getElementById("quote").innerHTML = "<dt>" + idioms[idiomNo] + "</dt>" + "<dd>" + examples[idiomNo] + "</dd>"
}
loadQuote();
</script>
