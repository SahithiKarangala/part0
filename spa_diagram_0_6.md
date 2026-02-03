sequenceDiagram

    participant browser
    participant server

    Note right of browser: The below sequence of event is when save button is clicked
    
    Note right of browser: 1.The new note is created and rendered to the note list on the page.
    Note right of browser: 2.The new note is sent to the server

    browser-->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate server
    Note left of server: new note sent to the server in json format
    server-->>browser: 201 status code and response in the form of json
    deactivate server
