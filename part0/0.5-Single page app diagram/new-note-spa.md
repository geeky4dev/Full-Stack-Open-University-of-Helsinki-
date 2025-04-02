# Diagram depicting the situation where the user goes to the single-page app version of the notes app

sequenceDiagram
    participant browser
    participant server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: main.css Response (the css file)
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    activate server
    server-->>browser: spa.js Response (the JavaScript file)
    deactivate server

    Note right of browser: The browser starts executing the JavaScript code that manipulates the page dynamically
    
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: JSON Response (Notes Data)
    deactivate server

    Note right of browser: The browser updates the page content dynamically without reloading
```



    

