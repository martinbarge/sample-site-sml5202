# JavaScript Examples

## Manipulating Browser windows

<p>Hi! In this post I want to show you two methods for opening pop-up windows using the powerful scripting language called JavaScript.</p>

## Example 1

<p>Here is the simplest form of <b>pop-up window</b>. Click the link below to see the window in action.</p>
<a href="javascript:void(0)" onclick="window.open('http://www.webdevelopersnotes.com/tutorials/javascript/creating_opening_new_window_pop_ups_javascript.php3','welcome','width=500,height=200,scrollbars=1')">Open a new window</a><br>
<hr>

## Example 2
<p>This is a slightly more sophisticated pop-up. Firstly, it opens in the centre of the screen. Secondly, it re-focuses (pops-up) even when the window is minimised. Try it and see!</p>

<script>

function popup_special(url)
{
var width  = screen.width/2; 
var height = screen.height/2; 
var left   = (screen.width  - width)/2; var top    = (screen.height - height)/2; 
var params = 'width='+width+', height='+height; params += ', top='+top+', left='+left; 
params += ', directories=no'; params += ', location=no'; params += ', menubar=no'; 
params += ', resizable=no'; params += ', scrollbars=no'; params += ', status=no'; 
params += ', toolbar=no';
newwin=window.open(url,'windowname5', params); 
if (window.focus) {
newwin.focus()
} 
return false;
}
</script>
<p>
<a href="javascript: void(0)" onclick="popup_special('http://en.wikipedia.org/wiki/JavaScript')">Open a centred popup window</a><br>
</p>

## Variations

<p>I can now write a piece of text and add some vocabulary glosses. E.G.:</p> 
<p>A <a href="javascript: void(0)" onclick="popup_special('http://wordnetweb.princeton.edu/perl/webwn?s=glossary')">glossary</a> can be very useful in a text.</p>

### Acknowledgement:
<p>The JavaScript for these examples is adapted from: <a href="http://javascript-array.com/scripts/window_open/" target="_blank" ,="">javascript-array.com</a>.</p>
