# The confidentiality decision tree

```
Client project with confidentiality requirements?
├── YES → Check client AI policy
│    ├── Cloud SaaS approved? → Use with documented approval
│    └── No approval or restricted? → Ollama / LM Studio / approved enterprise tool
└── NO → Standard enterprise cloud tools apply
```

**Never — on any project:**
- Credentials or API keys
- PII
- Proprietary client algorithms or business logic
