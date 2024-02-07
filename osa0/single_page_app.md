sequenceDiagram  
    participant browser  
    participant server

Note: browser makes a GET request for HTML document, server returns the HTML document

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server

    server-->>browser: HTML document
    deactivate server

Note: while executing HTML browser makes GET request for css file and javascript files.

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server

    server-->>browser: the css file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    activate server

    server-->>browser: the javascript file
    deactivate server

Note: while executing javascript the browser sends GET request for json file

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server

    server-->>browser: [{"content": "OS MENINO TA COM O PACOTE",
    "date": "2024-02-07T22:16:55.963Z"}, ... ]
    deactivate server