option-b_dl-rag_distilbert/
└─ skeleton/
   ├─ app/
   │  ├─ main.py
   │  ├─ routers/
   │  │  └─ triage.py
   │  ├─ services/
   │  │  ├─ dl_classifier.py
   │  │  ├─ retriever.py
   │  │  ├─ fallback.py
   │  │  └─ response_builder.py
   │  └─ schemas/
   │     ├─ request.py
   │     └─ response.py
   │
   ├─ training/
   │  ├─ train_category.py
   │  ├─ train_urgency.py
   │  └─ evaluate.py
   │
   ├─ scripts/
   │  ├─ build_embeddings.py
   │  └─ smoke_test.py
   │
   ├─ knowledge_base/
   │  └─ sample_runbooks.md
   │
   ├─ data/
   │  └─ .gitkeep
   │
   ├─ models/
   │  └─ .gitkeep
   │
   ├─ reports/
   │  └─ .gitkeep
   │
   ├─ tests/
   │  ├─ test_inference.py
   │  ├─ test_retrieval.py
   │  └─ test_api.py
   │
   ├─ .env.example
   ├─ Dockerfile
   ├─ docker-compose.yml
   ├─ requirements.txt
   └─ README.md