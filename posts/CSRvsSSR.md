#  Client Side Rendering vs Server Side Rendering

## Client Side Rendering (CSR)

Client Side Rendering (CSR) means rendering pages directly in the browser using JS.  All the logic - including data fetching and routing - is done on client-side on the browser.  This means that users can get near-instant updates and feedback when interacting with a page without requiring a full page reload eg. clicking the submit form on a form.

How does Client Side Rendering (CSR) work? Let's break it down!

1.    **User requests a webpage**: The user requests a webpage from the browser.

2.    **The server receives the request**: The user’s action triggers a GET request to the server, which identifies the desired route or URL.

3.    **The server sends a minimal HTML page with links to CSS and JavaScript files**: The browser requests the initial HTML file from the server. The file contains links to external CSS stylesheets and JavaScript files.

4.    **Parsing the HTML**: The browser parses the HTML markup and constructs the Document Object Model (DOM) tree, which represents the webpage's structure.

5.    **Browser downloads CSS and JavaScript**: The browser sends additional requests to the server to download the CSS and JavaScript resources.

6.    **Rendering the page**: The browser uses the DOM tree and the downloaded CSS files to render the basic structure of the web page. This includes elements like text, images, buttons, and styles.

7.    **JavaScript execution**: The browser executes the JavaScript code to add interactivity and dynamic content to the webpage. This can include animations, form validations, or fetching data from an API.

8.    **Re-rendering and updating**: As the user interacts with the webpage (clicking on buttons, filling out forms), the browser will re-render parts of the webpage based on the user's actions. This can involve updating the DOM or making additional requests to the server for new data.

9.    **Final display**: The updated DOM, along with any dynamically fetched data, is rendered by the browser, resulting in a fully interactive and dynamically updated webpage.

## Server Side Rendering

Server Side Rendering is when a web page is rendered on the server rather than on the browser, like client side rendering. 

The Web Browser will send a request for information to the server which sends the fully rendered page to the client.  The browser will down the JS files to make the page be interactable. 

Server Side Rendering is suitable for web pages that display real-time information, updates or frequently changing content.

Here's a high-level overview of how the SSR process works and how it generates and serves web pages:

1.    **A user visits a URL**: a user navigates to a URL via their browser.

2.    The server receives a request for the page: This action sends a request to the server, which receives the request and identifies the desired route or URL.

3.    Fetching data: The server retrieves the necessary data from databases, external APIs, or other relevant sources. This data will be used to populate the HTML template.

4.    Template rendering: The server generates the HTML markup using a templating engine or a framework that combines the fetched data with the predefined structure of the page. This includes rendering the content, applying styles, and adding any necessary functionality.

5.    Sending the rendered page: Once the template is rendered and the HTML is generated, the server sends the fully rendered page to the user's browser as a response to the request.

6.    Displaying the page: The user's browser then displays the page without waiting for additional JavaScript execution since the initial page load does not depend on JavaScript code.

7.    Rehydration: Along with the rendered HTML, the server also sends the JavaScript required to handle client-side interactivity and dynamic behavior. This JavaScript is responsible for "rehydrating" the static HTML into a fully interactive web app, ensuring a seamless transition from server-side rendering to client-side interactivity. For example, say an app has a form submit button, the rehydration process attaches the click event listener to the button, ensuring it fires when clicked. Without rehydration, the button will remain non-interactive when clicked.

8.    Repeat the rendering process: When the user navigates to other pages, the browser sends new requests to the server, and the process repeats itself.

Examples include:

* Real-time chat app that provides the initial page load with user data and chat history.

* Payment app that displays user account details and recent transactions.

* E-commerce site with pages that offer products with dynamic pricing and availability.

* News site with ever changing new stories

The benifits of SSR is:

* Faster load time for better UX by speeding up page loading when users have a slow internet connection.

* Search engines can easily index and crawl content because the content can be rendered before the page is loaded.

* Enables real-time content generation allowing for instant updates and personalized experiences.

* Connects with various back-end services and / or databases and can handle very complex logic.

Drawbacks:

* May cause slower page rendering. Server-side rendering is ideal for static HTML site generation. However, SSR generates pages for each request, which can lead to slower load speeds in very complex applications. 

* Since Server Side Rendering uses higher server resources, hosting those applications can become more expensive.

* SSR can elevate server load, necessitating more reliable infrastructure and upkeep. 
