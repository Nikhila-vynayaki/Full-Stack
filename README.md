```mermaid
sequenceDiagram
  browser --> server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
  server --> browser :(redirect, status:302) to GET /exampleapp/notes

