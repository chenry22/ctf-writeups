### Index
- [Bookmarklet](#bookmarklet)
- [WebDecode](#webdecode)

### Bookmarklet
- In this challenge we are provided a link to a web page, and visiting this page provides us with a bookmarklet! A **bookmarklet** is essentially a browser bookmark that can run code- in this case we are given JavaScript.
-  Creating a new bookmarklet with the provided code will give us our flag- creation will vary depending on your browser!

### WebDecode
- We are linked to a webpage and told to inspect around! Navigating to the about tab and inspecting the HTML, we see that the element `<section class="about">` has an attribute "notify_true" with a Base64 encoded string in it! Decoding this string gives us our flag!