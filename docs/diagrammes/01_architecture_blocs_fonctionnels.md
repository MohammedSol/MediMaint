flowchart TD
    subgraph S_USER["👤 Utilisateur & Terrain"]
        TECH["👷 Technicien Biomédical"]
    end

    subgraph S_FRONT["🖥️ 1. Interface Utilisateur & Entrées"]
        UI["Interface Chat & Upload Photo\n(Web / Responsive Mobile)"]
    end

    subgraph S_API["🌐 2. API Gateway & Sécurité Amont"]
        API["API REST / WebSocket Gateway\n(FastAPI)"]
        AUTH["Module d'Authentification\n(Tokens JWT / Rôles)"]
        PC1{"[PC1] CONTRÔLE D'ACCÈS\nLe technicien a-t-il le droit\nde voir cet équipement ?"}
        SEC_FILTER["Filtre Anti-Injection & Scope\n(DR 100e & BeneVision)"]
    end

    subgraph S_ORCH["🤖 3. Orchestration Agentique & Décision"]
        ROUTER["Routeur Multimodal d'Intentions"]
        PLANNER["Planificateur / Décomposeur\n(LangGraph StateGraph)"]
        SYNTH["Synthétiseur de Réponse Sourcée"]
        PC3{"[PC3] VÉRIFICATION CITATIONS\nChaque affirmation est-elle\nétayée par une page réelle ?"}
    end

    subgraph S_VLM["📸 4. Modèle Vision-Langage (VLM) & OCR"]
        VLM["Modèle Vision-Langage / OCR\n(Qwen2-VL / Llama-3.2-Vision / Tesseract)"]
    end

    subgraph S_RAG["📚 5. Recherche Documentaire Hybride"]
        RAG_ENGINE["Moteur de Retrieval Hybride\n(Dense BGE-M3 + BM25 Sparse)"]
        RERANK["Re-ranker Cross-Encoder"]
    end

    subgraph S_STORE["💾 6. Stockage & Index"]
        CHROMA[("Base Vectorielle ChromaDB\n(Index 1024d + Métadonnées)")]
        CORPUS_RAW[("Dossier Corpus Local\n(PDFs, Markdown, Images)")]
        AUDIT_DB[("Journal d'Audit Immuable\n(Logs requêtes & citations)")]
    end

    subgraph S_MCP["🔌 7. Outils & Serveur MCP (Model Context Protocol)"]
        MCP_SERVER["Serveur MCP GMAO / Tickets\n(stdio / SSE)"]
        PC2{"[PC2] APPROBATION HUMAINE\nLe technicien valide-t-il\nla création du ticket ?"}
        GMAO[("Système GMAO Hôpital\n(Gestion Maintenance Assistée)")]
    end

    %% Flux principaux
    TECH -->|"Question texte + Photo voyant"| UI
    UI -->|"Requête multipart/form-data"| API
    API --> AUTH --> PC1
    PC1 -->|"✅ Accès autorisé (Groupe valide)"| SEC_FILTER
    PC1 -->|"⛔ Accès refusé"| UI
    SEC_FILTER -->|"Requête saine & dans périmètre"| ROUTER
    SEC_FILTER -->|"⛔ Hors périmètre / Injection"| UI

    ROUTER -->|"Si image présente"| VLM
    VLM -->|"Description textuelle des voyants"| ROUTER
    ROUTER -->|"Requête enrichie + filtre groupe"| PLANNER

    PLANNER -->|"Recherche sémantique filtrée"| RAG_ENGINE
    RAG_ENGINE -->|"Consultation index"| CHROMA
    CHROMA -.->|"Lecture chunks autorisés"| RAG_ENGINE
    RAG_ENGINE -->|"Top-10 chunks"| RERANK
    RERANK -->|"Top-4 chunks re-classés"| SYNTH

    SYNTH -->|"Brouillon réponse avec citations"| PC3
    PC3 -->|"✅ Citations exactes et fondées"| UI
    PC3 -->|"❌ Citation hallucinée ou absente"| SYNTH
    SYNTH -.->|"Enregistrement audit"| AUDIT_DB

    %% Flux MCP Action Sensible
    PLANNER -->|"Besoin d'intervention corrective"| PC2
    PC2 -->|"Attente confirmation technicien"| UI
    UI -->|"✅ Accord explicite 'Créer le ticket'"| PC2
    PC2 -->|"Appel d'outil sécurisé (créer_ticket)"| MCP_SERVER
    MCP_SERVER -->|"Écriture idempotente (UUID)"| GMAO
    GMAO -->|"N° Ticket confirmé (TICK-2025-089)"| MCP_SERVER
    MCP_SERVER -->|"Confirmation avec N°"| UI

