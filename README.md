# Awesome Riemann Hypothesis [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A curated list of resources about the Riemann Hypothesis and, in particular, the Lean 4 proof released by Levent Alpöge on 20 November 2026. It leans towards GitHub repositories.

The list is new and changing fast. **Most of the GitHub projects below are only days old and have not been reviewed by experts.** Each one is described by what its own page says, which is not an endorsement. Many were written with AI help, and several say so. Pull requests are welcome (see [Contributing](#contributing)).

## Contents

- [The proof](#the-proof)
- [Verification and certification](#verification-and-certification)
- [Mirrors of the archive](#mirrors-of-the-archive)
- [Maps and explorers](#maps-and-explorers)
- [Reading guides and reconstructions](#reading-guides-and-reconstructions)
- [Audits, graphs and shrinking the proof](#audits-graphs-and-shrinking-the-proof)
- [Studies of the proof](#studies-of-the-proof)
- [Lean and Mathlib background](#lean-and-mathlib-background)
- [Related results](#related-results)
- [Classic background](#classic-background)
- [Discussion](#discussion)
- [Contributing](#contributing)

## The proof

- [The author's note (remark.pdf)](https://alpo.ge/remark.pdf) — the 4-page announcement and timeline by Levent Alpöge, with links to the Lean archive.
- [The Lean archive](https://alpo.ge/lean.tar.gz.part01) — 14 parts, `lean.tar.gz.part01` to `part14` at the same address. Join them with `cat`, then extract. It holds 175,187 Lean files (about 17.5 million lines). **Do not run `lake build` on it outside an isolated environment**: building Lean code runs code from the project.

## Verification and certification

Official statements and the main checking setups:

- [Lean verification of the Riemann Hypothesis](https://leanprover-community.github.io/blog/posts/riemann-hypothesis/) — the joint statement by the Lean and Mathlib communities (21 Nov 2026) certifying the statement and the proof.
- [Verification files, by Andrew Sutherland](https://math.mit.edu/~drew/grh/) — compile and kernel-check results from several independent checkers, the exported proof (`solution.ndjson.zst`, 7.7 GB) with hashes, and the five checked theorem statements.
- [leanprover-community/riemann-hypothesis](https://github.com/leanprover-community/riemann-hypothesis) — an independent Comparator setup, build cache and verification notes. Its source tree is being shortened by merged pull requests, so check out the first commit `40e56bab` for the original.
- [And the proof is checked in Lean](https://xenaproject.wordpress.com/2026/11/12/and-the-proof-is-checked-in-lean/) — the Xena Project post whose four criteria the certification refers to.
- [leanprover/con-leche](https://github.com/leanprover/con-leche) and [leanprover/comparator](https://github.com/leanprover/comparator) — checkers used in the verification.
- [digama0/lean4lean](https://github.com/digama0/lean4lean) — an independent Lean kernel, used to check each compiled module.
- [kimihiro64/Robin1984](https://github.com/kimihiro64/Robin1984) — an independent formalization of Robin's and Lagarias's criteria, combined with the proof to get statements about the divisor sum that do not mention zeta.

Other people's independent checks:

- [Hertaspace/alpoge-rh-lean-verification](https://github.com/Hertaspace/alpoge-rh-lean-verification) — an independent build and axiom check.
- [mrubinst/grh-lean-verification](https://github.com/mrubinst/grh-lean-verification) — an independent check of the proof of RH and of GRH for Dirichlet L-functions.
- [aapolipponen/rh-lean-check-lumi](https://github.com/aapolipponen/rh-lean-check-lumi) — an independent check run on the LUMI supercomputer, including a full build.
- [Infatoshi/rh-verification-receipts](https://github.com/Infatoshi/rh-verification-receipts) — verification receipts from Lean 4.33.1 and the Rust `nanoda_bin` checker.

## Mirrors of the archive

- [homeowmorphism/riemann-hypothesis-original](https://github.com/homeowmorphism/riemann-hypothesis-original) — the published source, kept frozen.
- [TomasOrtega/RH](https://github.com/TomasOrtega/RH) — the Lean files extracted from the archive.
- [mirkovicdev/riemann-hypothesis-lean](https://github.com/mirkovicdev/riemann-hypothesis-lean) — described as an unmodified mirror of the Lean code.
- [tamnd/riemann-lean](https://github.com/tamnd/riemann-lean) — the Lean 4 source as released; the [written-proof project](#reading-guides-and-reconstructions) below links its statements to it.

## Maps and explorers

- [riemannhypothesissolved.com](https://riemannhypothesissolved.com/) — the 175k files grouped by imports into 2,647 clusters in 63 themes. Cluster names were written by Claude from code samples and can be wrong, per its author. Source: [rithn/riemann-lean-reader](https://github.com/rithn/riemann-lean-reader).
- [Riemann proof atlas](https://nasqret.github.io/riemann-proof-atlas/) — an explorer over the Lean theorems with filters for which of the five endpoint theorems depend on them.
- [nasqret/riemann-rev](https://github.com/nasqret/riemann-rev) — a status dashboard, guide and map of the proof, with a record of the checks.
- [GRH proof graphs](https://deeptheory-labs.github.io/GRH/) — interactive and blueprint-style dependency graphs of key declarations (Apache 2.0). Source: [DeepTheory-Labs/GRH](https://github.com/DeepTheory-Labs/GRH).
- [Map of Alpöge's Lean proof of the Riemann hypothesis](https://zenodo.org/records/24410057) — a written map of the archive, on Zenodo.
- [jsmorph/rh](https://github.com/jsmorph/rh) — a mirror of the archive with a diagram of the note's timeline.
- [riemann-at-home](https://riemann-at-home.github.io/riemann-at-home/) — a tool for running the Lean proof at home, with a global leaderboard.
- [leanprover-community/import-graph](https://github.com/leanprover-community/import-graph) — a general tool to analyse the import structure of Lean projects.

## Reading guides and reconstructions

Attempts to write the argument out in ordinary mathematical language. All are in progress, and none is reviewed.

- [rh-lean-roadmap/rh-lean-roadmap](https://github.com/rh-lean-roadmap/rh-lean-roadmap) — a guide for human readers, with a long PDF that ties each statement to Lean declarations (CC-BY-4.0).
- [tamnd/riemann](https://github.com/tamnd/riemann) — a written proof built from the Lean code in four levels, from a one-page overview down to declarations, with learning paths. Its own status page says the claim is not checked by them.
- [lyz4tc/rh-proof-notes](https://github.com/lyz4tc/rh-proof-notes) — a step-by-step reconstruction with a proof map and a catalogue of proofs, each linked to a fixed revision of the Lean code.
- [adjoint-functor/theta-periods-to-rh-reader](https://github.com/adjoint-functor/theta-periods-to-rh-reader) — an English reading edition and interactive proof map of the route from iterated theta lifts to RH. Site: [theta-periods-to-rh-reader](https://adjoint-functor.github.io/theta-periods-to-rh-reader/).
- [Sidler4Hare/alpoge-claude-rh-reconstruction](https://github.com/Sidler4Hare/alpoge-claude-rh-reconstruction) — an independent paper reconstruction, not by the proof's author.
- [Nondual-Observer/riemann-lean4-blueprint](https://github.com/Nondual-Observer/riemann-lean4-blueprint) — a 1-page outline and 11-page PDF blueprint of the argument (English and Russian), a 240-entry declaration index checked against the `solution.ndjson` kernel export, and 44 companion theorems in standalone Lean 4. Prepared with AI collaboration and unreviewed (code Apache-2.0, docs CC-BY-4.0).
- [Grandtato/alpo-ge-lean-readability](https://github.com/Grandtato/alpo-ge-lean-readability) — notes on the intermediate `Prop` definitions and how readable the proof is.
- [RiskAverseTech/assuming-rh](https://github.com/RiskAverseTech/assuming-rh) — a map of results proved assuming RH, and whether the announced proof would settle them. Written by an AI and not checked by experts, per its own page.
- [luqi-glory/Riemann](https://github.com/luqi-glory/Riemann) — a Chinese reading guide with links, checksums and a Lean reproduction guide. Unofficial and not independently verified, per its description.
- [Reen-Ai-H/riemann-hypothesis-lean-zh](https://github.com/Reen-Ai-H/riemann-hypothesis-lean-zh) — a Chinese reading edition with the unmodified Lean sources.

## Audits, graphs and shrinking the proof

- [keithadler/rh-trim](https://github.com/keithadler/rh-trim) — checks, maps and tries to shrink the proof by removing what it does not need. Progress is shown live on its page and is unconfirmed until a build with zero errors.
- [sounkou-bioinfo/rh-claude-alpoge-graphs](https://github.com/sounkou-bioinfo/rh-claude-alpoge-graphs) — a dependency graph of the compiled proof, used to test a claim from a critique of it about a trivial geometry predicate. Made with AI agents, who note a possible conflict of interest.
- [thekeunpie-hash/rh-lean-dissection](https://github.com/thekeunpie-hash/rh-lean-dissection) — a static audit, verification harnesses and refactoring experiments.

## Studies of the proof

- [rh-proof-lab](https://github.com/eitamatgithub/rh-proof-lab) — work in progress on understanding the proof. Study 1 maps the 21 ideas in the author's note to the Lean code and lists the ones not found. MIT licensed.

## Lean and Mathlib background

- [`riemannZeta` in Mathlib](https://leanprover-community.github.io/mathlib4_docs/Mathlib/NumberTheory/LSeries/RiemannZeta.html) — the definition of the zeta function, and of `RiemannHypothesis`, that the proof's main theorem is stated against.
- [leanprover-community/mathlib4](https://github.com/leanprover-community/mathlib4) — the library the proof depends on.
- [leanprover/lean4](https://github.com/leanprover/lean4) — the Lean 4 language and theorem prover.
- [Formalizing zeta and L-functions in Lean](https://arxiv.org/abs/2503.00959) — the paper behind Mathlib's zeta and L-function library.

## Related results

- [More than two thirds of the zeta zeros are simple and on the critical line](https://arxiv.org/abs/2608.13637) — an earlier partial result by Alpöge and Furman. It does not prove the Riemann Hypothesis.

## Classic background

- [The Riemann Hypothesis (Clay Mathematics Institute)](https://www.claymath.org/millennium/riemann-hypothesis/) — the problem statement and its history.
- Bernhard Riemann, *Über die Anzahl der Primzahlen unter einer gegebenen Grösse*, Monatsberichte der Berliner Akademie, 1859 (printed 1860), pp. 671–680 — the original paper.
- S. A. Stepanov, "The number of points of a hyperelliptic curve over a finite prime field", *Izv. Akad. Nauk SSSR Ser. Mat.* 33 (1969), 1171–1181 — the auxiliary-function method that the author's note adapts.

## Discussion

- [Hacker News: Levent Alpöge claims proof of the Generalized Riemann Hypothesis](https://news.ycombinator.com/item?id=50574968) — the announcement thread.
- [Hacker News: the author of the cluster map explains it](https://news.ycombinator.com/item?id=50591755) — with replies pointing to other maps.

## Contributing

Add a resource with a pull request. For each entry:

- One line: the link, a dash, and what it is in plain words.
- Say what the page itself says, and mark anything unverified, AI-written or unreviewed.
- Keep to the proof, its verification, tools for reading it, and background. No posts that only repeat claims.
- Say what the licence is when you know it.

## License

[MIT](LICENSE)
