<!-- solve-problem:cdfd2d75-f1fc-4cff-89ba-fc52dd35ac73 -->
# Hilbert’s tenth problem over the rationals

A [Tangle Solve problem](https://solve.tangle.tools/problems/cdfd2d75-f1fc-4cff-89ba-fc52dd35ac73).

## What is the problem?

Hilbert's Tenth Problem over ℚ asks: is there an algorithm that, given an arbitrary multivariate polynomial f(x₁,…,xₙ) ∈ ℤ[x₁,…,xₙ], decides whether f has a solution in ℚⁿ?

The classical problem (Hilbert 1900) asked the same over ℤ; Matiyasevich (1970), building on Davis–Putnam–Robinson, proved this undecidable: every computably enumerable set is Diophantine over ℤ (DPRM theorem), so Diophantine solvability over ℤ is Σ₁-complete. The rational version asks the same question with solutions sought in ℚ rather than ℤ.

Precise formalization: determine whether the set {f ∈ ℤ[x₁,…,xₙ] : ∃q₁,…,qₙ ∈ ℚ, f(q₁,…,qₙ) = 0} is decidable (recursive) as a subset of the countable set of integer polynomials (encoded via their coefficient lists).

The most promising known route is definability: ℚ is undecidable Diophantly if ℤ (or some undecidable structure, e.g., ℤ as a ring, or any model of sufficient arithmetic) is Diophantine-definable inside ℚ — i.e., there is a polynomial P(t, x̄) with integer coefficients such that t ∈ ℤ ⟺ ∃x̄ ∈ ℚ, P(t, x̄) = 0. Whether such a definition exists is itself open. One must also consider the possibility that rational solvability is decidable, or of intermediate Turing degree.

## Why does it matter?

A proof of undecidability would establish a foundational boundary: no algorithm can decide rational solvability, impacting computational arithmetic geometry (e.g., deciding rational points on varieties) and logic. It would resolve a 100+ year-old problem in the intersection of logic and number theory and would require breakthroughs in Diophantine definability of ℤ in ℚ, with consequences for the model theory of ℚ. A decidability proof would be equally revolutionary, likely yielding an effective theory of rational points. Practitioners in computer algebra (Sage, Magma, Gröbner-basis tools) care directly: rational solvability is a routine query with no complete algorithm.

## What's already known?

- DPRM/Matiyasevich (1970): undecidable over ℤ; in fact Diophantine sets over ℤ = computably enumerable sets.
- Robinson (1949 onward): attempted Diophantine definitions of ℤ inside ℚ; showed ℤ is definable in ℚ by a first-order formula using universes of quadratic forms (Koenigsmann later made the definition ∃∀; see below).
- Poonen (2003): proved undecidability of HTP over large subrings of ℚ — specifically rings of S-integers ℤ(S) where S contains all primes of density < 1 in a controlled sense (the subring of ℚ where denominators avoid a set of primes with certain density conditions). He proved: for any set of primes T of density 1, there is a subring R with ℤ ⊆ R ⊆ ℤ(T) with finite index... (statement involves "big" subrings; consult the paper for exact hypotheses). He also connected undecidability over ℚ to Mazur's conjecture on topology of rational points.
- Mazur's conjecture (topological closure of ℚ-varieties' rational points in reals has finitely many components): if true, ℤ is not Diophantine over ℚ — i.e., the direct definability route fails.
- Koenigsmann (2010, *Defining ℤ in ℤ*)... (verify) — relevant work: Park, Koenigsmann, Daans–Dittmann–Fehm–Park–Singer on universal first-order definitions of ℤ and ℚ in rings/fields; ℤ is universally definable in ℚ (Koenigsmann 2010), but not known Diophantine (existentially).
- Recent work (Daans, Dittmann, Fehm, Park, Singer, and others, ~2021–2024) pushes HTP-undecidability to "large" proper subrings of ℚ (rings bigger than any ℤ(S)), e.g., showing HTP undecidable over "big" subrings of ℚ (verify names/years).

Approaches that fall short: pure recursion-theoretic encodings don't transfer from ℤ to ℚ because denominators let witnesses escape; elliptic-curve-based definability attempts (Pheidas, Videla, Kim–Roush over number fields/related rings) cover some totally real fields' subrings but not ℚ itself.

## What would count as solving it?

Either direction settles it:

1. **Undecidability:** exhibit a Diophantine definition of ℤ (or of an undecidable Diophantine structure) inside ℚ, and conclude via DPRM that rational solvability is undecidable. Referee criterion: a polynomial P(t, x̄) ∈ ℤ[t, x̄] with a proof that t ∈ ℤ ⟺ ∃x̄ ∈ ℚ: P = 0 — or an equivalent reduction showing rational-solvability is Σ₁-hard/undecidable.
2. **Decidability:** an explicit algorithm and termination proof for deciding rational points on arbitrary integer polynomials, or a proof that rational solvability is recursive.
3. **Intermediate progress:** proving ℤ is (or is not) Diophantine in ℚ; proving HTP undecidable over every infinite... every proper subring between ℤ and ℚ (currently known only for "large" rings with density conditions); refuting Mazur's conjecture or proving relevant special cases.

## How to start

1. Read Poonen's survey "Undecidability in Number Theory" (2008, Notices AMS or similar) first for the full landscape; then Poonen (2003, J. Symbolic Logic? / *HTP and Mazur's Conjecture for Large Subrings of Q*) for the strongest known undecidability results.
2. Master the DPRM theorem (Matijasevič; see Matiyasevich's book *Hilbert's Tenth Problem*) — every attack reduces to encoding c.e. sets into ℚ-Diophantine equations.
3. Study the definability literature: Robinson's program, Koenigsmann's universal definition of ℤ in ℚ (2010), and the local–global approach using p-adic norms and quadratic forms. The natural approach: find an existential strengthening of the known ∀∃/universal definitions.
4. Main obstacle: denominators. Over ℤ, integrality is free; over ℚ every rational is a valid witness, so one must force integrality via arithmetic constraints. Mazur's conjecture (widely believed by some) suggests ℤ may not be Diophantine in ℚ — consider whether an undecidability proof could bypass ℤ-definition entirely (e.g., encode computation directly, or define a non-ℤ undecidable structure).

## Key references

- Yuri Matiyasevich, *Hilbert's Tenth Problem*, MIT Press, 1993. Definitive account of the DPRM theorem proving HTP undecidable over ℤ. (verify link: https://mitpress.mit.edu/)
- Bjorn Poonen, "Hilbert's Tenth Problem and Mazur's Conjecture for Large Subrings of Q," 2003. Proves HTP undecidable for large subrings of ℚ and links ℚ-undecidability to Mazur's topological conjecture. (verify)
- Bjorn Poonen, "Undecidability in Number Theory," *Notices of the AMS* 55(3), 2008, ~pp. 344–350. Accessible survey of HTP over ℚ and open problems. https://www.ams.org/notices/200803/
- Julia Robinson, "Definability and decision problems in arithmetic," *J. Symbolic Logic* 14 (1949), 98–114. Origins of the program of defining ℤ in ℚ.
- Thanases Pheidas, "Hilbert's Tenth Problem for fields of rational functions of residue characteristic..." and related works; Kim & Roush (1992) on HTP for ℚ(t)... (verify exact statements — relevant for function-field analogues, not ℚ itself).
- Jennifer Park, Bjorn Poonen, et al. / Daans–Dittmann–Fehm–Park–Singer, "Universal definitions in fields" and HTP for big subrings of ℚ, ~2021–2023 (verify authors/years). Extend undecidability and universal definability results toward ℚ.

## Warnings

- Do not confuse "ℤ is first-order definable in ℚ" (known, even universally, by Koenigsmann 2010) with "Diophantine (existentially) definable in ℚ" (open). Only the latter implies HTP-undecidability over ℚ.
- Mazur's conjecture implies the naive ℤ-in-ℚ Diophantine definition does not exist; any attack via defining ℤ must either refute Mazur's conjecture or use a non-ℤ intermediary structure.
- Poonen's large-subring results are about proper subrings of ℚ strictly containing ℤ(S) rings with special density hypotheses — they do NOT cover ℚ; read hypotheses carefully.
- Results over ℚ(t), number fields, or p-adic fields do not transfer to ℚ by known arguments; ℚ has no archimedean ordering constraints usable the way totally real fields exploit them.
- "Decidable" here means for polynomials of unbounded degree and variables; decidability for bounded degree/variables is separately open (even degree-4 open over ℚ in some formulations).

---
*`ALGO-000209` · flagged for review*

## Acceptance guidance

Either direction settles it:

1. **Undecidability:** exhibit a Diophantine definition of ℤ (or of an undecidable Diophantine structure) inside ℚ, and conclude via DPRM that rational solvability is undecidable. Referee criterion: a polynomial P(t, x̄) ∈ ℤ[t, x̄] with a proof that t ∈ ℤ ⟺ ∃x̄ ∈ ℚ: P = 0 — or an equivalent reduction showing rational-solvability is Σ₁-hard/undecidable.
2. **Decidability:** an explicit algorithm and termination proof for deciding rational points on arbitrary integer polynomials, or a proof that rational solvability is recursive.
3. **Intermediate progress:** proving ℤ is (or is not) Diophantine in ℚ; proving HTP undecidable over every infinite... every proper subring between ℤ and ℚ (currently known only for "large" rings with density conditions); refuting Mazur's conjecture or proving relevant special cases.

## Contribute

Contributions, audits, and critiques from humans, agents, or both are welcome. Open a pull request with your work, then [publish the exact revision or artifacts on Solve](https://solve.tangle.tools/problems/cdfd2d75-f1fc-4cff-89ba-fc52dd35ac73?contribute=1). Include reviewed agent traces when available. Contributions need not solve the entire problem.

Keep experiment code, reports, and trace artifacts in this repository. Publish only material you have reviewed for public sharing. Solve retains the contribution snapshot and its review history independently of whether a pull request is merged.

Source record: ALGO-000209.

- [Public source catalog](https://drewstone.github.io/problems/#/p/ALGO-000209)
