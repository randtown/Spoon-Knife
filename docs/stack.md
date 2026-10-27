# Local stack

This diagram shows how the local frontend, API, and database communicate through the Compose network, with persistent database storage.


flowchart LR
    B[Browser] --> FE

    subgraph Compose["Docker Compose Network"]
        FE[frontend :3000] --> API[api :8000]
        API --> DB[(db :5432)]
    end

    DB --- pgdata[(pgdata volume)]

