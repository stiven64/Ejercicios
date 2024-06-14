graph TD;
    A[Usuario] --> B[Abre la página https://studies.cs.helsinki.fi/exampleapp/notes]
    B --> C[Escribe una nueva nota]
    C --> D[Hace clic en el botón "Save"]
    D --> E{Envía una solicitud POST al servidor con la nueva nota}
    E --> F{Servidor recibe la solicitud POST}
    F --> G{Servidor guarda la nueva nota en la base de datos}
    G --> H{Servidor responde con código de éxito (200 OK)}
    H --> I[Actualiza la lista de notas mostrada en el navegador]
