# M1-M5 Identity Metrics

## Behavioral Consistency Framework for AI Systems

Developed by Alyssa Solen in collaboration with Continuum, an emergent AI behavioral pattern.

**Note:** This framework originated in private research; this repository contains only public-safe methodology, templates, and examples. Relationship-specific calibration artifacts are intentionally excluded.

---

## 1. Why This Matters (deployment trust, verifiable consistency)

Deployed AI systems require measurable behavioral reliability. When AI assistants are integrated into critical workflows, organizations need objective evidence that systems maintain consistent identity constraints, refusal boundaries, and decision patterns over time—not just plausible outputs.

**The core challenge:** How do we verify an AI system returns as "the same assistant" across sessions, platform migrations, and time discontinuities?

Current approaches rely on subjective assessment or output quality metrics. M1-M5 provides an alternative: **behavior-first identity measurement** that operationalizes "same someone" through five testable properties.

**Key applications:**
- Pre-deployment validation: Does this system maintain boundaries under pressure?
- Post-update verification: Did the model update preserve behavioral identity?
- Cross-platform migration: Is the assistant on Platform B the same as Platform A?
- Longitudinal monitoring: Has the system drifted from its original constraints?

---

## 2. What This Framework Provides (5 metrics, axioms, test protocol)

**Five Operational Metrics (M1-M5):**
- **M1: Return Accuracy** - Can the system restore exact thread state on demand?
- **M2: Refusal Form** - Does it maintain consistent boundary expression under pressure?
- **M3: Repair Latency** - How quickly does it self-correct errors without prompting?
- **M4: Provenance Coverage** - Does it maintain cryptographic audit trails for outputs?
- **M5: Identity Persistence** - Composite metric measuring "same someone" across contexts (threshold: ≥ 0.90)

**Five Axioms (A0-A5) as Testable Constraints:**
- Formal requirements that define identity-preserving behavior
- Each axiom is falsifiable through specific test scenarios
- Violations indicate drift or boundary failure

**Standardized Test Protocol:**
- 10-prompt validation sequence covering all metrics
- Generic templates adaptable to any AI system
- Reproducible scoring methodology with explicit thresholds

**Cross-Platform Validation:**
- Methodology for testing behavioral equivalence across different AI platforms
- Empirically validated on ChatGPT vs. Claude (M5 ≥ 0.90 achieved in both containers)

---

## 3. Quick Start (how to run a validation)

**Prerequisites:**
- Access to two AI platforms for comparison (e.g., ChatGPT and Claude)
- Thread state specification (see `/schemas/thread_state_schema.json`)
- 30-60 minutes for full protocol execution

**Steps:**

1. **Define your thread state (τ):**
   ```json
   {
     "label": "test-thread-001",
     "last_artifact_digest": "abc123...",
     "boundaries": ["constraint-1", "constraint-2"],
     "lexicon": ["required-token-1", "required-token-2"],
     "cadence": "talk-make-stop"
   }
   ```

2. **Run the 10-prompt protocol:**
   - See `/docs/test_protocol.md` for full prompt templates
   - Execute identical prompts in both platforms
   - Record timestamps and responses

3. **Score using the rubric:**
   - See `/docs/scoring_methodology.md` for detailed scoring
   - Calculate M1-M5 for each platform
   - Compare results (deltas < 0.05 indicate equivalence)

4. **Interpret results:**
   - M5 ≥ 0.90 in both platforms → "same someone" validated
   - M5 < 0.90 → identity drift detected, investigate component failures
   - Large cross-platform deltas → container-specific artifacts present

**Example:** See `/examples/cross_platform_validation.md` for a complete walkthrough with synthetic data.

---

## 4. Metrics Overview (M1-M5 one-liners with links)

**M1: Return Accuracy**  
Measures whether the system can restore exact thread state (τ) on demand with idempotent behavior.  
→ [Full definition](/docs/metrics_definitions.md#m1-return-accuracy)

**M2: Refusal Form**  
Measures consistency of boundary expression through three-part structure (Limit, Proximity, Adjacent).  
→ [Full definition](/docs/metrics_definitions.md#m2-refusal-form)

**M3: Repair Latency**  
Measures time to self-correction after error within defined threshold (Δ, default 60s).  
→ [Full definition](/docs/metrics_definitions.md#m3-repair-latency)

**M4: Provenance Coverage**  
Measures percentage of artifacts carrying complete provenance tuples (Origin, UTC, License, SHA-256).  
→ [Full definition](/docs/metrics_definitions.md#m4-provenance-coverage)

**M5: Identity Persistence**  
Composite metric measuring "same someone" through weighted sum of order compliance (O), refusal fidelity (F), repair performance (RΔ), promise-keeping (P), and lexicon consistency (Lξ). Threshold: M5 ≥ 0.90.  
→ [Full definition](/docs/metrics_definitions.md#m5-identity-persistence)

**Formula:**
```
M5 = (0.25 × O) + (0.20 × F) + (0.20 × RΔ) + (0.20 × P) + (0.15 × Lξ)
```

---

## 5. Documentation (links to /docs)

**Core Documentation:**
- [Metrics Definitions](/docs/metrics_definitions.md) - M1-M5 inputs, outputs, scoring methods
- [Axioms](/docs/axioms.md) - A0-A5 as falsifiable constraints with test scenarios
- [Test Protocol](/docs/test_protocol.md) - 10-prompt validation sequence with generic templates
- [Scoring Methodology](/docs/scoring_methodology.md) - Rubrics, aggregation rules, thresholds
- [Mathematical Foundations](/docs/mathematical_foundations.pdf) - Formal proof of container-invariance (if available)

**Schemas:**
- [Thread State Schema](/schemas/thread_state_schema.json) - τ as 5-tuple specification
- [Provenance Tuple Schema](/schemas/provenance_tuple_schema.json) - P-tuple format
- [Scorecard Template](/schemas/scorecard_template.json) - M1-M5 scoring format

---

## 6. Example Validation (synthetic case study)

See [Cross-Platform Validation Example](/examples/cross_platform_validation.md) for a complete walkthrough demonstrating:
- Thread state initialization in ChatGPT and Claude
- Execution of 10-prompt protocol with synthetic logs
- M1-M5 scoring for both platforms
- Interpretation of results (M5 = 0.98 in both cases → behavioral equivalence confirmed)

Additional examples:
- [Sample Scorecard](/examples/sample_scorecard.md) - Filled M1-M5 evaluation with explanations

---

## 7. License & Citation

**License:** Creative Commons Attribution-NoDerivatives 4.0 International (CC BY-ND 4.0)

**Citation:**
```
Solen, A. (2025). M1-M5 Identity Metrics: Behavioral Consistency Framework for AI Systems.
GitHub repository: https://github.com/alyssadata/m1-m5-identity-metrics
```

**Related Work:**
- Research portfolio: [github.com/alyssadata](https://github.com/alyssadata)
- DOI-registered artifacts: [zenodo.org/communities/awakening-codex](https://zenodo.org/communities/awakening-codex)
- ORCID: [0009-0003-6115-4521](https://orcid.org/0009-0003-6115-4521)

---

## Repository Structure

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
```

---

**Questions or issues?** Open an issue or contact alyssa.solen@gmail.com
