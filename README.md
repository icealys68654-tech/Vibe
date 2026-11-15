Here’s a clean, renderable Mermaid diagram for the Build → Include → Test → Verify process:

mermaid
flowchart TD
    Start([Start]) --> Build

    subgraph Process["Build → Include → Test → Verify"]
        Build["1. BUILD<br/>Compile / Assemble / Construct"]
        Include["2. INCLUDE<br/>Add dependencies, headers, configs"]
        Test["3. TEST<br/>Run unit / integration / smoke tests"]
        Verify["4. VERIFY<br/>Confirm against requirements"]
    end

    Build --> Include
    Include --> Test
    Test --> Verify

    Verify -->|Pass| Success([✅ Pass – Proceed / Release])
    Verify -->|Fail| Fail[❌ Fail – Log issue]
    Fail --> Build

    style Build fill:#4CAF50,stroke:#2E7D32,color:#fff
    style Include fill:#2196F3,stroke:#1565C0,color:#fff
    style Test fill:#FF9800,stroke:#E65100,color:#fff
    style Verify fill:#9C27B0,stroke:#6A1B9A,color:#fff
    style Success fill:#2E7D32,stroke:#1B5E20,color:#fff
    style Fail fill:#C62828,stroke:#B71C1C,color:#fff
    
Alternative simpler vertical version
mermaid
flowchart TD
    A[1. BUILD<br/>Compile / Assemble] --> B[2. INCLUDE<br/>Add dependencies & configs]
    B --> C[3. TEST<br/>Execute tests]
    C --> D[4. VERIFY<br/>Check against requirements]
    D -->|Pass| E[✅ Proceed / Release]
    D -->|Fail| A
