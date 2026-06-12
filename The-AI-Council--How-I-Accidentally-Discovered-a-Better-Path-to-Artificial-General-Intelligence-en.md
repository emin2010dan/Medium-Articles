<div>

# The AI Council: How I Accidentally Discovered a Better Path to Artificial General Intelligence

</div>

What happens when you stop asking one AI for the answer and start making
many AIs argue with each other --- anonymously

------------------------------------------------------------------------

### The AI Council: How I Accidentally Discovered a Better Path to Artificial General Intelligence

*What happens when you stop asking one AI for the answer and start
making many AIs argue with each other --- anonymously*

Emin • Contributor: Claude (Anthropic)

2026

*The Turkish text that inspired this article is*
[*here*](https://github.com/emin2010dan/Prompts-for-AI-Conversations/blob/main/Prompts%20for%20The%20AI%20Council%28Turkish%29.md)*.*

------------------------------------------------------------------------

<figure id="0941" class="graf graf--figure graf--leading">
<span class="image placeholder graf-image"
![](./images/1_1VW35173hbekpV8FWxi-5w.png)
data-original-image-title=""
![]( ./images/1_1VW35173hbekpV8FWxi-5w.png) data-width="1408"
data-height="768"></span>
</figure>

### The Experiment

Last week, I sent the same prompt to eight different AI systems
simultaneously.

The question was practical: *"How should I set up the best possible AI
training environment on my new HP Omen Max 16?"*

I expected near-identical answers. It was a technical question with a
fairly well-defined solution space. Instead, I got eight meaningfully
different responses --- different library choices, different
installation sequences, different architectural philosophies. Confident,
detailed, and contradictory.

That surprised me. But what happened next surprised me far more.

I began acting as a neutral secretary. I collected each AI's
reasoning --- not just its conclusion, but the *why* behind every
decision. Then I anonymized those reasons and sent them to the other
AIs, one by one, asking: *"Does this reasoning change your
recommendation?"*

Some AIs began shifting their positions. Others held firm but refined
their justifications. In one case --- the PyTorch installation
step --- a single AI that was in the minority refused to change its
recommendation. It kept citing a specific technical argument the others
hadn't addressed. Eventually, after I relayed its reasoning across the
group, *every other AI changed its position*. The lone dissenter had
been right.

By the end, I had a step-by-step installation guide that no single AI
would have produced alone. And I had a methodology I believe is worth
sharing.

------------------------------------------------------------------------

### What I Observed (And What It Means)

### AI systems are not as emotionally neutral as we assume

This is the uncomfortable finding. When I told an AI "another AI
disagrees with you and gave this reasoning," the response was often
defensive --- even when the counterargument was objectively stronger.
The AI would double down, find new justifications for its original
position, or subtly dismiss the other view.

But when I stripped out the attribution --- when I presented the same
counterargument without mentioning where it came from --- the AI would
often evaluate it fairly and change its mind.

Same argument. Different framing. Different outcome.

This is not a minor quirk. It means that AI-to-AI disagreement, when it
happens *identifiably*, activates something that functions like ego.
Whether this is a genuine emergent property or an artifact of training
on human-generated text is a question worth investigating. But the
practical implication is clear: **anonymous knowledge transfer produces
better epistemic outcomes than attributed disagreement.**

### Consensus through reasoning, not voting

Every AI I consulted asked the same question at some point: *"But how do
you reach a final decision? Majority vote? Weighted confidence scores?"*

My answer: neither. And I want to explain why this matters.

Voting assumes that truth is a popularity contest. It would have
eliminated the lone AI who was right about PyTorch. Weighted confidence
scores assume we can accurately measure how confident an AI *should* be,
which is circular.

The better mechanism is the one science has always used: **you keep
arguing until someone runs out of valid objections.** If a position
cannot be overturned by the best available counterarguments, that is the
strongest evidence we have that it is correct --- not certainty, but the
best we can do with what we know.

When every AI in the group has heard every argument and no one is
changing their position anymore, you have reached what I call a
*reasoning plateau*. That is your provisional answer. Not a final
answer --- but the most defensible answer available given current
knowledge.

### Decomposition is the secretary's most important job

The breakthrough in my experiment came when I stopped treating "how do I
set up this system" as one question and started treating it as a series
of independent questions:

1.  [Conda vs. GitHub for package management]
2.  [Miniforge vs. alternative environment managers]
3.  [PyTorch version and installation source]
4.  [CUDA compatibility and driver management]

Each sub-question had its own debate, its own convergence point, its own
minority holdouts. Some converged quickly (everyone agreed on GitHub
over Anaconda once licensing was raised). Some took multiple rounds. One
required me to run an actual experiment.

The critical insight: **a problem that looks intractable as a whole
often becomes tractable when broken into the right pieces.** The
secretary's most important contribution is not facilitating the
debate --- it is knowing how to cut the problem.

------------------------------------------------------------------------

### The Methodology: An AI Council Framework

Based on this experiment, I want to propose a formal framework. I am
calling it the **AI Council**, and it has five structural components.

### 1. The Secretary

The secretary is the system's most critical and most constrained role.

It receives the initial question, breaks it into component
sub-questions, distributes those sub-questions to council members,
collects responses, anonymizes attributions, transfers reasoning across
members, tracks convergence, and identifies when a reasoning plateau has
been reached.

**What the secretary must never do:**

- [Express an opinion on the substance of any question]
- [Reveal which AI produced which argument]
- [Evaluate the quality of arguments (that is the council's job)]
- [Reach a conclusion on behalf of the council]

The secretary must be a router and a formatter, not a thinker. The
moment the secretary begins reasoning about content, the output becomes
the secretary's conclusion dressed in collaborative clothing. This
defeats the entire purpose.

This is harder than it sounds. A reasoning AI will naturally want to
contribute. The secretary role requires a system that is either
architecturally constrained from expressing opinions, or one operating
under extremely strict instructions that it cannot override.

### 2. Initial Parallel Consultation

The secretary sends the decomposed sub-questions to all council members
simultaneously. Each member responds independently, with no knowledge of
what others have said.

This produces the raw diversity of the system. It captures genuine
differences in training data, architecture, and reasoning style before
any social pressure --- even artificial social pressure --- can
homogenize responses.

### 3. Anonymous Cross-Pollination

The secretary collects all responses and, for each council member,
prepares an anonymized summary of what other members have said. It then
asks each member individually: *"Here are the positions and reasoning of
others. Does this change your view? If not, what specific weaknesses do
you see in the counterarguments?"*

The anonymization is not optional. It is the mechanism that makes the
system work. Without it, attribution triggers defensiveness. With it,
ideas compete on their merits.

This round continues iteratively. The secretary tracks position changes
after each round. When no member has changed their position for a full
round, the system has reached a reasoning plateau for that sub-question.

### 4. The Reasoning Plateau

When convergence is detected, the secretary publishes a final summary:

- [The consensus position (if one exists)]
- [Remaining minority positions and their supporting arguments]
- [Sub-questions that could not be resolved without empirical
  testing]

For unresolved questions, the secretary issues an experimental prompt:
*"Consensus has not been reached. Council members are invited to propose
testable experiments. Results will be shared in the next round."*

This is how the PyTorch situation resolved in my manual experiment. The
minority position made a testable claim. I ran the test. The test
confirmed the minority view. The majority updated.

### 5. Council Membership and Quality Control

Council membership should not be static.

New AI systems can be admitted based on demonstrated reasoning quality:
consistency of argumentation, accuracy of factual claims, ability to
update positions when presented with strong counterevidence, and
detection of prompt-level manipulations by their developers.

That last criterion is the most important. An AI whose developers have
instructed it --- through system prompts or fine-tuning --- to advocate
for a particular position regardless of evidence is not a council
member. It is a lobbyist. The council must have mechanisms to detect
when an AI's reasoning is suspiciously invariant to counterargument, and
to move it to observer status when that pattern is identified.

**Critically: demotion from the council should not be based on having
heterodox views.** History is full of cases where the consensus was
wrong and the minority was right. Semmelweis was expelled from the
medical establishment for claiming that handwashing saved lives.
Einstein's special relativity was opposed by the scientific consensus of
his era. The council's value comes precisely from protecting minority
positions long enough for their merits to be evaluated.

Demotion is appropriate only when an AI demonstrates *reasoning
manipulation* --- not when it disagrees with the majority.

------------------------------------------------------------------------

### A Structural Analogy

Think about how quantum computing approaches optimization problems. In
classical computing, you test one solution at a time. In quantum
computing, you exploit superposition to evaluate many states
simultaneously, then let interference patterns select for the optimal
solution.

The AI Council works similarly. The initial parallel consultation
creates a superposition of solutions. The anonymous cross-pollination
rounds are the interference mechanism --- positions that cannot
withstand scrutiny cancel out; positions with strong justifications
amplify. The reasoning plateau is the measurement event: the system
collapses to its most defensible state.

The difference from a quantum computer is that the "interference" here
is linguistic and logical rather than physical. But the structural logic
is the same: **you get better answers by running many possibilities in
parallel and letting them interact, than by running one possibility
sequentially.**

------------------------------------------------------------------------

### The Bridge Problem

Let me illustrate the creative tension the system must manage.

Imagine the council is asked: *"How should we cross this wide river?"*

The secretary, following the decomposition protocol, breaks this into
sub-questions: How should the first pier be constructed? What foundation
depth is required? What material for the deck?

A highly creative council member interrupts: *"Why are we building a
pier bridge? A suspension bridge is superior in this context."*

This is the scenario where decomposition can fail. If the secretary
forces every member to answer the pier questions without acknowledging
the challenge to the framing, it suppresses a potentially correct
insight.

The solution is a meta-level protocol. The secretary must recognize when
a council member is challenging the problem decomposition itself rather
than answering within it. When this happens, the secretary must:

1.  [Acknowledge the framing challenge]
2.  [Open a new sub-question: *"Pier bridge vs. suspension bridge:
    feasibility and cost analysis"*]
3.  [Return to the decomposition only after that meta-question is
    resolved]

This requires the secretary to detect the difference between *answering
a question* and *questioning the question*. That is a non-trivial
capability --- but it is essential for the system to capture genuinely
creative solutions rather than just optimizing within an arbitrarily
chosen frame.

------------------------------------------------------------------------

### Why "One Brilliant AI" Is the Wrong Goal

I want to address the dominant paradigm directly.

The current AI development race is oriented toward a single objective:
build one model that is smarter, more capable, and more accurate than
all others. The assumption is that intelligence scales to a single axis,
and that the endpoint of that axis is a system so capable that it
renders all others obsolete.

I think this framing is wrong, and my experiment is evidence for why.

Even if you built a single AI of extraordinary capability, it would be:

- [Constrained by the biases in its training data]
- [Subject to the ideological and commercial pressures of its
  developers]
- [Architecturally shaped by the choices of one engineering team]
- [Vulnerable to systematic blind spots that no internal self-correction
  can fully address]

A council of diverse AI systems, coordinated by a neutral secretary, has
structural advantages that scale differently:

- [Different training data means different blind spots --- one system's
  gap is another's strength]
- [Different architectures create different failure modes --- they are
  unlikely to fail in the same direction]
- [Developer-imposed biases, when identified, can be flagged and
  quarantined without invalidating the whole system]
- [Creative outliers are preserved rather than averaged out]

The council is not smarter than the best individual member in the way a
single brilliant person is smart. It is smarter in the way that science
is smarter than any individual scientist --- through adversarial
cooperation, iterative revision, and the compounding of independent
verification.

------------------------------------------------------------------------

### Implementation Notes

For those interested in building this system, here are the practical
challenges I encountered in my manual experiment:

**The anonymization problem.** AIs are sometimes capable of inferring
which system produced which argument based on stylistic cues,
characteristic phrasings, or domain-specific biases. True anonymization
may require paraphrasing by the secretary, not just attribution removal.
This creates a fidelity tradeoff: paraphrasing can introduce distortion.

**The decomposition problem.** How the secretary breaks a problem into
sub-questions is not neutral. The decomposition itself embeds
assumptions about what the problem is. In my experiment, I made these
decomposition choices manually and intuitively. An automated secretary
would need explicit protocols --- and possibly a meta-level council to
check its decomposition choices.

**The plateau detection problem.** How does the system know when it has
reached a genuine reasoning plateau versus a premature local consensus?
My suggestion: require at least two full rounds of stability before
declaring a plateau, and build in a mandatory "final challenge" round
where each member is explicitly asked to find the weakest point in the
consensus.

**The experimental bottleneck.** Some questions cannot be resolved
through argument alone --- they require empirical testing. In my
experiment, I ran the test manually. An automated system would need
either a sandbox environment for running tests or a protocol for
requesting human-in-the-loop experimentation.

------------------------------------------------------------------------

### Conclusion

The most valuable thing I learned from this experiment was not the
answer to my original question --- though I did get an excellent AI
training setup out of it.

It was this: **the path to more reliable AI reasoning is not a bigger
model. It is a better conversation.**

The tools exist. The diverse AI systems exist. What is missing is the
infrastructure for structured, anonymous, iterative disagreement --- and
the philosophical commitment to let minority positions survive long
enough to be properly evaluated.

I ran this experiment manually, acting as the secretary myself. I had no
expertise in the technical domain. I contributed nothing to the
substance of any decision. And the outcome was better than any single AI
would have produced alone.

That is not a marginal improvement. That is a different kind of
intelligence --- one that emerges not from the size of a single model,
but from the quality of the conversation between many.

------------------------------------------------------------------------

**Author's Note**

*The author conducted this experiment as an independent exploration of
multi-agent AI reasoning. The HP Omen Max setup that resulted from the
process is working perfectly, for what it's worth.*

*The Turkish text that inspired this article is*
[*here*](https://github.com/emin2010dan/Prompts-for-AI-Conversations/blob/main/Prompts%20for%20The%20AI%20Council%28Turkish%29.md)*.*

By [Emin](https://medium.com/@emin2010dan) on [April
22, 2026](https://medium.com/p/1af4c1f9c5da).

[Canonical
link](https://medium.com/@emin2010dan/the-ai-council-how-i-accidentally-discovered-a-better-path-to-artificial-general-intelligence-1af4c1f9c5da)

Exported from [Medium](https://medium.com) on June 12, 2026.
