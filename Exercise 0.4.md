```mermaid
    sequenceDiagram
        participant User
        participant Browser
        participant Server

        Browser->>+Server: GET [https://https://studies.cs.helsinki.fi/exampleapp/notes]
        Server-->>-Browser: HTML Document

        Browser->>+Server: GET [https://https://studies.cs.helsinki.fi/exampleapp/main.css]
        Server-->>-Browser: CSS File

        Browser->>+Server: GET [https://https://studies.cs.helsinki.fi/exampleapp/main.js]
        Server-->>-Browser: JS File

        Note over Browser, Server: *the browser executes the javascript code

        Browser->>+Server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
        Server-->>-Browser: [{"content": "yo", "date": "2025-04-27T14:58:06.459Z"},...

        Note over Browser, Server: Renders the notes page through callback function

        User->>Browser: User Inputs to Text Field
        
        Note right of User: Input: Hello World

        User->>Browser: User clicks the "Save" Button
        Browser->>+Server: User input is sent to the server via the Form's "Submit"
        Server-->>-Browser: The Server instructs the browser to reload the notes page with a *redirect
```
