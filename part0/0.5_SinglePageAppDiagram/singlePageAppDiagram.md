# 0.5: Single page app diagram



```mermaid

sequenceDiagram
    participant browser
    participant server

    Note right of browser: Browser starts requesting the page from the server

    browser-->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server-->>browser: HTML document
    deactivate server

    browser-->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: CSS file
    deactivate server

    browser-->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    activate server
    server-->>browser: JS file
    deactivate server

    Note right of browser: Browser executes the JavaScript code that requests the list of notes from the server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: JSON file containing the list of notes
    deactivate server

    Note right of browser: Browser executes the event handler that adds notes to an array and renders them for display

```


