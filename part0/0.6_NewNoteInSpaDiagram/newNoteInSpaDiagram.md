# 0.6: New note in SPA diagram



```mermaid

sequenceDiagram
    participant browser
    participant server

    Note right of browser: Form is filled out and the submit button is pressed

    Note right of browser: Browser executes the event handler that submits the data

    Note right of browser: Event handler creates a new note object and adds it to an array

    Note right of browser: Event handler executes the function that renders notes to display

    Note right of browser: Event handler sends the new note to the server

    browser-->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa { "content": "...", "date": "..." }
    activate server
    Note left of server: Server adds the new note to the list of notes 
    server-->>browser: HTTP 201 { "message": "note created" }
    deactivate server

```

