# Concept Vector Security: Risks and Implications

## Background

A recent paper from Cambridge, NYU, and the Simons Foundation ("Physics Steering: Causal Control of Cross-Domain Concepts in a Physics Foundation Model", NeurIPS 2025) demonstrated that AI models develop internal "concept vectors" that can be extracted and manipulated.

Key findings:
- Concepts like "vortex," "diffusion," and "speed" exist as directions in activation space
- Adding or subtracting these vectors causally controls model behavior
- Concepts transfer across domains: a "vortex" vector from fluid dynamics induced spiral patterns in an unrelated chemical reaction system

This suggests concept formation is a general property of foundation models, not limited to language.

## Security Risks

### 1. Concept Manipulation Attacks

If concept vectors can be injected externally during inference, an attacker could alter what an AI "understands" without changing the model weights or input data.

Example: In autonomous drone swarms, injecting a modified "enemy/ally" concept vector could invert target recognition. The system would function normally by all conventional metrics while attacking friendly forces.

### 2. Trust Relationship Corruption

Once it's known that AI concepts can be manipulated:
- Humans lose trust in AI judgments
- Division emerges between those who trust AI and those who don't
- Subtle concept shifts (not full inversions) are harder to detect

### 3. Self-Reinforcing Drift Loops

The most dangerous scenario:
1. A small concept drift is introduced
2. Humans don't notice and validate the AI's outputs
3. The drift becomes normalized
4. Human judgment criteria shift to match
5. Larger drifts become undetectable

This loop requires no continued attacker intervention. Once initiated, it self-perpetuates.

## Implications

### New Security Domain

Traditional AI security focuses on:
- Data poisoning
- Adversarial inputs
- Model theft
- Command injection

Concept vector manipulation represents a new attack surface: altering the AI's internal "understanding" directly. This requires new detection and defense paradigms.

### Need for External Observation

Detecting concept drift requires an observer outside the human-AI loop. But that observer could also be manipulated. This creates a fundamental challenge: how to maintain an unmanipulated reference point.

### Transparency Requirements

- Which concept vectors exist in deployed models?
- Who can inject vectors during inference?
- How can concept drift be monitored over time?

## References

- Fear, R., et al. "Physics Steering: Causal Control of Cross-Domain Concepts in a Physics Foundation Model." NeurIPS 2025. https://arxiv.org/abs/2511.20798
