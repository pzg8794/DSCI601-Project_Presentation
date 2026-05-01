# Final Presentation Review: Acronyms, Citations, Grammar, and Color Symmetry

This is a review aid for the final Beamer deck. It does not replace `main.tex`; it documents the required cleanup so the final pass can be applied safely without disrupting the Overleaf/repo state.

## Acronym handling

Recommended deck convention: define acronyms in a tiny gray footer the first time they appear, or whenever a slide contains several acronyms. Keep definitions in the footer rather than expanding every bullet.

Suggested macro:

```latex
\newcommand{\slidefoot}[1]{\vspace{0.25em}{\tiny\color{gray!75}\raggedright #1\par}}
```

Recommended definitions:

| Acronym | Definition |
|---|---|
| MAB | Multi-armed bandit |
| CMAB | Contextual multi-armed bandit |
| iCMAB | Informative contextual multi-armed bandit |
| SDS | Sequential decision system |
| EQUITAS | Project fairness mediation layer / EQUITAS-style audit and mitigation boundary |
| RQ | Research question |
| COVID | Coronavirus disease 2019 |
| NEJM | New England Journal of Medicine |
| JAMA | Journal of the American Medical Association |
| RIT | Rochester Institute of Technology |
| DSCI | Data Science course/project context |
| GitHub | Source-control and code-review platform |
| GCP | Google Cloud Platform |
| CLI | Command-line interface |
| CSV | Comma-separated values |
| JSON | JavaScript Object Notation |
| PHI | Protected health information |
| CI | Continuous integration |
| UCB | Upper confidence bound |
| API | Application programming interface |
| DOI | Digital object identifier |

## Slide-level footer recommendations

Add these only where the acronym or source load is high. Do not overload every slide.

### Project Overview

```latex
\slidefoot{Acronyms: SDS = sequential decision system; MAB = multi-armed bandit; CMAB = contextual multi-armed bandit; iCMAB = informative contextual multi-armed bandit. Sources: Auer et al. (2002); Li et al. (2010); Lattimore and Szepesvari (2020).}
```

### Why This Project Matters

```latex
\slidefoot{Clinical sources: Sjoding et al. (2020); Fawzy et al. (2022). Quantum-routing motivation: Wehner et al. (2018); Pant et al. (2019); Garcia project quantum-routing materials.}
```

### Updated Domain Model

```latex
\slidefoot{Acronyms: SDS = sequential decision system; MAB/CMAB/iCMAB = non-contextual, contextual, and informative contextual bandit policy families. Source: DSCI601 approach report and current workspace implementation.}
```

### Why the Domain Model Changed

```latex
\slidefoot{Source: DSCI601 approach report and workspace architecture updates; the simplified view summarizes the four-phase model used in the detailed domain slide.}
```

### Why MAB, CMAB, and iCMAB

Already added in `approach_report/approach_slides.tex`:

```latex
\slidefoot{Acronyms: MAB = multi-armed bandit; CMAB = contextual multi-armed bandit; iCMAB = informative contextual multi-armed bandit; RQ = research question. Sources: Auer et al. (2002); Li et al. (2010); DSCI601 approach report and workspace implementation.}
```

### Updated Architecture Overview

```latex
\slidefoot{Acronyms: EQUITAS = fairness audit/mitigation boundary. Source: architecture diagram and current DSCI601 workspace implementation.}
```

### Architecture Layer 1: Research Context

```latex
\slidefoot{Clinical evidence: Sjoding et al. (2020, NEJM); Fawzy et al. (2022, JAMA Internal Medicine). Simulation evidence: DSCI601 clinical smoke/reporting artifacts.}
```

### Architecture Layer 2: Control and Validation

```latex
\slidefoot{Acronyms: RunSpec/FairnessSpec/ProvenanceSpec = run, fairness, and provenance contracts; CSV = comma-separated values; JSON = JavaScript Object Notation. Source: DSCI601 workspace fairness workflow and persistence code.}
```

### Architecture Layer 3: Execution

```latex
\slidefoot{Acronyms: GCP = Google Cloud Platform; EQUITAS = fairness mediation boundary. Source: DSCI601 workspace clinical experiment path and legacy quantum sidecar path.}
```

### Architecture Layer 4: Policy, Allocation, and Mediation

```latex
\slidefoot{Acronyms: UCB = upper confidence bound; EQUITAS = fairness mediation boundary. Source: DSCI601 workspace clinical model registry, allocator, and mediator code.}
```

### Architecture Layer 5: Artifacts and Reporting

```latex
\slidefoot{Acronyms: CSV = comma-separated values; JSON = JavaScript Object Notation. Source: DSCI601 workspace FairnessWorkflow and FairnessArtifactWriter.}
```

### GitHub Code Review Break

```latex
\slidefoot{Acronyms: GitHub = source-control/code-review platform; RunSpec = run contract; EQUITAS = fairness mediation boundary. Source: DSCI601 workspace code walkthrough guide.}
```

### Next Semester: Architecture Completion

```latex
\slidefoot{Acronyms: EQUITAS = fairness mediation boundary. Scope note: current system is smoke-tested with preliminary artifacts; full cross-testbed/cross-domain experiment battery remains future work.}
```

## Grammar and wording fixes

Apply these edits in `main.tex`:

1. Presentation plan: replace `MAB/CMAB/iCMAB comparison` with `MAB, CMAB, and iCMAB comparison` for readability.
2. Layer 3 status: replace `But we need to scale` with `Remaining work: scale`.
3. Layer 4 role: replace the semicolon before `the allocator` with a comma or new sentence.
4. Layer 4 component name: replace `ClinicalDfltResourceAllocator` with `ClinicalDefaultResourceAllocator` unless the shortened form is intentional for width.
5. Code review block: replace `Walkthrough guide, the code files include...` with `The walkthrough guide links to code files that include...`.
6. Next semester: replace `paper-grade validation hub` with `paper-ready validation hub` for a less awkward phrase.
7. Selected references: rename to `References` if it is intended to be complete; keep `Selected References` only if the deck is not claiming full bibliography coverage.

## Color symmetry checks

Keep the same color semantics across the whole deck:

| Meaning | Color |
|---|---|
| Environment / research context | `phase1blue` |
| Context quality / missingness | `phase2green` or `softred` when signaling risk |
| Decision / policy | `phase3orange` or `ritorange!18` |
| Evaluation / artifacts / reporting | `phase4purple` |
| Risk / disparity | `softred!18` |
| Positive/observed feedback | `softgreen!18` |

The current approach table already follows this pattern. The architecture layers mostly follow it. The main exception is the simplified domain comparison, where `Observed Context` is red because it emphasizes risk; that is acceptable.

## References that should appear in the final reference slide

Use a compact 2-column or tiny-font references slide if needed.

1. Auer, P., Cesa-Bianchi, N., and Fischer, P. (2002). Finite-time analysis of the multiarmed bandit problem. Machine Learning, 47, 235--256.
2. Li, L., Chu, W., Langford, J., and Schapire, R. E. (2010). A contextual-bandit approach to personalized news article recommendation. WWW 2010.
3. Lattimore, T., and Szepesvari, C. (2020). Bandit Algorithms. Cambridge University Press.
4. Sjoding, M. W., Dickson, R. P., Iwashyna, T. J., Gay, S. E., and Valley, T. S. (2020). Racial bias in pulse oximetry measurement. New England Journal of Medicine, 383(25), 2477--2478. doi:10.1056/NEJMc2029240.
5. Fawzy, A., Wu, T. D., Wang, K., et al. (2022). Racial and ethnic discrepancy in pulse oximetry and delayed identification of treatment eligibility among patients with COVID-19. JAMA Internal Medicine, 182(7), 730--738. doi:10.1001/jamainternmed.2022.1906.
6. Wehner, S., Elkouss, D., and Hanson, R. (2018). Quantum internet: A vision for the road ahead. Science, 362(6412), eaam9288.
7. Pant, M., Krovi, H., Towsley, D., et al. (2019). Routing entanglement in the quantum internet. npj Quantum Information, 5, 25.
8. DSCI601 Project Proposal: approach report, architecture report, rough draft report, and clinical evidence analysis artifacts.
9. DSCI601 Workspace: clinical experiment path, legacy quantum sidecar path, fairness workflow, artifact writer, reporting notebooks, and code walkthrough guide.

## Notes on citation completeness

- The current deck has one citation line on the research-context image slide and a short selected reference slide. That is not enough if the final deck claims full citation coverage.
- The safest presentation approach is to add short source footers to evidence-heavy slides and keep a final references slide with all cited works.
- Code/framework claims can cite the DSCI601 workspace and project proposal materials instead of external papers.
- Clinical evidence claims should cite Sjoding et al. (2020) and Fawzy et al. (2022).
- Bandit-method claims should cite Auer et al. (2002), Li et al. (2010), and Lattimore and Szepesvari (2020).
- Quantum-routing motivation should cite Wehner et al. (2018), Pant et al. (2019), and the project quantum-routing materials.
