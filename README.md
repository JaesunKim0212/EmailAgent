## Email agent 구조 ##


project/
├── app/
│   ├── main.py           # FastAPI
│   ├── graph.py          # LangGraph
│   ├── state.py
│   ├── nodes/             # 워크플로우 로직 담당
│   │     ├── planner.py
│   │     ├── search.py
│   │     ├── calendar.py
│   │     ├── draft.py
│   │     ├── review.py
│   │     └── send.py    
│   ├── tools/              # 외부 기능 호출 담당
│   │     ├── tavily_tool.py
│   │     ├── gmail_tool.py
│   │     └── caledar_tool.py
│   ├── fallback/
│   │     ├── retry.py
│   │     └── fallback_router.py
│   ├── validation/         # 입력/출력 검증 담당
│   │     ├── draft_validator.py
│   │     ├── tool_validator.py
│   │     └── input_validator.py
│   └── memory/                     # Conversation/history/state persistence
│         ├── sqlite_store.py
│         └── vector_store.py
├── data/
│   ├── app.db            # SQLite
│   └── chroma_db/
│
├── logs/
│
└── tests/
