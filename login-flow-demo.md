# Login Flow Demo

This file shows how the same Mermaid diagram appears when embedded in Markdown documentation on GitHub.

## Flowchart

```mermaid
flowchart TD
A([User]) --> B[Login Page]
B --> C{Valid credentials?}
C -->|yes| D[Create Session]
C -->|no| E[Show Error]
subgraph Auth["Auth Service"]
C
end
```

## Sequence Diagram

```mermaid
sequenceDiagram
actor U as User
participant W as Web App
participant A as Auth Service
participant D as Database
U->>W: POST /api/login
W->>A: validate(credentials)
A->>D: query user
D-->>A: user record
alt valid credentials
A-->>W: JWT token
W-->>U: redirect to dashboard
else invalid credentials
A-->>W: auth failed
W-->>U: Show error
end
```

Source files are in the `example/` folder for editing and version control.
