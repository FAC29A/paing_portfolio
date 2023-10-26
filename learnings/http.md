# Weeks 4-6: Learn how to manage asynchronous tasks and send HTTP requests using JavaScript.
Examples are based on this API project, [**GitFlick**](https://github.com/FAC29A/GitFlick).

## 1. Write code that executes asynchronously

```js
// GIPHY
async function fetchGif(searchTerm) {
  try {
    const response = await fetch(
      `https://api.giphy.com/v1/gifs/search?q=${searchTerm}&api_key=7zcr5tNW9JmYSO2awsqBqGK3OjpLjnh3&limit=10`
    );
    const data = await response.json();

    if (!data.data.length) {
      throw new Error(
        "Sorry, No results found for the provided search term!😔 "
      );
    }

    return data.data.map((gif) => gif.images.original.url);
  } catch (error) {
    throw error;
  }
}
```

- The `fetchGif` function is defined as asynchronous using the `async` keyword.
- It makes an asynchronous API request using `fetch` with the `await` keyword, which pauses execution until the request is complete.
- Upon receiving the response, it processes the data asynchronously using `await response.json()`.
- If no data is found, it throws an error, otherwise, it returns an array of URLs.
- If any error occurs during this process, it's caught and re-thrown in the `catch` block, showcasing error handling in asynchronous operations.


## 2. Use callbacks to access values that aren’t available synchronously

- The `forEach` method processes each item in an array using a callback, allowing for asynchronous access to the values within the array.

```js
function displayRepos(repos) {
    const repoList = document.querySelector(".repo-list");
    repoList.innerHTML = "";  // clear existing repos

    repos.forEach((repo) => {
        const repoDiv = document.createElement("div");
        repoDiv.className = "repo-item";
        repoDiv.innerHTML = `
            <h2>${repo.name}</h2>
            <p>Language: ${repo.language}</p>
            <a href="${repo.html_url}" target="_blank">View on GitHub</a>
        `;
        repoList.appendChild(repoDiv);
    });
}


```
- In this snippet, the callback function is `(repo) => {...}`, and it is being used to access each `repo` object in the `repos` array asynchronously as the `forEach` method iterates through the array.

## 3. Use promises to access values that aren’t available synchronously

- Promises are objects representing the eventual completion or failure of an asynchronous operation. In this code snippet, I've used `then` method to handle the resolution of a Promise.

```js
const [profile, repos] = await Promise.all([
    fetch(`https://api.github.com/users/${username}`).then((res) => res.json()),
    fetch(`https://api.github.com/users/${username}/repos?sort=updated`).then((res) => res.json())
]);

```

## 4. Use the fetch method to make HTTP requests and receive responses


- I utilized the `fetch` method to send HTTP requests to GitHub API and handle the responses asynchronously.

```js
const response = await fetch(`https://api.github.com/users/${username}`);

```



## 5. Configure the options argument of the fetch method to make GET and POST requests

- In our code, we've demonstrated `GET` requests using fetch. We did not use `POST` method here.

```js
  try {
    const [profile, repos] = await Promise.all([
      fetch(`https://api.github.com/users/${username}`).then((res) =>
        res.json()
      ),
      fetch(`https://api.github.com/users/${username}/repos?sort=updated`).then(
        (res) => res.json()
      ),
    ]);
```

```js
  try {
    const response = await fetch(apiUrl, {
      method: 'GET',
      headers: headers,
    });
```


## 6. Use the map array method to create a new array containing new values

- The `map()` method is employed to create a new array by calling a function on every element in the initial array.


```js
return data.data.map((gif) => gif.images.original.url);

```


## 7. Use the filter array method to create a new array with certain values removed

- The `filter()` method is used to create a new array by testing each element with a predicate function.

```js
 // Get the language filter dropdown
    const languageFilter = document.getElementById("languageFilter");

    // Clear existing options first (except the first 'Filter by Language' option)
    while (languageFilter.options.length > 1) {
      languageFilter.remove(1);
    }

```

## 8. Access DOM nodes using a variety of selectors

- Various DOM selectors have been employed to access elements within the document.

```js
const username = document.getElementById("username").value;
const repoList = document.querySelector(".repo-list");

```


## 9. Add and remove DOM nodes to change the content on the page

- DOM manipulation methods are used to add or remove content on the page.

```js
repoList.innerHTML = "";  // clear existing repos
repoList.appendChild(repoDiv);  // add new repoDiv

```

## 10. Toggle the classes applied to DOM nodes to change their CSS properties

- ClassList methods are used to add or remove classes, affecting the styling of DOM elements.
```js
document.getElementById("flickBtn").classList.add("loading");
document.getElementById("flickBtn").classList.remove("loading");

```

## 11. Use consistent layout and spacing

- I made sure our code has a consistent layout and spacing which is crucial for readability and maintenance.


## 12. Follow a spacing guideline to give our app a consistent feel

- I have followed a specific spacing guideline throughout my code to make sure our app looks consistent and organized.


## 13. Debug client side JS in our web browser

- Utilizing `console.error` to log errors to the console is a crucial step for debugging client-side JavaScript.

```js
console.error("Network Error:", error);

```




## 14. Use console.log() to help us debug our code

- We had to use `console.log()` as it is fundamental for debugging.
- Usually it does get removed from the code once we are certain that everything runs correctly.
- Although `console.log()` wasn't used in our code, `console.error` serves a similar purpose of logging information to the console which is a crucial part of the debugging process.

```js
console.error('Error:', error);

```


