sequenceDiagram  
    participant browser  
    participant server

Note: Sending form as POST request and the server answers with http code 302

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server

    server-->>browser: redirecting browser to make GET request to /notes
    deactivate server

Note: browser makes a GET request for HTML document, server returns the HTML document

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server

    server-->>browser: HTML document
    deactivate server

Note: while executing HTML browser makes GET request for css file and javascript files.

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server

    server-->>browser: the css file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server

    server-->>browser: the javascript file
    deactivate server

Note: while executing javascript the browser sends GET request for json file

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server

    server-->>browser: [{"content": "534", "date": "2024-02-06T16:48:15.150Z"}, ... ]
    deactivate server