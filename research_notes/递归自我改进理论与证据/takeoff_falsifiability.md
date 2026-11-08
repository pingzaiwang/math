# Takeoff models under automated AI research: parameters, evidence, and falsifiable signatures of recursive acceleration

Research date: 2026-11-08. Sources were opened with WebFetch unless marked **[snippet only]** (seen only in a search result summary) or **[UNVERIFIED, from background knowledge]** (not opened in this session).

## Q1. Quantitative takeoff models and their key parameters

### Takeaway
Every major model reduces "is takeoff recursive?" to one returns parameter: Forethought's r (doublings of software per doubling of cumulative research input), equivalent to λ+φ>1 in growth-theory terms, plus one substitution parameter: σ, the elasticity of substitution between compute and labor.
- r > 1 and σ not near 0 gives a software intelligence explosion (SIE).
- r < 1, or compute–labor complementarity, gives a fast but non-explosive "fizzle".
- Published central estimates of r straddle 1, at roughly 0.5–2 with hardware held fixed.

### Cited Findings
**Forethought SIE model (Eth & Davidson, 26 Mar 2025)**
- r is defined as "the number of times AI software capacity doubles for each doubling of cumulative software R&D work."
  - r = 1: sustained exponential growth.
  - r < 1: fizzle.
  - r > 1: SIE.
  - r = 1 is a knife-edge. — [Forethought](https://www.forethought.org/research/will-ai-r-and-d-automation-cause-a-software-intelligence-explosion)
- Empirical r estimates cited there:
  - Image recognition (Epoch): median 1.4, 5–95% range 0.8–2.4.
  - Computer chess: 0.8.
  - RL sample efficiency: 1.6.
  - SAT solvers: 3.5.
  - Linear programming: 1.1.
  - "Algorithms in general": about 4, on rough assumptions.
  - Hardware: about 7 historically; GPUs 2006–2022 about 5 (authors flag these as possible overestimates).
  - Best guess for frontier AI software: about 1–4. Adjusted for holding hardware constant: **about 0.5–2**. — [Forethought](https://www.forethought.org/research/will-ai-r-and-d-automation-cause-a-software-intelligence-explosion)
- Assumptions and worked examples:
  - Current AI software efficiency doubles about every 6 months.
  - The first doubling after ASARA (AI systems for AI R&D automation) is assumed to take about 1 month.
  - With r = 0.7, each doubling takes 35% longer: 41, 55, 74, 100 days.
  - With r = 3, each doubling takes 63% as long: 19, 12, 7.6, 4.8 days.
  - In the toy model, an SIE asymptotes about 8 months after full automation.
  - No numeric probability is given; an SIE is "at least decently likely" with hardware held constant. — [Forethought](https://www.forethought.org/research/will-ai-r-and-d-automation-cause-a-software-intelligence-explosion)
- Compute and training-time arguments:
  - Inference compute could run hundreds of thousands of researcher-equivalent copies now, and millions within a few years.
  - Multi-month training runs delay an SIE but do not prevent it.
  - Early ASARA may need much more thinking time per task, which cuts effective parallelism. — [Forethought](https://www.forethought.org/research/will-ai-r-and-d-automation-cause-a-software-intelligence-explosion)
- A companion Forethought piece concludes there is "a good chance that compute bottlenecks don't slow down a software intelligence explosion until its late stages." **[snippet only]** — [Forethought compute bottlenecks](https://www.forethought.org/research/will-compute-bottlenecks-prevent-a-software-intelligence-explosion)

**Davidson compute-centric takeoff model (Open Philanthropy, June 2023)**
- The model has a median of about 3 years from 20% to 100% automation of cognitive tasks.
  - The "effective FLOP gap" is about 3.5 OOM, crossed at about 1.3 OOM/yr.
  - There is about a 10% chance takeoff takes under 10 months and about 10% it takes over 12 years.
  - AGI training requirements are about 1e36 FLOP with 2020 algorithms (another summary says 2022 algorithms, a discrepancy).
  - Davidson also gives about 40% to takeoff lasting more than 5 years. **[snippet only; primary page returned HTTP 403 and now redirects to coefficientgiving.org]** — [AF post](https://alignmentforum.org/posts/Gc9FGtdXhK9sCSEYu/what-a-compute-centric-framework-says-about-ai-takeoff); [LessWrong summary](https://www.lesswrong.com/posts/ykJ8Ku7tKeSCe9fFo/when-will-ai-automate-all-mental-work-and-how-fast)

**Epoch GATE (Mar 2025, arXiv 2503.04941)**
- GATE is an integrated assessment model that combines compute-based AI development, task automation, and growth with endogenous investment.
  - It projects growth 2–20× the historical ~3%/yr during automation.
  - Growth above 30%/yr requires about 50–70% of tasks automated.
  - Default parameters immediately put about 20% of world output (about $20T/yr) into AI, and give "optimal" 2025 AI investment of $25T.
  - Epoch says outputs "are not meant to represent Epoch AI's forecasts." **[snippet only]** — [Epoch GATE](https://epoch.ai/gate/); [arXiv](https://arxiv.org/html/2503.04941v2); [Epoch "explosive growth redux"](https://epoch.ai/gradient-updates/ai-and-explosive-growth-redux)
- Note: GATE is compute-centric. Explosive growth there comes from broad automation plus reinvestment in compute, not from a software-only feedback loop. This is the Epoch/Erdil–Besiroglu framing.

**Erdil / Besiroglu (Epoch, later Mechanize)**
- Their stated position: 2045+ timelines, they "don't think an intelligence explosion is plausible," but they expect explosive economic growth. Besiroglu likens "intelligence explosion" to calling the Industrial Revolution a "horsepower explosion." **[snippet only]** — [Dwarkesh podcast](https://www.dwarkesh.com/i/161532341/intelligence-explosion)
- Epoch calls the compute-bottleneck argument "suggestive but the empirical evidence is shaky." Scale-dependent innovations create a compute bottleneck that makes an explosion less likely. **[snippet only]** — [Epoch, "The least understood driver of AI progress"](https://epoch.ai/gradient-updates/the-least-understood-driver-of-ai-progress)

**AI 2027 / AI Futures Project and the titotal critique**
- titotal's critique targets AI 2027's ~40% weight on a "superexponential" time-horizon curve that "shoots to infinity in a few years, regardless of your starting point." It also flags places where the code does not match the written methodology. **[snippet only]**
  - The authors called the specific superexponential functional form arbitrary but defended the forecast as state of the art.
  - Kokotajlo moved his median from 2027 to 2028.
  - Zvi called the critique "high quality" but disputed its framing. — [Zvi analysis](https://thezvi.substack.com/p/analyzing-a-critique-of-the-ai-2027); [response](https://www.lesswrong.com/posts/gdv93PboLFGHy8vPR/the-practical-value-of-flawed-models-a-response-to-titotal-s)
- AI Futures Q1 2026 update:
  - Automated Coder medians moved about 1.5 years earlier: Daniel from late 2029 to mid 2028; Eli from early 2032 to mid 2030.
  - Medians for the current METR doubling time moved from 5.5 months to 4 months (Daniel) and 4.5 months (Eli).
  - Daniel's AC 80%-horizon requirement fell from 3 years to 1 year.
  - "If real-world events progress at ~65% of the pace in AI 2027, AC is achieved in 2028." — [AI Futures blog](https://blog.aifutures.org/p/q1-2026-timelines-update)
  - Comparison: the original AI 2027 scenario narrative put a superhuman coder around early 2027 **[UNVERIFIED, from background knowledge; ai-2027.com not opened]**.

**Aschenbrenner, "Situational Awareness" (June 2024)** **[UNVERIFIED, from background knowledge; not opened]**
- Physical compute is extrapolated at about 0.5 OOM/yr and algorithmic efficiency at about 0.5 OOM/yr, plus "unhobbling."
- He argues hundreds of millions of automated AI researchers could compress about a decade of algorithmic progress (≥5 OOM) into ≤1 year.
- The writer should verify these numbers at situational-awareness.ai before citing them.

### Inferences
- The disagreement between "hard" (Forethought, AI 2027, Aschenbrenner) and "slow/broad" (Epoch, Erdil–Besiroglu) camps is mostly about two numbers:
  - r with hardware fixed. Central estimates span 0.5–2 and straddle the threshold of 1.
  - σ, the compute–labor elasticity (see Q2).
- Model outputs are knife-edge sensitive. Forethought's own worked examples show r = 0.7 giving about 30× in about a year, versus r = 3 giving near-asymptotic growth within weeks. Point forecasts should therefore be presented as conditional on r.

### Gaps
- Could not open Davidson's primary report (HTTP 403 after the Open Philanthropy → Coefficient Giving redirect). Its numbers come from secondary summaries.
- Did not open ai-2027.com's takeoff supplement, Aschenbrenner, or the Aghion–Jones–Jones paper (NBER w23928, "Artificial Intelligence and Economic Growth", **[UNVERIFIED]**).
- Did not verify any post-2025 update to the Forethought r estimates.

## Q2. Empirical evidence on key parameters (algorithmic progress, compute, bottlenecks)

### Takeaway
- Algorithmic progress in pretraining halves required compute about every 8 months (95% CI 5–14 months).
- Forethought assumes about 6 months for overall software, including post-training.
- The only econometric estimate of compute–labor substitution in frontier labs (Whitfill & Wu 2025) gives opposite answers depending on specification:
  - σ ≈ 2.6 (substitutes; explosion possible).
  - σ ≈ 0 (complements; compute-bottlenecked).
  - It rests on only 27 firm-year observations.
- The bottleneck question is therefore empirically unresolved.

### Cited Findings
- **Ho et al. 2024 (Epoch), pretraining algorithmic progress:**
  - Compute needed for a fixed performance level "halved roughly every 8 months," 95% CI 5–14 months.
  - Shapley attribution: 60–95% of gains come from compute and data scaling, 5–40% from algorithms.
  - The transformer is worth almost 2 years of progress; Chinchilla is worth 8–16 months.
  - Pretraining only; results are highly model-dependent. — [Epoch](https://epoch.ai/blog/algorithmic-progress-in-language-models)
- **Whitfill & Wu, "Will Compute Bottlenecks Prevent an Intelligence Explosion?" (arXiv 2507.23181, v2 Aug 2025)**
  - Data: 27 firm-year observations (OpenAI 2016–24, Anthropic 2022–24, DeepMind 2014–24, DeepSeek 2023–24).
  - Labor is total PitchBook headcount, not research-only.
  - Research compute is *assumed* to be one third of training compute.
  - Estimates of σ:

    | Specification | σ | Clustered SE | Monte Carlo SE | R² |
    |---|---|---|---|---|
    | Baseline CES | 2.583 | 0.341 | 0.657 | 0.857 |
    | "Frontier experiments" | −0.103 | 0.176 | 0.419 | 0.982 |

  - The frontier-experiments σ is indistinguishable from 0 (near-perfect complements).
  - The authors say feasibility of an explosion is "highly sensitive to how AI research production is structured." — [arXiv](https://arxiv.org/html/2507.23181v2)
  - Commentary notes that elasticity may not be constant over time. **[snippet only]** — [LessWrong](https://www.lesswrong.com/posts/9Dn5wFGhwN3taHiTM/modeling-a-constant-compute-automated-ai-r-and-d-process)
- **Compute scaling:** Davidson's model crosses the FLOP gap at about 1.3 OOM/yr of effective compute. **[snippet only]** — [slides](https://docs.google.com/presentation/d/1MKHOkSyC5stPzLP_RUGRSCccQUXgeBoblSGBfGghEwI/htmlpresent)
  - Commonly cited Epoch figures are about 4–5×/yr growth in frontier training compute. **[UNVERIFIED, not opened this session]**
- **Semiconductor and energy constraints:** not researched in depth this session (see Gaps).

### Inferences
- Ho et al.'s 60–95% compute attribution means that, historically, most "effective compute" gains came from hardware and spending, not ideas. A software-only loop must therefore raise the algorithmic share sharply to dominate.
- If σ ≈ 0 holds at the frontier-experiment margin, the relevant r for an SIE is the hardware-constant one, which is the lower 0.5–2 range. Abundant AI labor would then mostly be wasted waiting for experiments, and takeoff speed would be set by compute growth: the Davidson/GATE world.

### Gaps
- No independent replication of Whitfill & Wu found.
- Did not open Epoch's training-compute trend page, energy/chip supply analyses (e.g., "Can AI scaling continue through 2030?"), or the Forethought compute-bottleneck paper in full.
- No 2026 update of algorithmic-progress halving times was located. Post-training, RL and inference-time gains are not covered by Ho et al.

## Q3. Growth-theory analogs and the blow-up condition

### Takeaway
In the idea production function dA/dt = δ R^λ A^φ, setting R ∝ A (AI researchers scale with software level, compute fixed) gives dA/dt = δ A^{λ+φ}.
- λ+φ > 1: finite-time blow-up.
- λ+φ = 1: exponential growth.
- λ+φ < 1: decelerating polynomial growth.
- This is algebraically the same as Forethought's r > 1, with r = λ/(1−φ).
- Human-economy evidence (Bloom et al.) shows strongly diminishing returns (φ well below 1), which is why the empirical fight is about whether AI R&D has larger λ/(1−φ) than the general economy.

### Cited Findings
- **Bloom, Jones, Van Reenen & Webb ("Are Ideas Getting Harder to Find?", NBER w23782, AER 2020):**
  - Researchers needed to sustain Moore's-law doubling are over 18× the early-1970s level.
  - Semiconductor research productivity falls about 6.8%/yr (an earlier draft said about 10%).
  - US aggregate research productivity has fallen 41× since the 1930s, more than 5%/yr.
  - Steady growth persists only because research effort keeps rising. — [NBER](https://www.nber.org/papers/w23782.pdf) (exact rates differ across drafts; check the AER version)
- **Jones (1995) semi-endogenous growth:** with φ < 1 and researchers growing at rate n, steady-state growth is g_A = λn/(1−φ). Growth is bounded by researcher-population growth unless researchers are made from output (AI). **[UNVERIFIED citation details: Jones, C. "R&D-Based Models of Economic Growth," JPE 1995; formula is standard]**
- **Aghion, Jones & Jones (2017/2019), "Artificial Intelligence and Economic Growth":** shows singularities can arise if automation of idea production is complete, and that Baumol-style bottlenecks (essential non-automated tasks) can prevent explosion even with high automation. **[UNVERIFIED, not opened]**

### Derivation (math, no source needed)
- With s = λ+φ > 1 and A(0) = A₀:
  - A(t) = [A₀^{1−s} − (s−1)δt]^{−1/(s−1)}.
  - Blow-up time: T* = A₀^{1−s}/((s−1)δ).
- Successive doubling-time ratio (in Forethought's cumulative-input form): Δt_{k+1}/Δt_k = 2^{1/r − 1}.
  - Check: r = 3 gives 0.63; r = 0.7 gives 1.35. Both match Forethought's examples.
- Mapping to r: d ln A = (λ/(1−φ)) d ln(cumulative R). So r = λ/(1−φ), and with R ∝ A, r > 1 ⇔ λ+φ > 1.
- A **one-time level jump**, meaning a multiplicative boost M to research input (e.g., AI makes each researcher M× productive once), raises growth once by a factor M^λ. If λ+φ < 1, doubling times then lengthen again. Recursion requires the boost itself to grow with A.

### Inferences
- If λ ≈ 0.5–1 and φ is as low as the Bloom et al. aggregate data imply, then λ+φ < 1 for human R&D. The SIE case requires AI-specific software R&D to have much higher returns (r > 1), which the image-recognition (1.4) and SAT (3.5) estimates suggest but do not establish for frontier LLMs.
- Baumol and Amdahl effects (Aghion–Jones–Jones; compute complementarity) mean the effective λ for "AI labor" can fall toward 0 as the non-automated share binds.

### Gaps
- No direct published estimate of φ and λ specifically for frontier LLM software R&D was found beyond Forethought's r compilation.

## Q4. Falsifiability: observables distinguishing recursive acceleration from a one-time level jump, and what 2024–2026 data show

### Takeaway
The cleanest discriminator is the **trend in successive doubling times** of a capability or efficiency metric.
- Under recursion (r > 1) each doubling is a constant fraction shorter than the last, so the growth rate itself rises and the log-curve is convex.
- A level jump gives one shortened doubling time that then stays flat or re-lengthens.

Current data are ambiguous. METR's doubling time has shortened across windows (196 → 131 → 89 days), and lab-internal code share is reported above 80%. But the shortening coincides with a plausible one-off regime change (RL reasoning models, 2024), task-suite artifacts, and saturation. Measured human-productivity uplift in RCTs went from −19% (slowdown) in early 2025 to statistically insignificant speedups in late 2025.

### Cited Findings
**METR time horizons**
- TH1.1 (29 Jan 2026), 50%-success doubling times:

  | Window | Doubling time (TH1.1) | Earlier TH1.0 value |
  |---|---|---|
  | 2019–2025 | 196.5 days | 195.8 days |
  | Since 2023 | 130.8 days (CI 107–161) | 165.3 days |
  | Since 2024 | 88.6 days (no CI) | 108.9 days |

  — [METR TH1.1](https://metr.org/blog/2026-01-29-time-horizon-1-1/)
- Frontier 50% horizons (TH1.1):
  - Claude Opus 4.5: 320 min (CI 170–729).
  - GPT-5: 214 min.
  - o3: 121 min. — [METR TH1.1](https://metr.org/blog/2026-01-29-time-horizon-1-1/)
- METR caveats:
  - Only 31 tasks are 8 hours or longer, and only 5 of those have human baselines.
  - The suite is near saturation.
  - The trend shift is partly due to different task difficulty distributions: older models' estimates fell 35–57% while GPT-5's rose 55%.
  - There is scaffold sensitivity (Vivaria vs Inspect). — [METR TH1.1](https://metr.org/blog/2026-01-29-time-horizon-1-1/)
- Estimates above 16 hours are reported as unreliable due to saturation. **[snippet only]** — [LessWrong "METR time horizons now 10x/year"](https://www.lesswrong.com/posts/EYb2K9acKfyG2bome/metr-time-horizons-now-10x-year)
- Secondary sources cite a local doubling of about 49 days around Opus 4.6. This is unconfirmed by METR's published window fits. **[snippet only]** — [Substack tracker](https://akimakimov.substack.com/p/agi-progress-journal)

**METR developer uplift RCTs**
- Early 2025: AI made tasks take **19% longer** (CI +2% to +39%). — [METR uplift update](https://metr.org/blog/2026-02-24-uplift-update/)
- Late 2025 follow-up:
  - Returning developers: **−18%** time (speedup), 95% CI −38% to +9%.
  - New developers: **−4%**, CI −15% to +9%. — [METR uplift update](https://metr.org/blog/2026-02-24-uplift-update/)
- Problems with the follow-up:
  - 30–50% of developers withheld tasks they did not want to do without AI.
  - Selection bias from opt-outs, and a pay cut from $150 to $50/hr.
  - METR calls the estimates a likely lower bound and "only very weak evidence" of increased speedup, and is abandoning task-level randomization. — [METR uplift update](https://metr.org/blog/2026-02-24-uplift-update/)

**Anthropic Institute, "When AI builds itself" (June 2026, as reported; primary not opened)**
- Over 80% of merged production code is Claude-authored as of May 2026, up from low single digits in February 2025.
- Engineers merged about 8× more code per day in Q2 2026 versus 2024.
- Median self-reported research-staff output is about 4× with Mythos Preview (poll, n = 130).
- Success on the hardest open-ended engineering problems is 76%, up 50 points in 6 months.
- Agreement with human researchers on the "next step" rose from 51% to 64% (Nov 2025 → Apr 2026).
- In one safety-research demo, nine agents closed 97% of a gap versus 23% for two humans over a week.
- Anthropic says it is "not yet at recursive self-improvement" and calls its research evidence "more preliminary." — [The Next Web](https://thenextweb.com/news/anthropic-claude-recursive-self-improvement-code)
- An internal optimization benchmark reportedly rose from about 3× (Opus 4, May 2025) to about 52× (Mythos Preview, Apr 2026). **[snippet only]**
- A January 2026 spokesperson figure put company-wide code share at 70–90%. **[snippet only]** — [The Decoder](https://the-decoder.com/anthropic-says-claude-now-writes-over-90-of-its-code-and-wants-the-world-to-have-an-ai-pause-button/)

**Explicit indicator proposals**
- GovAI/Oxford, "Measuring AI R&D Automation" (Chan et al., arXiv 2603.03992, Mar 2026) proposes combining three kinds of metric:
  - capability evals on R&D tasks;
  - operational signals (compute use, capital share of R&D spending);
  - oversight-effectiveness measures (defects in AI-generated output).
- The paper says no single metric suffices and that labs hold the most informative data. **[snippet only]** — [GovAI](https://www.governance.ai/research-paper/measuring-ai-r-d-automation); [arXiv](https://arxiv.org/abs/2603.03992)
- An AGI-forecasting review suggests labs track the number and duration of agent-run experiments, the share of commits authored by AI, and error rates. **[snippet only]** — [arXiv 2604.22766](https://arxiv.org/pdf/2604.22766)

### Proposed measurable signatures (synthesized from the above; each maps to the derivation in Q3)

| # | Signature | Level jump | Recursion (r > 1) | Current reading (Nov 2026) |
|---|---|---|---|---|
| 1 | Successive doubling-time ratio for METR horizon / algorithmic efficiency | Step change, then ratio ≈ 1 | Ratio consistently < 1 (≈ 2^{1/r−1}) | Windowed fits shorten (196 → 131 → 89 d), but this is window-dependent and confounded by task mix and the 2024 reasoning-model regime shift. Not yet distinguishable from a step. |
| 2 | Algorithmic-efficiency halving time (compute-equivalent gains) | Constant (~8 mo, Ho et al.) | Shrinking over time | No 2026 update found. Gap. |
| 3 | Progress per unit of *physical compute* (hardware-constant r) | Flat | Rising | Not publicly measured. Whitfill & Wu's σ ∈ {≈0, ≈2.6} leaves it open. |
| 4 | AI share of research labor vs measured end-to-end R&D speedup | Share rises; speedup bounded by non-automated fraction (Amdahl) | Speedup rises superlinearly as share → 1 | Code share >80% (self-reported), but RCT uplift is small or insignificant. Code share ≠ R&D speedup. |
| 5 | Ratio of research output to compute input at labs (compute-bottleneck test) | Falls as labor becomes abundant (σ ≈ 0) | Holds or rises (σ > 1) | Unknown. Requires lab-internal data (GovAI). |
| 6 | Self-reported vs RCT-measured uplift | Persistent gap (early 2025: +20% expected vs −19% measured) | Converging large measured uplift | RCT methodology broke down in late 2025 (selection). No clean measurement. |

### Inferences
- **Hard-takeoff-leaning evidence:**
  - Shortening METR doubling times (the 2024+ window is about 2.2× faster than the full-period fit).
  - Rapid rise in AI-authored code and in internal "next-step agreement" metrics.
  - Forethought's r estimates above 1 in several domains.
  - Whitfill & Wu's baseline σ ≈ 2.6.
- **Slow-takeoff / red-team evidence:**
  - METR's own attribution of part of the speedup to task-composition changes, plus suite saturation above about 16 hours.
  - RCT uplift near zero or negative through 2025.
  - The frontier-experiments σ ≈ 0.
  - Ho et al.'s finding that 60–95% of past gains came from compute.
  - Bloom et al.'s strong diminishing returns.
  - Davidson's own about 40% weight on takeoff over 5 years.
  - Vendor self-reporting of the most bullish lab numbers.
- A one-time shift (e.g., RL-on-reasoning in 2024) would produce exactly the observed "faster in recent windows" pattern. A genuine test needs at least two or three further doubling intervals that each shorten, which at a ~3–4 month doubling means roughly 2027.
- "Share of code by AI" is a weak observable: it can approach 100% with modest total speedup if experiment compute, research taste, or review are the binding inputs (Amdahl / σ ≈ 0).

### Gaps
- No METR time-horizon release after early 2026 was confirmed in this session, so it is unknown whether shortening continued through Nov 2026.
- The Anthropic Institute primary report and the GovAI paper were not opened in full.
- No public lab data on hardware-constant algorithmic progress (signature 3) or experiment throughput (signature 5).
- No 2026 Epoch algorithmic-progress update was found.
