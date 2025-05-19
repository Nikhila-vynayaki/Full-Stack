```mermaid
sequenceDiagram
    participant User
    participant Browser
    participant Server

    Note left of User: Initial Page Load (First Visit)
    User->>Browser: Visits SPA (e.g., /spa)
    Browser->>Server: GET /spa (HTML)
    activate Server
        Server-->>Browser: Minimal HTML + links to CSS/JS
    deactivate Server

    Browser->>Server: GET /styles.css (CSS)
    Server-->>Browser: Returns CSS
    Browser->>Server: GET /spa.js (JavaScript)
    Server-->>Browser: Returns JS

    Browser->>Browser: Parses HTML, applies CSS, executes JS
    Browser->>Server: GET /data.json (API call for data)
    Server-->>Browser: JSON data (e.g., notes)
    Browser->>Browser: Dynamically renders content

    Note left of User: Form Submission (SPA Behavior)
    User->>Browser: Submits form (e.g., new note)
    Browser->>Browser: JS prevents default submit
    Browser->>Server: POST /api/notes (JSON)
    Server-->>Browser: 201 Created (No redirect)
    Browser->>Browser: Updates DOM (No reload)
