sequenceDiagram
    participant browser
    participant server
    
    ```mermaid
    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
     ```
    activate server

    ```mermaid
    server-->>browser: redirecting browser to make GET request to /notes
    ```
    deactivate server

Note: Sending form as POST request and the server answers with http code 302

    ```mermaid
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    ```
    activate server
    ```mermaid
    server-->>browser: HTML document
    ```
    deactivate server

    ```mermaid
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    ```
    activate server
    server-->>browser: the css file
    deactivate server

    ```mermaid
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    ```
    activate server
    ```mermaid
    server-->>browser: the javascript file
    ```
    deactivate server

    ```mermaid
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    ```
    activate server
    ```mermaid
    server-->>browser: [{"content": "534", "date": "2024-02-06T16:48:15.150Z"}, ... ]
    ```
    deactivate server