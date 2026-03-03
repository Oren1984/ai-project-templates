option-a_classical-ml_rag-lite/
└─ skeleton/
   ├─ app/
   │  ├─ main.py
   │  ├─ routers/
   │  │  └─ triage.py
   │  ├─ services/
   │  │  ├─ classifier.py
   │  │  ├─ retriever.py
   │  │  └─ response_builder.py
   │  └─ schemas/
   │     ├─ request.py
   │     └─ response.py
   │
   ├─ scripts/
   │  ├─ prepare_data.py
   │  ├─ train_model.py
   │  └─ build_index.py
   │
   ├─ knowledge_base/
   │  └─ sample_runbooks.md
   │
   ├─ models/
   │  └─ .gitkeep
   │
   ├─ reports/
   │  └─ .gitkeep
   │
   ├─ tests/
   │  ├─ test_classifier.py
   │  ├─ test_retriever.py
   │  └─ test_api.py
   │
   ├─ .env.example
   ├─ Dockerfile
   ├─ docker-compose.yml
   ├─ requirements.txt
   └─ README.md