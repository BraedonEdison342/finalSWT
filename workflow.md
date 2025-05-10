flowchart TD
  subgraph User Interaction
    A[User Browser / CLI] -->|requests page or runs script| B[Dash Dashboard] 
    A -->|runs pipeline| C[Pipeline Service]
  end

  subgraph Pipeline Service
    C --> D[Data Ingestion & Preprocessing]
    D --> E[Model Training & Validation]
    E --> F[Prediction Engine]
    F --> G[Prediction Output CSV]
    F --> H[SHAP Explainability]
  end

  subgraph Storage & Config
    subgraph Config
      CFG[config.json]
    end
    subgraph Artifacts
      M[Trained Model (.pkl)]
      G
      R[SHAP HTML Report]
    end
    CFG --> C
    E --> M
    H --> R
  end

  subgraph Dashboard & Alerts
    B -->|reads| G
    B -->|embeds| R
    C -->|logs errors| L[Logging Service]
    L -->|on ERROR| S[Slack / Email Alert]
  end

  style User Interaction fill:#f9f,stroke:#333,stroke-width:1px
  style Pipeline Service fill:#bbf,stroke:#333,stroke-width:1px
  style Storage & Config fill:#bfb,stroke:#333,stroke-width:1px
  style Dashboard & Alerts fill:#ffb,stroke:#333,stroke-width:1px
