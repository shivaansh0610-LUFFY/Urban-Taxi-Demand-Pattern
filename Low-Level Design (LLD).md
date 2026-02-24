```mermaid
graph TD
    %% Styling - Darker fills with high-contrast white text
    classDef script fill:#37474f,stroke:#263238,stroke-width:2px,color:#ffffff;
    classDef data fill:#00695c,stroke:#004d40,stroke-width:2px,color:#ffffff;
    classDef action fill:#c62828,stroke:#b71c1c,stroke-width:2px,color:#ffffff;

    A[download_script.py]:::script -->|Uses urllib / requests| B[(Raw .parquet files)]:::data
    B -->|Loads via PyArrow| C[clean_data.ipynb]:::script
    C -->|dropna & drop_duplicates| D[Pandas DataFrame]:::data
    D -->|Merges with Zone CSV| E[(Enriched Clean Data)]:::data
    E -->|Inputs to| F[analysis.ipynb]:::script
    F -->|Calculates using SciPy.stats| G[Identify Demand Outliers]:::action
    G -->|Plots via Seaborn| H[Visual Distributions]:::action
