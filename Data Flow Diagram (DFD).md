```mermaid
graph TD
    %% Styling - Darker fills with high-contrast white text
    classDef dataState fill:#283593,stroke:#1a237e,stroke-width:2px,color:#ffffff;
    classDef action fill:#e65100,stroke:#bf360c,stroke-width:2px,color:#ffffff;

    A([Raw Trip Record<br>tpep_pickup, PULocationID, fare_amount]):::dataState --> B{Is Data Valid?}:::action
    B -->|No: Negative fare, 0 distance| C[Drop Row]:::action
    B -->|Yes| D[Format Datetime & Calculate Trip Duration]:::action
    D --> E[Join with Taxi Zone Lookup Table]:::action
    E --> F([Enriched Row<br>Borough, Zone Name added]):::dataState
    F --> G[Aggregate by Date, Hour & Zone]:::action
    G --> H([Final Metric<br>Total Rides per Hour per Zone]):::dataState
