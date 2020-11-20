
<style>
.iframe-container {
  position: relative;
  width: 100%;
  overflow: hidden;
  padding-top: 66.66%; /* 3:2 Aspect Ratio */
}

.responsive-iframe {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  width: 100%;
  height: 100%;
  border: none;
}
</style>

<h1>Embedded Language Game</h1>
<p>This is an example of two games for practising English-Spanish phrases.</p>
<p>The language content of these games can be created by you, on the [Cram website](https://www.cram.com/), so try this out and if you like what you see, create a Cram account and make your own!</p>
<p>There are two games types (matching items and a simple shooter game).</p>
<p>Select the game type from the dropdown to try it:</p>
<select name="" id="list" onclick="loadFrame()">
    <option value="shooter">Phrases Shooter Game</option>
    <option value="matching">Phrases matching game</option>
  </select>
  <br><br>
    
  <div class="iframe-container">
    <iframe class="responsive-iframe" id="ifrm" src="https://www.cram.com/flashcards/games/jewel/english-spanish-translations-11085554">
  <p>Your browser does not support iframes.</p>
  </iframe>
  </div>
  
   <p style="font-size:90%;">This <a href="https://benmarshall.me/responsive-iframes/">responsive iframe</a> is courtesy of Ben Marshall's demonstration of <a href="https://benmarshall.me/resize-videos-proportionally-intrinsic-ratios/">intrinsic ratio technique</a>.</p>


<script>
function loadFrame() {
  let e = document.getElementById("list");
  let url = e.options[e.selectedIndex].value;
  
  if (url == "shooter"){
  let gameUrl = "https://www.cram.com/flashcards/games/stellar-speller/english-spanish-translations-11085554";
  document.getElementById("ifrm").src = gameUrl;
  }
  
  if (url == "matching"){
  let gameUrl = "https://www.cram.com/flashcards/games/jewel/english-spanish-translations-11085554";
  document.getElementById("ifrm").src = gameUrl;
  }
  
}
</script>
