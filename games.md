
<style>
.iframe-container {
  position: relative;
  overflow: hidden;
  width: 100%;
  padding-top: 56.25%; /* 16:9 Aspect Ratio (divide 9 by 16 = 0.5625) *
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
<p>The language content of these games can be created by you, on the <a href="https://www.cram.com/">Cram website</a>, so try this out and if you like what you see, create a Cram account and make your own!</p>

<p>There are two games types (matching items and a simple shooter game).</p>

<p>Select the game type from the dropdown to try it:  
  <select name="" id="list" onclick="loadFrame()">
    <option value="shooter">Phrases Shooter Game</option>
    <option value="matching">Phrases matching game</option>
  </select>
</p>

    
  <div class="iframe-container">
<iframe class="responsive-iframe" id="ifrm" src="https://www.cram.com/flashcards/games/jewel/english-spanish-translations-11085554">
  <p>Your browser does not support iframes.</p>
  </iframe>
  </div>
  
<p><a href="https://raw.githubusercontent.com/martinbarge/templatetest/main/games.md">Get the code for this page.</a></p>

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
