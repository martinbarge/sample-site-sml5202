<h1>Wikipedia Search Application</h1>
<p>This example uses JavaScript to connect to the Wikipedia API to obtain a list of Wikipedia page entries based on any search term.</p>
<p>In this example, the script calls the English version of Wikipedia. However, you can change this to a different language version of the platform. To do this you change the 'en' entries in the two following lines of code:</p>
<p><code>https://en.wikipedia.org/w/api.php?</code></p>
<p><code>https://en.wikipedia.org/wiki/${result.title}</code></p>
<p>For example, to use the French version of Wikipedia, replace en with fr</p>
<p>Type in a search term to see it work:</p>


<header class="searchForm-container">
<img src="https://image.ibb.co/e6vOFQ/wikipedia.png" alt="Wikipedia Logo">
<form class="searchForm">
        <input type="search" class="searchForm-input">
        <button type="submit" class="icon searchIcon">
          <img src="https://image.ibb.co/cpG8zk/search.png" alt="Magnifying Glass Icon">
        </button>
        <a href="" class="icon randomIcon">
          <img src="https://image.ibb.co/fR5OX5/random.png" alt="Shuffle Icon">
        </a>
      </form>
</header>
<section class="searchResults"></section>
  
<script>
  function handleSubmit(event) {
    // prevent page from reloading when form is submitted
  event.preventDefault();
  // get the value of the input field
  const input = document.querySelector('.searchForm-input').value;
  // remove whitespace from the input
  const searchQuery = input.trim();
  // call `fetchResults` and pass it the `searchQuery`
  fetchResults(searchQuery);
}

function fetchResults(searchQuery) {
	  const endpoint = `https://en.wikipedia.org/w/api.php?action=query&list=search&prop=info&inprop=url&utf8=&format=json&origin=*&srlimit=20&srsearch=${searchQuery}`;
  	fetch(endpoint)
  		.then(response => response.json())
  		.then(data => {
        const results = data.query.search;
  	  	displayResults(results);
		})
       .catch(() => document.querySelector('.searchForm-input').value = 'Please enter a search term.');
       //.catch(() => console.log('An error occured'));
}

function displayResults(results) {
  const searchResults = document.querySelector('.searchResults');
  searchResults.innerHTML = '';
  results.forEach(result => {
  const url = encodeURI(`https://en.wikipedia.org/wiki/${result.title}`);
  
  searchResults.insertAdjacentHTML('beforeend',
  
  `<div class="resultItem">
  <h3 class="resultItem-title">
  <a href="${url}" target="_blank" rel="noopener">${result.title}</a>
  </h3>
  <span class="resultItem-snippet">${result.snippet}</span><br>
  <a href="${url}" class="resultItem-link" target="_blank" rel="noopener">${url}</a>
  </div>`
  );
  
});

console.log(results);
}
const form = document.querySelector('.searchForm');
form.addEventListener('submit', handleSubmit);
</script>

<hr>
<div style="clear:both;"></div>
<div>
	<p style="font-size: 86%;">Credit: The code for this application is derived from an excellent online tutorial by Ayooluwa Isaiah, a Web Technologies Software Developer based in Lagos, Nigeria. The tutorial can be followed <a href="https://freshman.tech/wikipedia-javascript/">here</a>.</p></div>
  
<h2>The code</h2>
<p>For this application, you need to include the JavaScript on your page, and then add some styles to your stylesheet. The two code extracts are provided below.</p>
<h3>The HTML and JS code</h3>
<p>First you need to copy and paste the code below into your own page. Change the 'en' to a language of your choice.</p>

```
<header class="searchForm-container">
<img src="https://image.ibb.co/e6vOFQ/wikipedia.png" alt="Wikipedia Logo">
<form class="searchForm">
        <input type="search" class="searchForm-input">
        <button type="submit" class="icon searchIcon">
          <img src="https://image.ibb.co/cpG8zk/search.png" alt="Magnifying Glass Icon">
        </button>
        <a href="" class="icon randomIcon">
          <img src="https://image.ibb.co/fR5OX5/random.png" alt="Shuffle Icon">
        </a>
      </form>
</header>
<section class="searchResults"></section>
  
<script>
  function handleSubmit(event) {
    // prevent page from reloading when form is submitted
  event.preventDefault();
  // get the value of the input field
  const input = document.querySelector('.searchForm-input').value;
  // remove whitespace from the input
  const searchQuery = input.trim();
  // call `fetchResults` and pass it the `searchQuery`
  fetchResults(searchQuery);
}

function fetchResults(searchQuery) {
	  const endpoint = `https://en.wikipedia.org/w/api.php?action=query&list=search&prop=info&inprop=url&utf8=&format=json&origin=*&srlimit=20&srsearch=${searchQuery}`;
  	fetch(endpoint)
  		.then(response => response.json())
  		.then(data => {
        const results = data.query.search;
  	  	displayResults(results);
		})
       .catch(() => document.querySelector('.searchForm-input').value = 'Please enter a search term.');
       //.catch(() => console.log('An error occured'));
}

function displayResults(results) {
  const searchResults = document.querySelector('.searchResults');
  searchResults.innerHTML = '';
  results.forEach(result => {
  const url = encodeURI(`https://en.wikipedia.org/wiki/${result.title}`);
  
  searchResults.insertAdjacentHTML('beforeend',
  
  `<div class="resultItem">
  <h3 class="resultItem-title">
  <a href="${url}" target="_blank" rel="noopener">${result.title}</a>
  </h3>
  <span class="resultItem-snippet">${result.snippet}</span><br>
  <a href="${url}" class="resultItem-link" target="_blank" rel="noopener">${url}</a>
  </div>`
  );
  
});

console.log(results);
}
const form = document.querySelector('.searchForm');
form.addEventListener('submit', handleSubmit);
</script>

```

<h3>The CSS styles</h3>
<p>Next, copy the following to your style.scss file in your assets/css folder.</p>

```
/** Wikipedia Search Styles **/

*,
*::before,
*::after {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}

.searchForm-container {
    width: 100%;
    height: 100px;
    box-shadow: 0 1px 0 rgba(0, 0, 0, 0.15);
    display: flex;
    align-items: center;
    justify-content: left;
    /* padding-left: 50px; */
}

.searchForm {
    margin-left: 30px;
    display: flex;
    background-color: #292929;
    border: 1px solid #242424;
    border-radius: 4px;
    /*** width:50%; ***/
    width: 80%;
}

.searchForm-input {
    background-color: #f0f0f5;
    border: none;
    height: 44px;
    width: 100%;
    padding: 5px 10px;
    color: #292929;
}

.icon {
    cursor: pointer;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 44px;
    height: 44px;
    border: none;
    background-color: #292929;
}

.icon:hover {
    background-color: #1f1f1f;
}

.icon img {
    width: 22px;
    height: 22px;
}

.searchResults {
    padding: 20px 0 50px;
    margin-top: 2px;
    width: 100%;
    text-align: left;
    background-color: white;
}

.resultItem {
    opacity: 0;
    margin-bottom: 20px;
    animation: show 0.5s forwards ease-in-out;
    color: #292929;
    border-radius: 2px;
    padding: 10px;
    width: 100%;
}


.resultItem:hover {
    background-color: aliceblue;
}

.resultItem-title {
    margin-bottom: 4px;
}

.resultItem-title a {
    color: black;
    text-decoration: none;
}

.resultItem-title a:hover {
    text-decoration: underline;
}

.resultItem-snippet,
.resultItem-link {
    color: darkSlateGray;
    font-size: 13px;
}

@keyframes show {
    0% {
        opacity: 0;
        transform: translateY(100px);
    }

    100% {
        opacity: 1;
        transform: translateY(0);
    }
}


@media screen and (max-width: 750px) {
    .searchForm-container {
        padding: 20px 0 20px;
        height: auto;
        justify-content: space-between;
        flex-direction: column;
    }

    .searchForm {
        margin: 20px auto 0;
    }

    .searchForm-input {
       width: 300px;
	/** width: 100%; **/
    }

    .searchResults {
        /** width: 388px; **/
	width: 90%;
        margin-left: auto;
        margin-right: auto;
    }
}


/* End Wikipedia Search Styles */

```
