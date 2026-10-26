sequenceDiagram
  participant U as User
  participant A as API
  participant D as Database
  U->>A: POST /login
  A->>D: SELECT user
  D-->>A: row
  alt password ok
    A-->>U: 200 + cookie
  else bad password
    A-->>U: 401
end