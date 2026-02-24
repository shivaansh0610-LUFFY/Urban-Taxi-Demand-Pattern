```mermaid
sequenceDiagram
    autonumber
    actor Stakeholder
    participant Interface as 📊 Tableau Dashboard
    participant Engine as Tableau Data Extract
    participant RealWorld as Decision Making

    Stakeholder->>Interface: Opens Urban Taxi Demand Dashboard
    Interface->>Engine: Request baseline NYC view
    Engine-->>Interface: Return city-wide heatmap data
    Interface-->>Stakeholder: Displays demand hotspots
    
    Stakeholder->>Interface: Filters to "Manhattan" & "Monday Mornings"
    Interface->>Engine: Query filtered subset
    Engine-->>Interface: Return specific distribution stats
    Interface-->>Stakeholder: Updates charts to show localized peaks
    
    Stakeholder->>RealWorld: Uses insights to propose taxi fleet reallocation
