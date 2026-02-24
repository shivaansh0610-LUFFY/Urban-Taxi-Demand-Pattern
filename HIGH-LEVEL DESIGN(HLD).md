```mermaid
graph TD
    %% Styling - Darker fills with high-contrast white text
    classDef external fill:#6a1b9a,stroke:#4a148c,stroke-width:2px,color:#ffffff;
    classDef storage fill:#0277bd,stroke:#01579b,stroke-width:2px,color:#ffffff;
    classDef compute fill:#d84315,stroke:#bf360c,stroke-width:2px,color:#ffffff;
    classDef present fill:#2e7d32,stroke:#1b5e20,stroke-width:2px,color:#ffffff;

    %% Nodes
    A[NYC TLC CDN]:::external
    B[(Local File System)]:::storage
    C[Batch Processing Layer<br>Jupyter/Python]:::compute
    D[Analytical Layer<br>SciPy/Stats]:::compute
    E[(Aggregated Data)]:::storage
    F[Tableau / Power BI]:::present
    G[Final PDF Report]:::present

    %% Connections
    A -->|Monthly .parquet| B
    B -->|Raw Data| C
    C -->|Cleaned Data| D
    D -->|Metrics & Outliers| E
    C -->|Zone Mapping| E
    E -->|Data Extract| F
    E -->|Visuals & Stats| G
