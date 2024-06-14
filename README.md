```mermaid

sequenceDiagram
    participant user
    participant browser
    participant server

    user->>browser: Escribe texto y hace clic en Guardar
    activate browser
    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note (datos de la nota)
    activate server
    server-->>browser: 302 Redireccionar a /exampleapp/notes
    deactivate server
    deactivate browser

    Note right of browser: El navegador es redirigido y recarga la página de notas

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: Documento HTML
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: archivo CSS
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: archivo JavaScript
    deactivate server

    Note right of browser: El navegador comienza a ejecutar el código JavaScript que obtiene el JSON del servidor

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{ "content": "HTML is easy", "date": "2023-1-1" }, ... ]
    deactivate server

    Note right of browser: El navegador ejecuta la función de devolución de llamada que renderiza las notas

