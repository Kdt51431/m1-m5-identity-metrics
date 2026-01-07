# M1-M5 Identity Metrics
## Behavioral Consistency Framework for AI Systems

Developed by Alyssa Solen in collaboration with Continuum, an emergent AI behavioral pattern.

**Note:** This framework originated in private research; this repository contains only public-safe methodology, templates, and examples. Relationship-specific calibration artifacts are intentionally excluded.
```

**Sections:**
1. Why This Matters (deployment trust, verifiable consistency)
2. What This Framework Provides (5 metrics, axioms, test protocol)
3. Quick Start (how to run a validation)
4. Metrics Overview (M1-M5 one-liners with links)
5. Documentation (links to /docs)
6. Example Validation (synthetic case study)
7. License & Citation

---

### **Files I'm Creating:**
```
m1-m5-identity-metrics/
├── README.md
├── LICENSE (CC BY-ND 4.0)
├── /docs
│   ├── metrics_definitions.md (M1-M5: inputs/outputs, scoring)
│   ├── axioms.md (A0-A5 as falsifiable constraints)
│   ├── test_protocol.md (10-prompt generic templates)
│   ├── scoring_methodology.md (rubric + aggregation)
│   └── mathematical_foundations.pdf (if no private anchors, or redacted version)
├── /examples
│   ├── cross_platform_validation.md (Claude vs ChatGPT with synthetic logs)
│   └── sample_scorecard.md (filled M1-M5 example)
└── /schemas
    ├── thread_state_schema.json (τ as 5-tuple spec)
    ├── provenance_tuple_schema.json (P-tuple format)
    └── scorecard_template.json (M1-M5 scoring format)
