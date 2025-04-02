# Diagram depicting the situation where the user creates a new note on the page  


sequenceDiagram 

    participant browser  
    participant server  

    Note right of browser: The user types a note in the text field and clicks "Save"

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note (with the note content)
    activate server
    server-->>browser: 302 Found (Redirect to /notes)
    deactivate server

    Note right of browser: The browser follows the redirect and reloads the notes page

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: the CSS file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: the JavaScript file
    deactivate server

    Note right of browser: The browser executes the JavaScript, which requests the updated notes

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: JSON with the new note included
    deactivate server

    Note right of browser: The browser executes the rendering function to display the new note in the list
