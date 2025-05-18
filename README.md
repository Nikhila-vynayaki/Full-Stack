```mermaid
sequenceDiagram
  browser ->> server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
 Note left of server: server redirects the browser with status:302 to /exampleapp/notes
  browser->> server: GET https://studies.cs.helsinki.fi/exampleapp/notes
server->>browser: HTML doc
browser ->> server:GET https://studies.cs.helsinki.fi/exampleapp/main.css
server ->> browser:CSS file
browser ->> server:GET https://studies.cs.helsinki.fi/exampleapp/main.js
server->>browser:JS file
Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    server-->>browser: [{ "content": "HTML is easy", "date": "2023-1-1" }, ... ]

    Note right of browser: The browser executes the callback function that renders the notes
