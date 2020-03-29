# Interview Questions

<details>
<summary>1. What's DOM?</summary>

> #### Answer:
>
> It's the `D`ocument `O`bject `M`odel that defines the logical structure of documents and the way a document is accessed and manipulated.

</details>

<details>
<summary>2. What's BOM?</summary>

> #### Answer:
>
> `B`rowser `O`bject `M`odel are additional objects provided by the browser (host environment) to work with everything except the document.

</details>

<details>
<summary>3. Is there any difference between window and document?</summary>

> #### Answer:
>
> The `document` object gives access to the page content. We can change or create anything on the page using it.
> The `window` object is a global object for JavaScript code, it represents the “browser window and provides methods to control it.

</details>

<details>
<summary>4. How to assign an event handler?</summary>

> #### Answer:
>
> - HTML attribute: `onclick="..."`;
> - DOM property: `elem.onclick = function`;
> - Methods: `elem.addEventListener(event, handler[, >phase])` to add, `removeEventListener` to remove.

</details>

<details>
<summary>5. What's bubbling principle?</summary>

> #### Answer:
>
> When an event happens on an element, it first runs the handlers on it, then on its parent, then all the way up on other ancestors.
>
> ![](../assets/image1.png)

</details>

<details>
<summary>6. How to stop bubbling?</summary>

> #### Answer:
>
> `event.stopPropagation()`

</details>

<details>
<summary>7. How to find out if the document is loaded (external resources can be still in progress of loading)?</summary>

> #### Answer:
>
> Subscribe on `DOMContentLoaded` event.

</details>

<details>
<summary>8. How to find out if the document is loaded (browser loaded all resources)?</summary>

> #### Answer:
>
> Subscribe on `window.load` event.

</details>

<details>
<summary>9. How to find node by id?</summary>

> #### Answer:
>
> ```javascript
> document.getElementById("id");
> document.querySelector("#id");
> ```

</details>

<details>
<summary>10. How to store data on the client side?</summary>

> #### Answer:
>
> - cookies
> - Web Storage
> - IndexedDB
> - Cache API

</details>

<details>
<summary>11. What are cookies?</summary>

> #### Answer:
>
> `Cookies` are small strings of data that are stored directly in the browser.

</details>

<details>
<summary>12. Which web storages are exist?</summary>

> #### Answer:

- `localStorage`
- `sessionStorage`

</details>

<details>
<summary>13. What is the difference between localStorage and sessionStorage?</summary>

> #### Answer:
>
> - The `sessionStorage` exists only within the current browser tab.
> - The data in the `sessionStorage` survives page refresh, but not closing/opening the tab.

</details>

<details>
<summary>14. Which JSON advantages over XML do you know?</summary>

> #### Answer:
>
> - Less verbose
> - Less size
> - Close of javascript

</details>

<details>
<summary>15. Which XML advantages over JSON do you know?</summary>

> #### Answer:
>
> - Meta data support
> - Mixed content Support
> - Browser rendering

</details>

<details>
<summary>16.  Which types of network requests are exist?</summary>

> #### Answer:
>
> - `XMLHttpRequest`
> - `AJAX`
> - `Fetch API`

</details>

<details>
<summary>17.  What's XMLHttpRequest?</summary>

> #### Answer:
>
> The `XMLHttpRequest` object can be used to request data from a web server.

</details>

<details>
<summary>19.  What's fetch?</summary>

> #### Answer:
>
> Method `fetch()` is the modern way of sending requests over `HTTP`. The browser starts the request right away and returns a promise.
> Getting a response is usually a two-stage process. The promise resolves with an object of the built-in Response class as soon as the server responds with headers.

</details>

<details>
<summary>20.  What's AJAX?</summary>

> #### Answer:
>
> `AJAX` is `A`synchronous `J`avaScript And `X`ML.
> `AJAX` just uses a combination of:
>
> - A browser built-in `XMLHttpRequest` object (to >request data from a web server);
> - JavaScript and `HTML` `DOM` (to display or use the >data).

</details>

<details>
<summary>21.  How do HTML parsing and script loading work if we use script tag without any special attribute?</summary>

> #### Answer:
>
> The `HTML` file will be parsed until the script file is hit, at that point parsing will stop and a request will be made to fetch the file. The script will then be executed before parsing is resumed.

</details>

<details>
<summary>22.  How do HTML parsing and script loading work if we use script tag with async attribute?</summary>

> #### Answer:
>
> `async` downloads the file during HTML parsing and will pause the `HTML` parser to execute it when it has finished downloading.

</details>

<details>
<summary>23.  How do HTML parsing and script loading work if we use script tag with defer attribute?</summary>

> #### Answer:
>
> `defer` downloads the file during `HTML` parsing and will only execute it after the parser has completed. `defer` scripts are also guaranteed to execute in the order that they appear in the document.

</details>

<br/>

**[⬆ back to top](#interview-questions)**
