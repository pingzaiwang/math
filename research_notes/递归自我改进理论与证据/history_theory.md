# Recursive Self-Improvement (RSI): Conceptual History and Theoretical Limits

Note on method: I opened every primary source cited below. PDFs were downloaded and converted to text (pdftotext), and quotations were checked against that text. Anything marked **[UNVERIFIED]** comes from memory or from an aggregator, and the report writer should treat it with caution. URLs are for the versions actually read.

---

## Q1. Origins: I.J. Good 1965 and precursors (Turing, von Neumann/Ulam, Vinge)

### Takeaway
Good (1965) gives the canonical "intelligence explosion" argument in one paragraph. If a machine surpasses every human intellectual activity, it surpasses machine design too, so it designs better machines, and the explosion follows "unquestionably". His argument is a verbal one-step induction. It contains no growth-rate model, and later work (Yudkowsky 2013) reframes the open question as one about *returns on cognitive reinvestment*.

### Cited Findings
- Good's passage, verbatim as reproduced by Yudkowsky: "Let an ultraintelligent machine be defined as a machine that can far surpass all the intellectual activities of any man however clever. Since the design of machines is one of these intellectual activities, an ultraintelligent machine could design even better machines; there would then unquestionably be an 'intelligence explosion,' and the intelligence of man would be left far behind. Thus the first ultraintelligent machine is the last invention that man need ever make." — [Yudkowsky 2013, IEM §1, p.1](https://intelligence.org/files/IEM.pdf)
- Bibliographic data: Good, I. J. 1965. "Speculations Concerning the First Ultraintelligent Machine." In *Advances in Computers*, Vol. 6, ed. Franz L. Alt and Morris Rubinoff, pp. 31–88. New York: Academic Press. doi:10.1016/S0065-2458(08)60418-0. — [IEM references](https://intelligence.org/files/IEM.pdf)
  - Date conflict: Yampolskiy dates Good's paper to **1966** ("interestingly in the same year, 1966") and groups it with Minsky and von Neumann. — [Yampolskiy 2015, arXiv:1502.06512](https://arxiv.org/abs/1502.06512). The volume is usually cited as 1965. **[UNVERIFIED] My recollection is that the volume carries a 1965 copyright and physically appeared in 1966.**
- The sentence that follows "last invention" in Good's original continues with the caveat "provided that the machine is docile enough to tell us how to keep it under control." Wikipedia also paraphrases Good as predicting that an ultraintelligent machine was more likely than not to be built in the 20th century. — [Wikipedia, "Technological singularity" (pointer only)](https://en.wikipedia.org/wiki/Technological_singularity). **I could not open Good's original PDF (incompleteideas.net returned HTTP 503), so the caveat and the prediction are verified only via Wikipedia.**
- Von Neumann/Ulam: Wikipedia attributes to Stanislaw Ulam's 1958 tribute to von Neumann a conversation "centered on the accelerating progress of technology and changes in human life", which mentions an essential "singularity". — [Wikipedia](https://en.wikipedia.org/wiki/Technological_singularity). **The primary source (Ulam, "John von Neumann 1903–1957", Bull. AMS 64(3), 1958) could not be retrieved because the AMS PDF download failed. [UNVERIFIED in primary]**
- Turing as precursor (child machine and self-education rather than an explosion). Yampolskiy quotes Turing 1950: "Instead of trying to produce a programme to simulate the adult mind, why not rather try to produce one which simulates the child's? If this were then subjected to an appropriate course of education one would obtain the adult brain…" — [Yampolskiy 2015 §1](https://arxiv.org/abs/1502.06512)
- **[UNVERIFIED]** Turing's 1951 lecture "Intelligent Machinery, A Heretical Theory" says that "at some stage therefore we should have to expect the machines to take control." I did not open this source.
- **[UNVERIFIED in primary]** Vinge's 1993 essay "The Coming Technological Singularity" predicted greater-than-human intelligence between 2005 and 2030 (per [Wikipedia](https://en.wikipedia.org/wiki/Technological_singularity)).

### Inferences
- Good's argument assumes that "design of machines" is one capability among others and that surpassing humans at it yields *iterated* improvement. Neither the speed nor the boundedness of the iteration is addressed. "Unquestionably" is the step later critics attack (IEM: "Many have since gone on to question Good's unquestionable").
- Turing's precursor concerns learning, not self-redesign. Calling Turing an "RSI" originator stretches what he wrote.

### Gaps
- I did not read Good's full original text, Ulam 1958 or Turing 1951 directly.

---

## Q2. Schmidhuber's Gödel machine, OOPS, and Hutter's AIXI

### Takeaway
A Gödel machine is a self-referential program that contains a proof searcher. The machine executes a self-rewrite ("switchprog") only once it has proved, in an axiomatized formal system A that describes its hardware, environment and utility, that the rewrite gives higher utility than continuing to search. Theorem 4.1 (global optimality) follows almost by construction and is relative to A and its consistency. Its practical limits are that useful target theorems may be unprovable or prohibitively expensive to find, and Schmidhuber states these limits himself.

### Cited Findings
- Paper: J. Schmidhuber, "Goedel Machines: Self-Referential Universal Problem Solvers Making Provably Optimal Self-Improvements", arXiv:cs/0309048, IDSIA-19-03; v1 25 Sep 2003, v5 17 Dec 2006. — [arXiv](https://arxiv.org/abs/cs/0309048)
- Definition: the initial algorithm "can completely rewrite itself, but only if a proof searcher embedded within the initial algorithm can first prove that the rewrite is useful, given a formalized utility function reflecting computation time and expected future success (e.g., rewards)." — [Schmidhuber v5 §1](https://arxiv.org/pdf/cs/0309048v5)
- Utility: a typical "value to go" utility u(s, Env): S × E → ℝ, i.e. expected future reward up to lifetime T, conditioned on the current state. — [§2](https://arxiv.org/pdf/cs/0309048v5)
- Target theorem: the proof searcher builds pairs (switchprog, proof) until it finds "a proof of a target theorem which essentially states: 'the immediate rewrite of p through current program switchprog on the given machine implies higher utility than leaving p as is'." — [§2.2](https://arxiv.org/pdf/cs/0309048v5)
- The axioms A include hardware axioms, reward axioms, environment axioms, uncertainty axioms, initial-state axioms and utility axioms. — [§3](https://arxiv.org/pdf/cs/0309048v5)
- **Theorem 4.1 (verbatim):** "Given any formalizable utility function u (Item 1f), and assuming consistency of the underlying formal system A, any self-change of p obtained through execution of some program switchprog identified through the proof of a target theorem (2) is globally optimal in the following sense: the utility of starting the execution of the present switchprog is higher than the utility of waiting for the proof searcher to produce an alternative switchprog later." — [§4.1](https://arxiv.org/pdf/cs/0309048v5)
  - Proof idea: "leaving p as is" includes all future switchprogs the searcher could find, so proving the current switch beats that alternative implicitly beats all of them. "Q.E.D." takes a few lines.
  - §4.2: a relaxed "≥" target theorem gives a weaker optimality ("at least as high").
  - §4.3: "all possible 'meta-levels' of the self-referential system are collapsed into one."
- Initial proof searcher: Bias-Optimal Proof Search (BIOPS), "O()-optimal" (Theorem 5.1), and it can use OOPS. — [§5](https://arxiv.org/pdf/cs/0309048v5)
- **Limitations, as Schmidhuber states them (§2.4):** "even a Gödel machine with unlimited computational resources must ignore those self-improvements whose effectiveness it cannot prove … one can construct pathological examples of environments and utility functions that make it impossible for the machine to ever prove a target theorem. Compare Blum's speed-up theorem … a realistic Gödel machine with limited resources cannot profit from self-improvements whose usefulness it cannot prove within its time and space constraints." — [§2.4](https://arxiv.org/pdf/cs/0309048v5)
- Rice's theorem, as Schmidhuber treats it (§4.4): "adopting the extreme notion of triviality embodied by Rice's theorem … only trivial improvements of a given strategy may be provably useful." He argues that Rice's infinite function classes are "irrelevant … for a typical Gödel machine dealing with a limited number of events." — [§4.4](https://arxiv.org/pdf/cs/0309048v5)
- Schmidhuber's reply to the Gödel limit: "These restrictions should not worry us; if there is no proof of some self-rewrite's utility, then humans cannot do much either." — [§1](https://arxiv.org/pdf/cs/0309048v5)
- Schmidhuber on hard theorem proving (FAQ 5): "some proofs are indeed hard to find, but here humans and Gödel machines face the same fundamental limitations." — [FAQ](https://arxiv.org/pdf/cs/0309048v5)
- Relation to AIXI: "Unlike hardwired systems such as Hutter's [16,17] and Levin's … [the Gödel machine can] rewrite any part of its software." AIXI(t,l) "needs a very time-consuming but constant set-up phase whose costs disappear in the O()-notation but not in a utility function." A Gödel machine initialized with AIXI(t,l) might prove that switching away from it is useful. — [§1, §4.4](https://arxiv.org/pdf/cs/0309048v5)
- OOPS: J. Schmidhuber, "Optimal Ordered Problem Solver", IDSIA-12-02, arXiv:cs/0207097 (v2 23 Dec 2002). It extends Levin's universal search, where phase i tests all programs p with runtime ≤ 2^i·P(p), to task sequences. It freezes the first found solution as non-writeable code that later programs may copy and edit, and it splits search time half-and-half between programs extending the most recent solution and fresh search. Abstract: "oops is the fastest general way of solving one task after another, always optimally exploiting solutions to earlier tasks when possible." — [arXiv:cs/0207097](https://arxiv.org/abs/cs/0207097)

### Inferences (red team)
- Global optimality is defined *relative to the agent's own axioms A and utility u* and holds only *given* a proof found. It guarantees nothing about whether a proof will ever be found or how long the search takes. The theorem is close to tautological: it holds by definition of the target theorem.
- Because a Gödel machine trusts its own proofs, a switchprog that rewrites the proof searcher itself also has to deal with self-trust. This is exactly what Yudkowsky and Herreshoff later formalize as the Löbian obstacle (see Q4). Schmidhuber's "assuming consistency of A" is where the obstacle hides.
- Impracticality: it needs a complete, correct axiomatization of hardware and environment, plus proof search over an astronomically large space. No nontrivial Gödel machine was implemented in the 2003–2006 papers. **[UNVERIFIED]** The 2025 "Darwin Gödel Machine" (Zhang, Clune et al., Sakana AI) explicitly replaces proofs with empirical benchmark validation, which concedes the impracticality of provable rewrites. I did not open this paper.

### Gaps
- Hutter's AIXI primary sources (Hutter 2000/2005) were not opened. The only verified AIXI facts are those quoted in Schmidhuber's paper.

---

## Q3. Yudkowsky (IEM 2013, LOGI), Bostrom 2014 (optimization power / recalcitrance), Hanson–Yudkowsky FOOM debate 2008

### Takeaway
Yudkowsky (2013) recasts Good's thesis as a question of **returns on cognitive reinvestment** and uses the analogy of a fission pile's multiplication factor k (k>1 is critical). Bostrom (2014) compresses takeoff kinetics into dI/dt = Optimization power / Recalcitrance. Critics such as Benthall (2017) note that this formula is qualitative and that recalcitrance rising with I yields linear rather than explosive growth. The 2008 FOOM debate set up the core disagreement between Hanson's view of slow, distributed, economy-wide growth and Yudkowsky's view of local, fast recursive takeoff.

### Cited Findings
- IEM: Yudkowsky, "Intelligence Explosion Microeconomics", MIRI Technical report 2013-1, last modified 13 Sep 2013. — [IEM](https://intelligence.org/files/IEM.pdf)
  - "I identify the key issue as returns on cognitive reinvestment—the ability to invest more computing power, faster computers, or improved cognitive algorithms to yield cognitive labor which produces larger brains, faster brains, or better mind designs." — [IEM abstract](https://intelligence.org/files/IEM.pdf)
  - Evidence the paper weighs: hominid evolution, Moore's Law and machine chess competence. Proposed next step: "formalize return on investment curves, so that each stance can formally state which possible microfoundations they hold to be falsified by historical observations." — [IEM abstract](https://intelligence.org/files/IEM.pdf)
  - Fission analogy: Fermi's pile had k = 1.0006, but k = 0.9946 counting only prompt neutrons, so it grew on a slow exponential because of delayed neutrons. "A pile with k = 1.0006 for prompt neutrons would have doubled in neutron intensity every tenth of a second." Footnote: "No argument by analogy is intended." — [IEM §1](https://intelligence.org/files/IEM.pdf)
  - Evidence noted as cutting both ways: "Investing exponentially more computing power into a constant chess-playing program produces linear increases in the depth of the chess-game tree." "Chess-playing algorithms have recently improved much faster than chess-playing hardware." Human/hominid evolution "does not seem to reveal exponentially greater amounts" of optimization needed per improvement. "We shouldn't expect some single grand law about whether you get superexponential, exponential, linear, logarithmic, or constant returns on cognitive investments." — [IEM §2–3](https://intelligence.org/files/IEM.pdf)
  - Hard takeoff scenario: once immediately accessible software improvements run out, the AI solves protein structure, orders DNA from peptide labs and builds molecular nanotech. "This rough sort of scenario is sometimes colloquially termed 'hard takeoff' or 'AI-go-FOOM.'" — [IEM](https://intelligence.org/files/IEM.pdf)
  - Logarithmic-returns case: Yampolskiy notes Yudkowsky also considers "only logarithmic returns on cognitive reinvestment: log(n) + log(log(n)) + … in each recursive cycle". — [Yampolskiy 2015](https://arxiv.org/abs/1502.06512)
- FOOM debate: "In late 2008, economist Robin Hanson and AI theorist Eliezer Yudkowsky conducted an online debate … about whether generally intelligent AIs will be able to improve their own capabilities very quickly (a.k.a. 'foom')." Guest posts came from James Miller and Carl Shulman. The book version, MIRI 2013 (ISBN-10 1939311039), adds the 2011 Jane Street in-person debate, a summary by Kaj Sotala and IEM. Posts are dated from 12 Nov 2008 onward on *Overcoming Bias*, and the book includes Yudkowsky chapters titled "Recursion, Magic" and "Engelbart: Insufficiently Recursive". — [The Hanson-Yudkowsky AI-Foom Debate (MIRI 2013)](https://intelligence.org/files/AIFoomDebate.pdf)
  - Hanson's prior model: "Economic Growth Given Machine Intelligence" (1998) models brain emulations entering the economy as skilled labor. Yudkowsky notes that the model "doesn't try to model an agent that" improves its own cognition. — [IEM §1](https://intelligence.org/files/IEM.pdf)
- Bostrom 2014 (via secondary sources; I did not open the book):
  - Model: "Rate of change in intelligence = Optimization power / Recalcitrance". Takeoff classes are slow (decades or centuries), moderate (months or years) and fast ("minutes to days"). "Crossover" is "a point at which the inputs to a project are mostly its own outputs." Recalcitrance examples: hardware is "potentially low", AI content "might be very low", and algorithms are uncertain and could drop with a key insight. — [LessWrong reading group, "Superintelligence 6: Intelligence explosion kinetics"](https://www.lesswrong.com/posts/GT8uvxBjidrmM3MCv/superintelligence-6-intelligence-explosion-kinetics) (secondary summary)
  - Benthall's critique: he writes the model as dI/dt = O/R and takes O(I) = αI + β. With constant R = k, I grows exponentially, "the 'intelligence explosion' that gives Bostrom's argument so much momentum." But "Bostrom does not mention the possibility of recalcitrance increasing in intelligence". With R linear in I, the growth rate tends to α_o/α_r: "This is linear, not exponential, growth." The motivation is low-hanging fruit followed by harder search. — [Benthall 2017, arXiv:1702.08495](https://arxiv.org/abs/1702.08495)
- **[UNVERIFIED]** LOGI: Yudkowsky's "Levels of Organization in General Intelligence" (in Goertzel & Pennachin eds., *Artificial General Intelligence*, Springer 2007; written c. 2002) introduces "seed AI" and the idea that recursive self-improvement differs from ordinary feedback because the optimizer improves the optimizer. I did not open it.

### Inferences
- In IEM, Yudkowsky concedes that the question is empirical (the shape of the return curves) and cannot be settled a priori. That is a significant retreat from Good's "unquestionably".
- Bostrom's O/R formula is a definitional identity until O(I) and R(I) are specified. All the content lies in the assumption that R stays flat or falls while O ∝ I.

### Gaps
- I could not open Bostrom's book text. Precise page numbers and any worked numerical example (for instance a hyperbolic case) are unverified.
- LOGI was not opened.

---

## Q4. The Löbian obstacle (Yudkowsky & Herreshoff 2013) and later MIRI work

### Takeaway
An agent that acts only on proven theorems, and that trusts a successor because the successor also acts only on theorems proven in the same theory T, needs the soundness schema □_T⌜φ⌝ → φ to be provable in T. By Löb's theorem this is impossible for consistent T, so a naive design can only build successors with strictly weaker math, a finite chain of trust. The paper gives technical workarounds: infinitely descending soundness schemas, Fallenstein's parametric polymorphism T_κ, and probabilistic reflection. The authors call these partial solutions that are "not … realistic", and later logical induction (2016) achieves a limited, probabilistic self-trust without resolving tiling.

### Cited Findings
- Paper: Yudkowsky & Herreshoff, "Tiling Agents for Self-Modifying AI, and the Löbian Obstacle", Early Draft, **October 7, 2013**, MIRI. Research was refined at the Nov 2012 and Apr 2013 MIRI workshops, with Christiano, Fallenstein, Barasz, LaVictoire, Dewey, Yuan, Armstrong, Steinhardt, Taylor and Critch. — [MIRI PDF](https://intelligence.org/files/TilingAgentsDraft.pdf)
- Löb's theorem as stated: "A consistent mathematical theory T cannot trust itself in the sense of verifying that a proof in T of any formula φ implies φ's truth—we cannot have the self-verifying scheme (over all formulas φ) of ∀φ : T ⊢ T⌜φ⌝ → φ (Löb 1955)." — [§1](https://intelligence.org/files/TilingAgentsDraft.pdf)
- Link to Gödel II (fn 9): "Suppose that T proves its own soundness schema … If φ = ⊥ then T ⊢ T⌜⊥⌝ → ⊥ and T is inconsistent by Gödel's Second Incompleteness Theorem." — [fn 9](https://intelligence.org/files/TilingAgentsDraft.pdf)
- The obstacle itself: "For A1 to trust A0, the system Axm1 must be able to prove that whenever a proof exists in Axm0 of ⌜φ(x)⌝, then φ(x) must be true. Löb's Theorem normally implies that no system can prove its own soundness schema—only strictly more powerful systems can prove a soundness schema over weaker systems. This seemingly implies that Axm1 ≠ Axm0 and that the offspring A0 must possess strictly weaker mathematical power than its parent A1, which is the Löbian obstacle." — [§2](https://intelligence.org/files/TilingAgentsDraft.pdf)
  - Consequence: "an agent architecture can only tile a finite chain of successors (or make a finite number of self-modifications) before running out of 'trust.'" (§1). Example: a ZF parent can trust a PA child (fn 10).
- Failed attempts (§3): a diagonal fixed point ψ ↔ φ(x) ∨ T⌜ψ(x)⌝ collapses because "T⌜ψ(x)⌝ → ψ(x) so by Löb's Theorem ∀x : T ⊢ ψ(x)". A naive descending sequence T̃–n fails because T̃–0 ⊢ T̃–0⌜⊥⌝ → T̃–1⌜⊥⌝.
- Desiderata (§3): "Indefinitely tiling trust", "Reflectively coherent quantified belief", "Reflective trust" and "Naturalistic trust". The authors' status assessment: "At present we can partially resolve the Löbian obstacle by technical means to the extent of obtaining the first and second desiderata, but not yet the third and fourth desiderata, nor yet by fundamental rather than technical means." — [§3](https://intelligence.org/files/TilingAgentsDraft.pdf)
- Workaround 1, infinitely descending soundness schemas (§4.1): T–n ≜ T ∪ {∀φ: ψ(n) → (∀x: T–(n+1)⌜φ(x)⌝ → φ(x))} with ψ(n) ≡ ¬Bew_ZF(n, ⌜⊥⌝). T proves each ψ(n) but not ∀n ψ(n), which would be Con(ZF), and this blocks the collapse. — [§4.1](https://intelligence.org/files/TilingAgentsDraft.pdf)
- Workaround 2, parametric polymorphism (Benja Fallenstein, §4.2): add a constant κ, intended to be any natural number, with T_κ ≜ T ∪ {∀φ: (κ>0) → ∀x: T_κ⌜φ(x)⌝ → φ(x)[κ\κ−1]}. The paper proves soundness by induction on the models {ℕ, κ=n}. Agents act only if an action is "safe for κ steps".
  - Limits, verbatim: Fallenstein's T_κ "demonstrates indefinite tiling without loss of mathematical strength using a series of agents employing syntactically identical theories … It does not address reflectively coherent quantified belief." "It is difficult to see what 'believing in' Tκ could correspond to in terms of the epistemic state of a rational agent." "We would again not offer Tκ as a realistic candidate for the mental state of a coherent self-modifying agent; rather Tκ is being exhibited as a technical possibility proof." Workshop nickname: κ was "the number of ineffable mystery" (fn 28). — [§4.2](https://intelligence.org/files/TilingAgentsDraft.pdf)
  - The paper also discusses Willard's (2001) self-verifying systems, in which addition and multiplication are not provably total, so the exact Löb formula never materializes. The authors "cannot yet see how to adopt" them because of a shortening "telomere".
- Workaround 3, probabilistic reflection (Christiano et al. 2013, §4.3): a system can represent its own probability predicate to within ε: a < P(φ) < b ⇒ P(a < p⌜φ⌝ < b) = 1. This sidesteps Tarski's undefinability via open intervals, and existence is shown via the Kakutani fixed-point theorem. Status: "We do not yet have any version of the Aα formalism which goes through for a probabilistic reflection principle." — [§4.3](https://intelligence.org/files/TilingAgentsDraft.pdf)
- "Model polymorphism": the term does not appear in the draft I read, where a text search for "model polymorph" found nothing. The paper's techniques are named as above. **The task brief's "model polymorphism" may conflate this with another source. [UNVERIFIED]**
- Rice's theorem in the tiling paper (fn 6): "By Rice's Theorem no nontrivial property of output can be determined over arbitrary programs, but of course an AI, like a human engineer, may choose to work within a more restrictive space of programs which it can understand." — [fn 6](https://intelligence.org/files/TilingAgentsDraft.pdf)
- Authors' disclaimer: Gödelian difficulties apply equally to humans, since "any human way of bypassing the Gödelian difficulty" should be available to AI (fn 3). — [fn 3](https://intelligence.org/files/TilingAgentsDraft.pdf)
- The procrastination paradox (as described by Yampolskiy): "the system will find itself in a state in which a change made immediately is as desirable and likely as the same change made later … this may result in an infinite delay." He cites refs [83, 84]. — [Yampolskiy 2015](https://arxiv.org/abs/1502.06512). **[UNVERIFIED]** The primary source is Fallenstein & Soares, "Problems of self-reference in self-improving space-time embedded intelligence" (AGI 2014). I did not open it.
- Logical induction: Garrabrant, Benson-Tilsen, Critch, Soares & Taylor, "Logical Induction", arXiv:1609.03543 (v5 7 Dec 2020). It is "a computable algorithm that assigns probabilities to every logical statement in a given formal language, and refines those probabilities over time", and "learns to have accurate beliefs about its own current beliefs, in a manner that avoids the standard paradoxes of self-reference". "Logical inductors also learn to trust their future beliefs more than their current beliefs." — [arXiv:1609.03543](https://arxiv.org/abs/1609.03543)
  - Self-trust result: Theorem 4.12.4 (Self-Trust) and Theorem 4.12.1 (Expected Future Expectations), E_n(X_n) ≂_n E_n("E_f(n)(X_n)"). The authors state the scope themselves: "The specific type of self-trust that logical inductors achieve … is a subtle subject, and worthy of a full paper in its own right." They call logical induction "a first step towards models of rational behavior that work in settings where agents must reason about themselves". — [§4.12, §7](https://arxiv.org/pdf/1609.03543)

### Inferences
- **Status.** The Löbian obstacle is a theorem about one specific *architecture*: agents that act only on proofs and trust successors through a soundness schema. It is not a theorem that RSI is impossible. The authors stress it is "a crisp difficulty", not a claim that it will block AI (fn 5 context). Workarounds exist but are technically odd (T_κ) or incomplete (probabilistic reflection). Logical induction gives asymptotic, probabilistic self-trust but provides no tiling agent formalism.
- Red team: modern ML systems do not act on proofs at all, so the obstacle bears on them only if one demands *provable* goal preservation across self-modification. It is an obstacle to verified safe RSI more than to RSI as such.
- **[UNVERIFIED]** MIRI's later "Embedded Agency" (Demski & Garrabrant 2018) lists robust delegation and Vingean reflection as still open. MIRI announced in 2020–2024 that it was deprioritizing this agent-foundations line. I did not open these sources.

### Gaps
- I did not open Fallenstein & Soares 2014/2015 (Vingean reflection, procrastination paradox) or Christiano et al. 2013 directly.

---

## Q5. Other limits: Rice, No Free Lunch, diminishing returns (Chollet), complexity, Yampolskiy, formal growth models

### Takeaway
None of these yields an impossibility theorem for practical RSI. Rice's theorem rules out deciding properties of *arbitrary* programs but not restricted, designed spaces, which both Schmidhuber and Yudkowsky concede. No Free Lunch is widely judged irrelevant because real environments are structured. The diminishing-returns arguments of Chollet and Benthall are empirical claims about the shape of R(I). Yampolskiy's catalog mixes real constraints (physics, complexity classes, verification difficulty) with informal arguments, some of them weak, such as his "proof by contradiction".

### Cited Findings
- Rice's theorem:
  - Yampolskiy: "Levin type search through the program space will face problems related to Rice's theorem [78] which states that for any arbitrarily chosen program it is impossible to test if it has any non-trivial property such as being very intelligent. This testing is of course necessary to evaluate redesigned code." — [Yampolskiy 2015](https://arxiv.org/abs/1502.06512)
  - Counterpoint 1: Schmidhuber says Rice's infinite domains are "irrelevant … for a typical Gödel machine dealing with a limited number of events." — [Gödel machine §4.4](https://arxiv.org/pdf/cs/0309048v5)
  - Counterpoint 2: Yudkowsky & Herreshoff say an AI "may choose to work within a more restrictive space of programs which it can understand." — [Tiling fn 6](https://intelligence.org/files/TilingAgentsDraft.pdf)
- No Free Lunch (Wolpert & Macready, "No free lunch theorems for optimization", IEEE Trans. Evol. Comp., cited as Yampolskiy ref 79; **[UNVERIFIED]** 1997, vol. 1(1):67–82):
  - Yampolskiy: "universal search over the space of mind designs which will not be computationally possible due to the No Free Lunch theorems as we have no information to reduce the size of the search space." — [Yampolskiy 2015](https://arxiv.org/abs/1502.06512)
  - Chollet, quoted in MIRI's reply: "no problem-solving algorithm can outperform random chance across all possible problems." — [Yudkowsky, "A reply to Francois Chollet", 6 Dec 2017](https://intelligence.org/2017/12/06/chollet/)
  - Rebuttal: real environments are low-entropy, and general learners such as Laplace's rule, Solomonoff induction and humans do well in them. Scott Aaronson is quoted as calling NFL-based AI-limit arguments "not a promising sign". — [MIRI reply](https://intelligence.org/2017/12/06/chollet/). Schmidhuber's FAQ 6 also addresses NFL. — [Gödel machine FAQ](https://arxiv.org/pdf/cs/0309048v5)
- Chollet 2017, "The impossibility of intelligence explosion" (Medium; later retitled "The implausibility of intelligence explosion" per the [search listing](https://medium.com/@francois.chollet/the-impossibility-of-intelligenceexplosion-5be4a9eda6ec)). Medium returned 403, so the quotations below come via MIRI's reply:
  - "Intelligence is situational — there is no such thing as general intelligence."
  - Science is "possibly the closest system to a recursively self-improving AI that we can observe"
  - "Crucially, the civilization-level intelligence-improving loop has only resulted in measurably linear progress"
  - "other parts of the system will inevitably start acting as bottlenecks" — [MIRI reply](https://intelligence.org/2017/12/06/chollet/)
  - Yudkowsky's counterarguments: AlphaGo Zero surpassed human Go knowledge in 3 days; world GDP grows exponentially; slow science is a bureaucratic artifact; Kasparov beat a collective of thousands of players; and "bounded, therefore harmless" is a fallacy (a supernova is not infinitely hot). — [MIRI reply](https://intelligence.org/2017/12/06/chollet/)
  - Boaz Barak (9 Dec 2017) agrees partly but disputes the title: "scientific progress has been accelerating, precisely because we use scientific progress to make more progress." — [Windows on Theory](https://windowsontheory.org/2017/12/09/on-the-impossiblity-of-intelligence-explosion/)
- Yampolskiy, "From Seed AI to Technological Singularity via Recursively Self-Improving Software" (arXiv:1502.06512, 2015). It surveys types of self-improvement, analyzes "limits on computation restricting recursive self-improvement" and introduces "RSI Convergence Theory". Specific claims, verbatim or near-verbatim:
  - Diminishing returns: "the law of diminishing returns quickly sets in and after an initial significant improvement phase, characterized by discovery of 'low-hanging fruit', future improvements are likely to be less frequent and less significant."
  - Complexity: "Assuming separation of complexity classes (such as P vs NP) holds, it becomes obvious that certain classes of problems will always remain only approximately solvable and any improvements in solutions will come from additional hardware resources not higher intelligence." Some problems, such as checkers, can be solved completely, after which no further improvement is possible.
  - Wiedermann: human-level intelligence is "upper-bounded by the Σ2 class of the Arithmetic Hierarchy."
  - Mahoney's formalization: P has goal G iff G(P(t)) eventually increases monotonically. P1 is RSI w.r.t. G iff P_i(−1) = P_{i+1} and the sequence is improving. Result: the "algorithmic complexity of Pn (the nth iteration of an RSI program) is not greater than O(log n)", i.e. limited knowledge gain.
  - Other obstacles he lists: the "multidimensionality of optimization" (no change is strictly an improvement); testing intelligence above one's own level; error accumulation over generations; the "Munchausen obstacle" (a system may lose the ability to understand itself as it grows); computational irreducibility of self-simulation; and the claim that "a Turing Machine cannot output a machine of greater algorithmic complexity" [ref 90].
  - "Proof by contradiction" of the impossibility of intentional RSI: "if an agent can produce a more intelligent agent it would already be as capable as that new agent."
  - Re-optimization: "re-optimization problem is proven to be as difficult as optimization itself" (refs 92–95).
  - He also notes that a "truly RSI system is theorized not to be subject to diminishing returns." — [Yampolskiy 2015](https://arxiv.org/abs/1502.06512)
- Red team on Yampolskiy:
  - The "proof by contradiction" equivocates between *capability in principle* (with unbounded time) and *capability at given resources*. A program that can eventually produce a faster solver was "capable" only in the trivial sense.
  - The Kolmogorov-complexity bound (K(P_n) ≤ K(P_1) + O(log n)) limits *description length*, not runtime performance. A low-K program can be extremely capable given compute: AIXI-like or search programs are short. (My inference.)
  - The physics limits (Bekenstein-type bounds) sit astronomically far above current systems, a point Yampolskiy concedes: "we are currently probably very far from reaching them."

### Formal growth models: dI/dt = f(I)
The following is standard ODE mathematics, derived by me. It is not a cited claim, but it is checkable by elementary integration.
- Separating variables gives t(I) = ∫_{I₀}^{I} dJ/f(J). **Finite-time blow-up** (a true "singularity") occurs iff ∫_{I₀}^{∞} dJ/f(J) < ∞ (Osgood-type criterion), and the blow-up time is T* = ∫_{I₀}^{∞} dJ/f(J).
  - f(I) = c·I^p: if p > 1, then T* = I₀^{1−p}/(c(p−1)) < ∞, giving a hyperbolic singularity: I(t) = [I₀^{1−p} − c(p−1)t]^{−1/(p−1)}.
  - p = 1 gives exponential growth with no finite-time blow-up.
  - 0 < p < 1 gives polynomial growth, I ~ t^{1/(1−p)}.
  - p = 0 gives linear growth.
  - f(I) = c·I·log I diverges logarithmically in the integral, so there is no blow-up (double-exponential growth), even though f is superlinear. This shows that "superlinear returns" is not sufficient for a singularity. Only ∫ dI/f < ∞ is.
- Mapping to Bostrom: dI/dt = O(I)/R(I). With O = αI + β:
  - R constant gives exponential growth (as Benthall shows).
  - R ∝ I gives growth that is asymptotically linear (Benthall).
  - R ∝ 1/I gives f ~ I², and so finite-time blow-up (my derivation).
  - In general, a singularity requires R(I) to fall fast enough that ∫ R(I)/O(I) dI < ∞. — The constant and linear cases are verified in [Benthall 2017](https://arxiv.org/abs/1702.08495). The other cases are my derivation.
- Yudkowsky's logarithmic-returns case, log(n) + log log(n) + …, in this framing corresponds to f growing sublinearly, i.e. no explosion. — [Yampolskiy 2015 citing Yudkowsky](https://arxiv.org/abs/1502.06512)
- **[UNVERIFIED]** Hyperbolic growth models of world population and GDP (von Foerster et al. 1960, "Doomsday: Friday, 13 November, A.D. 2026"; Kremer 1993) are the empirical-macro precedent for p>1 models. I did not open these sources.

### Mathematical motifs (fixed points, diagonalization, self-reference)
- Diagonal and fixed-point constructions are central to both directions:
  - Löb's theorem is proved by diagonalization, constructing a Löb sentence (tiling paper §3: "similar diagonalization over provability, Löb's Theorem constructs a Löb sentence").
  - The Kakutani fixed-point theorem gives probabilistic reflection (§4.3).
  - The Gödel machine is self-referential by design: its axioms describe its own code (Schmidhuber §1–3), and Schmidhuber notes that limits of self-observability are "reminiscent of Heisenberg's" principle. — [Tiling paper](https://intelligence.org/files/TilingAgentsDraft.pdf); [Gödel machine](https://arxiv.org/pdf/cs/0309048v5)
- Tarski's undefinability of truth is the reason for the open-interval formulation of probabilistic reflection. — [Tiling §4.3](https://intelligence.org/files/TilingAgentsDraft.pdf)

### Inferences
- Classical theorems such as Rice, Gödel/Löb and NFL limit *worst-case*, *arbitrary-program* or *proof-based* self-improvement. None of them bounds the speed of improvement on structured real-world tasks. The live question remains the empirical shape of R(I), i.e. the returns curve, as both Yudkowsky (IEM) and Benthall agree.
- Both sides have a symmetric weakness. Explosion arguments assume R does not rise; impossibility arguments (Chollet, Yampolskiy) assume it does, or misapply NFL and Rice.

### Gaps
- Chollet's original essay and Wolpert–Macready 1997 were not opened directly; Medium blocked fetching.
- I found no primary source giving a published, peer-reviewed formal RSI model with a proven blow-up condition beyond Benthall and Mahoney (the latter via Yampolskiy). The ODE analysis above is my own.
- Chalmers 2010 ("The Singularity: A Philosophical Analysis") is cited by Yampolskiy for the "correlation obstacle" but was not opened.
