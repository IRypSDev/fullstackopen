# 0.4: New note diagram



```mermaid

sequenceDiagram
    participant browser
    participant server

    Note right of browser: Form is filled out and the submit button is pressed
    browser-->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note { note: "..." }
    activate server
    Note left of server: Server adds the new note to the list of notes 
    server-->>browser: HTTP 302 (Header response) location: /exampleapp/notes
    deactivate server

    Note right of browser: Browser makes a new request to the location provided

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: CSS file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: JS file
    deactivate server

    Note right of browser: Browser executes the JavaScript code that fetches the list of notes from the server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: JSON file containing the list of notes
    deactivate server

    Note right of browser: Browser executes the JavaScript code to render the notes on the page

```

