# Diagram depicting the situation where the user creates a new note using the single-page version of the app.

sequenceDiagram

    participant browser
    participant server

    Note right of browser: The user types a note in the text field and clicks "Save"

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa (with the note content)
    activate server
    server-->>browser: 201 Created (JSON response with the new note)
    deactivate server

    Note right of browser: The browser updates the UI without reloading the page

    browser->>browser: JavaScript updates the notes list dynamically

    Note right of browser: The new note is now displayed immediately without a full page reload
