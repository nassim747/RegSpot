## Problem

Start-ups lose hours scanning multiple regulators’ sites…

## Architecture

```mermaid
flowchart TD
    Crawler -->|Redis Stream| Loader
    Loader -->|Postgres| DB[(Postgres + pgvector)]
    DB --> API
    API --> SlackBot
    API --> NextJS
