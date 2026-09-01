# Research proposal: consolidated feedback

Everything Jasper Bouwmeester said about the proposal draft, from two sources combined: the 45 comments left in the Overleaf document, and the review meeting of 27 August 2026 (15:00 to 16:30, full note at `../Meetings/Meeting Notes 2026-08-27.md`). His comments are in Dutch; they are given here in English.

Read part 1 first. It holds the arguments that have to change, and most of them touch more than one chapter. Part 2 is about how the document is put together. Part 3 is the working checklist, in document order.

Overall verdict, given at the top of the meeting: **a good draft.** The number of comments should not be read as a negative. He reviewed it as the first chapters of the thesis rather than as a standalone proposal, which is why several comments go deeper than a proposal review would; only the planning chapter later drops out or becomes an appendix.

## Status

| Chapter | Comments | Open | Done |
| --- | --- | --- | --- |
| 1. Introduction and project background | 4 | 2 | 2 |
| 2. Mission and instrument context | 4 | 4 | 0 |
| 3. State of the art | 25 | 14 | 11 |
| 4. Research questions | 5 | 5 | 0 |
| 5. Research methodology | 6 | 5 | 1 |
| 6. Planning | 1 | 1 | 0 |
| **Total** | **45** | **31** | **14** |

"Done" means resolved in Overleaf, which is mostly what commit `700b02c` of 1 September fixed. Items below are tagged **[open]** or **[done]** to match.

---

# Part 1: The content

Seven arguments Jasper pushed on. These are the ones worth fixing properly, because each recurs in more than one place and several of them affect what the thesis actually does rather than how it reads. One of the seven, 1.2, turned out to rest on a misreading and is already settled; it is kept here because the wording that caused it still needs fixing.

## 1.1 The baffle-integration argument is only half told

Raised three times: in the scope list, and twice in the agreement-and-silence section. It also took up a good part of the meeting.

The draft rejects an integrated baffle and M2 mechanism because the baffle tolerates considerable inaccuracy while the mirror does not. Jasper: that is half the story, and on its own it is not a reason to keep them apart. If differing requirements were the whole problem you would simply design to the most demanding one and be done. There is in principle nothing wrong with a baffle deployment that is much more accurate than it needs to be.

The real reason is thermal. The baffle receives sunlight and albedo, so it heats and fluctuates. That is unwanted for the optics and the suspension, partly through limited thermal self-imaging in SWIR, but above all through unwanted thermo-mechanical dynamics. The tightest requirement becomes hard to meet precisely because a large and dynamic heat input drives thermo-mechanical change. Integration is thermo-mechanically much more complicated, not requirement-incompatible.

**Action.** Rewrite the scope bullet and the corresponding sentence in chapter 3 to carry the thermal argument. Drop or heavily qualify "incompatible accuracy requirements" as the reason given in the literature.

## 1.2 The packing ratio: a comment written on a misreading, settled in the meeting

**Resolved. No change of substance needed, but the wording that caused the misreading should be fixed.**

The Overleaf comment on the novelty claim reads as a hard challenge: the packing ratio for the structure itself is not very useful and can even be misleading; what is useful is isolating the effect of the deployable M2 on the packing ratio at system level, separately from other variables such as other deployables. A second comment, on the corresponding gap bullet, asks whether it is not understandable that reports give whole-telescope volumes, since system level is what you really care about.

**Both were written on the assumption that "the structure itself" meant the boom on its own.** In the meeting, once the definition was actually on the table, Jasper agreed with it. His words: he is completely in agreement, but there is a level below it that the wording seemed to include, namely the packing ratio of the boom or member alone, and he had briefly thought that was what was meant. He confirmed it: "I thought for a moment you meant the packing ratio of the boom itself, but you were on the right track."

**The definition, stated plainly.** The object is the M2 mechanism and nothing else. The figure is the volumetric ratio of the mechanism stowed to the mechanism deployed, bounded at the point where it mounts to the rest of the spacecraft and running to its furthest extent. Three levels exist and only the middle one is wanted: not the boom or member alone, not the satellite as a whole, and not other deployables such as solar arrays, which are not part of the object rather than something to be netted out of it. That is exactly the isolation Jasper was asking for.

So the metric stands and the novelty claim stands. Three refinements came out of the same discussion:

- **State the level, every time.** This is what the comment is really asking for. The boom level behaves differently: telescopic tubes slide into one another, whereas articulated booms keep roughly the same volume stowed as deployed, possibly slightly more because of the hinges. If the text does not say which level a figure is at, a reader lands where Jasper landed.

- **Record the baffle effect separately**, beside the ratio rather than inside it, so the boundary stays the mechanism. Jasper's point holds: a concept that flares at the base when stowed, the deployable truss above all, or one that swings outside the bus, family F, pushes the baffle outward and enlarges the stowed volume at system level. The baffle itself is not designed here, since that is another student's work; only the volume it is forced to occupy is recorded.

- **Report two envelopes per concept**, the minimum envelope around the wireframe and the cylinder or box it fits into, giving a range rather than a single number, with a qualitative note on how practical the shape is. The launch volume of interest is a box rather than a cylinder, because that is how small satellites get their volume on piggyback rides.

**Action.** Do not weaken the claim. Write the definition out in the terms above wherever a packing ratio is quoted, in the novelty bullet and the gap bullet above all, so the mechanism-level reading is unmissable and the phrase "the M2 structure on its own" is not left to carry it. Then resolve both comments in Overleaf, since they are answered.

## 1.3 Two effects the review never considers

Flagged at the end of the agreement-and-silence list as "very relevant, but not yet named". Both bear directly on the packing question above.

**The volume between mirror and baffle taken by the support structure.** The more room the structure needs there, the larger the baffle has to become, which in turn enlarges the stowed system volume. Anything that folds wide, a deployable truss above all, carries an enormous disadvantage here. In the meeting this came back as the open question for the four-bar linkage, which deploys into the space outside the bus where the baffle sits.

**Negative optical effects of the deployable structure.** Whether the structure sits in the optical path, and how it behaves for stray light. In the meeting Hugo noted this can be judged quantitatively, for instance three struts obstruct less than four. Note also that inward-folding booms normally need a spider, which is in-plane and unavoidably in the field of view.

**Action.** Both belong in the agreement-and-silence list, and the first should feed the packing-ratio definition.

## 1.4 The correction-stage assumption needs verifying, not assuming

On the scope bullet about active correction. Jasper is content for the scope to stay narrow, but would add a step to verify the assumption holds.

Two specifics. In a symmetric design there are deviations in **5 degrees of freedom**, not 6, because rotation about the mirror axis is not relevant. And with actuators at the bases of the three arms you have **no control over displacement in the X-Y plane**. The question is how large those displacements turn out to be and whether they fit within budget passively.

He also asks whether actuators exist that fit the resulting requirements on stroke and accuracy. Requirements for all 5 degrees of freedom are needed as an output of the instrument design, and failing that a well-formulated assumption.

**Action.** Add a verification step. Restate the working assumption as 5 DOF, and say explicitly what the three-arm-base arrangement cannot correct.

## 1.5 Wavefront error is the wrong budget

On the sentence quoting Villalba: deployment repeatability runs to a few micrometres while wavefront-error requirements run to tens of nanometres.

Wavefront error is a property of the mirror itself and therefore applies only to deployable mirrors. Different budgets govern the relative positioning of optical elements. Possibly sub-micron, but it depends heavily on wavelength, resolution and so on. The meeting added that the actual figure needs Jérôme Loicq's instrument design, since it depends on the instrument, the ground sampling distance and the signal-to-noise budgets; expect a micron or sub-micron rather than nanometres.

**Action.** Separate the two in the text. Do not use a wavefront-error figure as the standard the M2 placement has to meet.

## 1.6 The VLEO gap has to be argued, not asserted

On the bullet claiming no work covers CubeSat optics whose thermal environment is analysed at these altitudes.

Jasper understands that if you are specific enough you will eventually find no literature. The question is how relevant a given combination is. **Is the VLEO environment really very different from LEO? If so, in what respect?** He assumes examples exist in the 20 to 30 cm class; VLEO itself is fairly new, so it may well be the interesting angle, but the text has to say on what exactly: the thermal environment, or the atomic oxygen and drag.

**Action.** Research the LEO versus VLEO difference and name the mechanism behind the gap. A second comment on the same list asks which regime the stability claim refers to, VLEO or the scale.

## 1.7 The CORE hinge argument is inherited, not examined

On the TU Delft heritage line, where every design uses compliant rolling-contact hinges at the boom ends with a self-locking strip or slotted hinge in the middle.

Jasper wants the argument for that choice told, and critically questioned. The background he gives: the CORE hinge was developed on the idea that the system should not be overdetermined, to prevent warping. The compliant mechanism can therefore still move after deployment, but without the backlash and hysteresis typical of other hinge types. **However, it has never been simulated whether a locked hinge really would suffer too much warping, nor whether the flexible hinge might itself cause unwanted effects under transient or microvibration inputs.**

This is the same question as the latch-count and overdetermination study, and the meeting sharpened what to do about it: his estimate is that a decision deferred to the midterm is a decision dropped at the midterm, so it has to be planned explicitly now or let go. Hugo's counter, which he accepted: the thermo-elastic analysis and the microvibration response are already planned activities, so pushing an over-determined model through the same process gives a second answer to compare at little extra cost.

**Action.** Tell the argument and question it in chapter 3. Decide within about a week whether the study enters the plan.

---

# Part 2: The document

## 2.1 A thesis is not a chronological record

The most repeated structural point, made twice explicitly and referred back to a third time.

It is fine, and good, to note where parts of the work are still missing input. Ideally that data arrives over time, and when relevant input lands in good time it is better to **update it throughout the whole thesis** rather than leave the earlier chapters describing an older state. Concurrent engineering does demand a flexible approach, but the document should not read as a diary of what was known when.

The meeting added the reverse case: if the inputs simply arrive on time, a choice can still be made then to descope to a narrower range or a single value.

**Action.** Write in a way that anticipates updating. Keep a note of where input is missing, but do not build the argument around the order in which things became known. Applies to the introduction's paragraph on parallel instrument design and to the "three consequences" passage in chapter 2.

## 2.2 Forward references

Chapter 2 refers to "the two architectural regimes identified in the literature survey" before they have been introduced, and separately announces "this is the subject of sub-question 2".

Back-references are generally preferred, because the reader can follow them. Forward references are occasionally needed for a good thesis structure, but they are the exception. On sub-question 2 specifically: **do not introduce it there at all.**

**Action.** Either move the passage or add a proper reference to the relevant section. Remove the sub-question 2 sentence.

## 2.3 Chapter 4 belongs inside chapter 3

The research questions chapter should become the **last subsection of the preceding chapter**, because it follows logically from it. Confirmed in the meeting: the gap and the questions come out of the analyses.

## 2.4 Chapter 6 is the part that does not survive

Only the planning chapter later drops out of the thesis or moves to an appendix. Everything else is a thesis chapter already, which is why the comments go as deep as they do.

## 2.5 One scope paragraph is in the wrong place for the final thesis

**[done]** The paragraph on what the thesis does and does not do with the correction stage is fine for now, but not very relevant in that position in the final thesis.

## 2.6 Tables and figures

- **[done]** The nine families should be in a table, with extra explanation and a sketch. Now done as `tab:family-descriptions`.
- **[done]** Readability of the classification table could be better. Now improved with `addlinespace` and rebalanced columns.
- **[open]** The heritage section is very abstract; add illustrations, with correct attribution. Figures may be taken from the source papers.
- **[open]** The family figures are still `\famstub` placeholders, and the origami subfigure cites an unresolved key `XXX_origami`.

## 2.7 Register and word choice

- **[done]** "Precision", in the sense of how well a unit was built, invites confusion with a design parameter. Use quality or maturity. Now reads "quality".
- **[done]** "Orders of magnitude" for the lab-demonstrator versus flight-unit gap is overstated. A lab demo will not deviate by orders of magnitude, and some design parameters already carry fairly little uncertainty at that stage, packing ratio for instance. Now reads "significantly".
- **[done]** "Existence proofs" is better phrased as feasibility evidence.
- **[done]** "PLASMO is a paper study" is better as "currently a feasibility study".

---

# Part 3: By chapter

In document order. The Overleaf comments themselves are not in document order, so this section reorders them.

## Chapter 1: Introduction and project background

**[done] The parallel instrument design.** On the paragraph noting that mirror sizes and separations are not fixed and off-axis remains open. Good to mention. Note where the thesis still lacks input, but write it so it can be updated as data lands (see 2.1). A generic approach with PLASMO as the design case is good for future projects and for the science regardless.

**[open] The baffle scope bullet.** See 1.1. The accuracy argument is half the story; the reason is thermal.

**[open] The active-correction scope bullet.** See 1.4. Verify the assumption, 5 DOF not 6, and name what the three arm-base actuators cannot correct.

**[done] The scope paragraph's placement.** See 2.5.

## Chapter 2: Mission and instrument context

**[open] "No deployment-accuracy requirement exists."** Same chronology point as 2.1: write it so it can be updated. The accuracy budget as a deliverable is a sensible output in its own right, setting the inputs and assumptions against the outputs of the analyses.

**[open] "The two architectural regimes identified in the literature survey."** Not yet treated at that point. Either this is in the wrong place, or it needs a reference to the relevant section. See 2.2.

**[open] "This is the subject of sub-question 2."** Do not introduce it here.

**[open] The drag bound on length.** "The sweep of activity 1.2 therefore carries that bound as a constraint rather than treating the separation as free" is **not entirely clear**. Rewrite.

## Chapter 3: State of the art

The heaviest chapter, 25 comments.

### Scope and method of the review

**[open] Declare the AI use.** Did you use AI for this? If so, good to say so and to explain the method briefly. This is the screening of the roughly 300 abstracts.

The meeting added a second half to this: the document must also say what the 300 and the 111 papers are actually **for**, since nothing quantitative is done with them and they are not all cited. The same description could have come from the subset that is cited. Either carry the count through, for example a papers-per-family column in the classification table, or present it honestly as preparatory work used to find papers.

**[done] "Precision".** See 2.7.

**[done] "Orders of magnitude".** See 2.7.

**[done] "Existence proofs" to feasibility evidence.** See 2.7.

### The mechanism families

**[done] Put the nine families in a table** with explanation and a sketch.

**[done] Table readability.**

**[done] "Inward-folding" is too specific a family name.** You can also fold sideways, and the family can consist of more than two elements. Better to use **articulated booms**. Two further comments point back at this one, on the geometric viability envelope and on the family A verdict.

### Architectural properties

**[open] What is the definition of athermal?** The athermal designs Jasper has seen deliberately use **different** materials to minimise the thermo-mechanical effect at system level, which is the opposite of what the draft implies when it contrasts a single continuous member against a chain of dissimilar parts.

The meeting went further: athermal design mixes properties by definition, that is the whole idea. Earlier work found it either not fully achievable or only partly effective, and it enlarges the design, because the booms have to be lengthened so a return path in another material can compensate. The thermomechanically decoupled baffle already limits the thermal variation. **Agreed to scope it out**, with the reasoning written down.

### The TU Delft heritage line

**[open] The hinge choice.** See 1.7. Tell the argument and question it.

**[open] Add illustrations.** See 2.6.

**[open] Did you also look at the SuperSharp design?** The meeting resolved the confusion behind this: SuperSharp is a thermal-infrared baffle design and the SSTL concept is the one that integrated baffle and optics. They are two different projects, both in the UK, which Hugo had taken for one. So there is more integrated-baffle evidence than assumed.

### The families assessed

**[open] "F, driven four-bar linkage": why exactly four?** The family name asserts a bar count the evidence may not support.

**[open] "Retained as reference points": what do you mean by this?** You have a category above that says these are carried for now and a category below that says these fall away, so what do you intend to do with this one? This became the devil's-advocate exchange in the meeting: the carried families are to be modelled and compared fairly, while these would be compared unfairly. **Agreed to set families C and E aside** on their clear disadvantages, while still naming what each is good at.

**[done] The family A geometric limit.** Points back at the articulated-booms naming comment.

### Agreement and silence in the literature

**[open] Wavefront error.** See 1.5.

**[open] Go deeper on the integrated-baffle papers.** How mature are those designs? Do they name accuracy and possible thermo-mechanical issues? The meeting sharpened the stakes: if they were not worked out or modelled and do not discuss it, calling them naive is defensible; if they computed it and claim it is not a problem, our own assumption has to be re-examined. Three cases.

**[open] "Incompatible accuracy requirements."** See 1.1.

**[open] The VLEO claim.** See 1.6.

**[done] Which regime?** VLEO or the scale, on the in-orbit stability bullet.

**[done] The packing-ratio silence.** Is that not understandable, given that system level is what you are really interested in? Same misreading as above; see 1.2. The point survives as a drafting instruction: say which level the silence is about.

**[open] Two effects not yet named.** See 1.3. Support-structure volume between mirror and baffle, and negative optical effects.

### The gap and the novelty claim

**[resolved in the meeting] "A packing ratio that means something."** See 1.2. The comment reads as a challenge to one of the four novelty claims, but it was written on the assumption that the figure was for the boom alone. Jasper agreed with the mechanism-level definition once it was clear. Fix the wording so the level cannot be misread, then resolve the comment.

**[done] "Inward folding stops being the better answer and extending mechanisms take over": what do you mean?** The meeting clarified that the claim rests on an assumed crossover point and only against one criterion, so the text has to say which criterion is leading.

**[open] The off-axis aperture claim.** Certainly interesting given the current status. But this alternative can generate a lot of work, so keep an escape hatch. If it turns out in a few weeks that the design goes on-axis anyway, that is an opportunity to descope. The meeting confirmed on-axis is the working assumption, and that off-axis is awkward to carry into parametric modelling because it comes in many kinds.

## Chapter 4: Research questions

**[open] Move the chapter.** See 2.3.

**[open] Broaden the framing.** You could make it a **microsatellite telescope for Earth observation, with PLASMO as the design case**. That way the parameter ranges of interest are not necessarily set by the current state of the design, and the question becomes rather more scientific, while keeping a strong case-driven design focus. Two further comments point back at this one, on the validity sub-question and on the inward-folding-to-extending phrasing.

The meeting made the same point from the research side: a thesis should serve the project and also anyone interested in deployable optics, which argues for taking parameters as variable inputs from the start rather than running a sensitivity analysis afterwards.

**[open] "Active control ... and which passive measures".** Use **and/or**. Deployment accuracy is a one-time event.

**Not raised, and it should have been.** Sub-question 1 lost its named-candidate parenthetical when the shortlist was cut on 26 August. That changes a question Jasper agreed on 16 July, so it needs his ratification, and it never came up at the review. Put it to him on 10 September.

## Chapter 5: Research methodology

**[done] "PLASMO is a paper study."** Now "currently a feasibility study".

**[open] Activities 1.1 and 1.2: what exactly are you modelling?** What do you take as fixed values and what as variables? To arrive at meaningful model designs **you will have to do something with stiffness**. He also advises adding an activity before these two, in which you describe all inputs and outputs thoroughly.

This was the longest technical thread of the meeting. Stiffness has to be held comparable because it drives the dimensioning of the booms, but a line-and-point model has no volume, so nothing fixes the tube thickness. A single assumed thickness for every family is not quite fair, and each family breaks the assumption differently: trusses and masts are not monolithic booms, being larger but probably lighter; the four-bar linkage has members of different lengths and is only comparable fully deployed; articulated booms need a spider in the field of view; telescopic booms have progressively smaller segments. Felix Wilting's telescopic deployable boom work, done for the nulling interferometry project at a much larger scale (up to 32 m), carries worked-out stiffness formulas that would speed this up.

Also from the meeting: diving straight into modelling risks not knowing precisely what to model, so the parameters come first.

**[open] Activity 1.3, the criteria.** Split this off and make it the **first** activity, so you know better what you actually have to model.

**[open] Activity 2.1, ESATAN.** Add a **preparatory activity before the midterm** that determines all the inputs for these analyses.

The meeting gave the reasoning: collecting and defining inputs, the thermal environment and the microvibration assumptions above all, routinely costs far more time than the modelling, which is about a day's work once you know what you are doing. Each input needs its own slice of literature study and its own decision about how to model it, and some may be missing altogether. The midterm is where the plan is checked for executability, so a lot of unknowns there is a bad position.

**[open] Atomic oxygen.** Atox looks like a standalone matter that could be handled earlier, under activity 1.5, alongside the cold model and material selection.

**[open] The two deferred decisions.** The latch-count and overdefinition question could already be relevant at activity 1.4, though it can be left open there, and it also looks relevant for 1.5. So the question is whether this is really something to decide at the midterm, or perhaps already after 1.3. See 1.7.

## Chapter 6: Planning

**[open] Use the activity numbers.** Why not use the activity numbers you defined earlier? The planning table names blocks and work in prose while the methodology chapter numbers everything 1.1 to 2.4; the two should line up.

---

## What the 1 September commit already changed

Commit `700b02c`, "Post meeting minor changes", touching `chapter-3.tex`, `chapter-5.tex` and `introduction.tex`:

- Added `tab:family-descriptions`, a table with an architecture line per family, plus a nine-panel figure block. The panels are still `\famstub` placeholders and one citation key is unresolved.
- Reworked the classification table's readability.
- "Precision" to "quality", "orders of magnitude" to "significantly", "existence proofs" to "feasibility evidence", "paper study" to "currently a feasibility study".
- Corrected the geometric viability envelope to the length or width of the satellite bus.
- Removed the "Status at this review" section from the introduction.

## Where the rest is written down

- `../Meetings/Meeting Notes 2026-08-27.md` for the full meeting, including the decisions and the action table.
- `../../../../../../../wiki/sources/src-2026-08-27-jasper-bouwmeester-meeting.md` for the ingested summary and the open threads.
- `../../../../../../../wiki/syntheses/deployment-architecture-survey.md` for the family verdicts and the packing-ratio definition.
- `../../../../../../../wiki/syntheses/thesis-method.md` for the phase-1 modelling method and the stiffness problem.
