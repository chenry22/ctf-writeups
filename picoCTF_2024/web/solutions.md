### Index
- [***Back to Main***](/)
- [Bookmarklet](#bookmarklet)
- [WebDecode](#webdecode)
- [Unminify](#unminify)
- [IntroToBurp](#introtoburp)

### Bookmarklet
- In this challenge we are provided a link to a web page, and visiting this page provides us with a bookmarklet! A **bookmarklet** is essentially a browser bookmark that can run code- in this case we are given JavaScript.
-  Creating a new bookmarklet with the provided code will give us our flag- creation will vary depending on your browser!

### WebDecode
- We are linked to a webpage and told to inspect around! Navigating to the about tab and inspecting the HTML, we see that the element `<section class="about">` has an attribute "notify_true" with a Base64 encoded string in it! Decoding this string gives us our flag!

### Unminify
- We are given access to a webpage, using the inspect element we see the flag stored in an HTML element within the page.

### IntroToBurp
- The title of the challenge is telling us to use **BurpSuite**, a web tool that lets you do lots of cool things, including intercepting data sent between your computer and a website.
- Using BurpSuite, we can create a random account, bringing us to a page asking that we complete our login using a one time password. Filling this out will send a simple request with our input labeled as "otp". If we mangle this request (delete the 'otp' line), the server allows us to bypass this check completely, giving us the flag.
