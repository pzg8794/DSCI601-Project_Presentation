# Approach report assets

This folder contains presentation-ready approach slides derived from the original approach report in `DSCI601-Project_Proposal/approach_report/approach-writeup.tex`.

The approach is intentionally kept consistent with the original report:

- clinical resource allocation and quantum-network routing are treated as structurally comparable routing problems
- the shared failure mode is missing, noisy, delayed, or excluded context
- the method comparison spans MAB, CMAB, and iCMAB
- the evaluation model follows four phases: Environment, Context Observation, Routing Decision, and Evaluation/Mitigation
- the implementation uses a shared modular evaluation pipeline for both domains

Use `approach_slides.tex` inside `main.tex` with:

```tex
\input{approach_report/approach_slides.tex}
```
