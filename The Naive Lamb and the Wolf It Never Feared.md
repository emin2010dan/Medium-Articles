# The Naive Lamb and the Wolf It Never Feared
## What a 1985 graduation thesis taught me about constraints, impossibility, and the courage to be wrong

---

The professor was kind about it. He told me the topic was too hard. He suggested I pick something else. He had been supervising master's theses for years, and he knew — better than I did — what the available methods could and could not do.

I thanked him and kept the topic anyway.

I was a final-year computer engineering student in Turkey in 1984. I had decided to build a system that could recognize hand-drawn digital logic circuits — AND gates, OR gates, flip-flops, the whole vocabulary of digital design — from freehand drawings on paper, with no restriction on the size of the symbols or the number of inputs per gate. The machine I had to work with was an Apple II+: a 1 MHz MOS 6502 CPU, 48 kilobytes of RAM, and a BASIC interpreter.

My professor was not wrong to be skeptical. The image processing courses I had audited — courses normally reserved for master's students, which I had specifically requested permission to attend — had shown me exactly why this was considered impossible. Every known method either required fixed symbol sizes, or a fixed number of inputs, or vastly more computational power than I had. The wolf, as far as the academic literature was concerned, had already won.

I was the naive lamb who hadn't read that memo.

---

## The Moment of Despair

Months into the project, I came across a paper describing a similar system — built at a well-funded laboratory, running on DEC minicomputers that dwarfed my Apple II+ the way a freight train dwarfs a bicycle. Their approach used mask matching: slide a template over the image, count the overlapping pixels, declare a match above some threshold. It was fast. It was clean. It worked.

And it only handled gates of fixed size with exactly two inputs.

At the time, I did not fully appreciate that last sentence. What I saw was: *someone else has done this, on hardware I could never have, and they got there first.* The despair was genuine. I had spent months on a problem that seemed solved.

But it wasn't solved. It was *started*.

Their system could recognize a two-input AND gate if it was drawn at precisely the right scale. Mine — if I ever finished it — would recognize any gate, at any size, with any number of inputs, drawn by any human hand with any degree of neatness. We were not solving the same problem. I just didn't have the confidence yet to see that.

---

## What 48 Kilobytes Forces You to Do

Here is the thing about extreme constraints: they do not merely restrict your options. They *eliminate the lazy ones*.

With 48 KB of RAM and a 1 MHz interpreter, mask matching was not on the table. Template libraries for gates with 2, 3, 4, 5, 6 inputs would have consumed the entire memory before I had written a single line of recognition logic. The comfortable path — the path the DEC system took — was not available to me. So I had to find another one.

The path I found was syntactical pattern recognition: representing circuit elements not as pixel templates but as *grammars*. A logic gate is not a particular arrangement of black and white pixels. It is a structural relationship between primitives — lines, arcs, curves — described by formal rules. Recognizing a gate becomes parsing a string according to a grammar, which a Finite State Automaton can do efficiently, regardless of the gate's size or input count.

This was theoretically elegant. It was also what the image processing literature said was appropriate for exactly this kind of problem. The trouble was that no one had implemented it under the constraints I was working under, on hardware this limited, for this specific domain.

I split the system into two layers. All pixel-level operations — noise elimination, line thinning, gap filling — were written by hand in 6502 assembly language, because the BASIC interpreter was too slow for dense image operations. The semantic layer — grammar parsing, gate recognition, circuit topology analysis — ran in BASIC, where development speed mattered more than execution speed.

The noise elimination alone required careful mathematical formulation. Hand-drawn images digitized at the resolution available to me were full of high-amplitude, low-frequency artifacts. I derived a threshold-based filter that operated on the derivative of the sampled coordinate sequence, eliminating isolated points and short spurious segments while preserving genuine line data. This ran in machine code because it had to.

Sherman's thinning algorithm — a 1960 method from a UNESCO conference proceedings, which I had tracked down in the library — reduced every drawn stroke to a one-pixel skeleton. Gap filling closed the inevitable breaks in hand-drawn lines. Width regularization smoothed the irregular edges that came from drawing with a stylus.

Only then did the grammar-based recognizer run. By that point, the input was clean enough for the Finite State Automaton to traverse, identify closed shapes, classify them by their structural properties, and label them as gates.

The constraint of 48 KB had forced me away from the brittle template-matching approach and toward a mathematically principled one that happened to be more general, more robust, and more theoretically sound. I didn't choose the better method because I was wise. I chose it because I had no choice.

---

## What the Wolf Actually Was

Looking back from forty years later, I think the wolf my professor warned me about was real — but I had misidentified it.

The wolf was not the technical difficulty. Technical difficulty is workable. You read more, you think harder, you find Sherman's 1960 paper in the library stacks and you implement it in assembly language.

The wolf was the psychological weight of *being told something is impossible by someone who knows more than you*. That is a different kind of obstacle. It does not yield to assembly language. It yields only to a particular kind of stubbornness that, in retrospect, looks either like courage or foolishness depending on how things turn out.

My professor was correct that the problem was hard. He was correct that the standard methods wouldn't work. What he could not have known — what I could not have known — was that the constraint of the Apple II+ would force me to abandon the standard methods entirely and find something better.

The naive lamb survived not despite its naivety, but partly because of it. It walked past the signs that said *wolf territory* and kept moving, and the wolf turned out to be standing in the wrong field.

---

## The Lessons, Stated Plainly

I have thought about this project many times in the forty years since. Here is what it actually taught me, beyond the obvious one about stubbornness:

**Constraints are not the enemy of good solutions. They are often their author.** Resource abundance permits laziness. When you cannot take the easy path, you are forced onto the correct one. The DEC system's mask matching was faster to build and easier to explain, but it solved a narrower problem. My 48 KB forced me toward a solution that scaled.

**"Impossible" usually means "impossible with known methods."** Every time my professor or the literature said this couldn't be done, what they meant — accurately — was that template matching, nearest-neighbour classification, and minimum-distance methods couldn't do it. That is true. But it is not the same as the problem being unsolvable. The map of known methods is not the territory of possible solutions.

**Being late to a problem is not the same as being beaten.** When I saw the DEC paper, I thought I had been scooped. I hadn't. They had solved a special case; I was working on the general case. The emotional experience of seeing prior work — the despair, the sense of futility — was real, but the logical conclusion I drew from it was wrong.

**Experts define the ceiling of the known, not the ceiling of the possible.** My professor's advice was sound given the state of the field. The state of the field was not the limit of what could be done. This is not a criticism of him — it is a structural feature of expertise. Experts know what has been tried. They do not always know what hasn't.

**The work you do under duress teaches you the most.** The image processing courses I audited, the assembly language I learned to write, the 1960 UNESCO proceedings I tracked down — none of this was required for the thesis. All of it was required to solve the problem. The pressure of the impossible specification drove a depth of learning that a comfortable topic never would have.

---

## A Note on Timing

I graduated in 1985 and moved on — to networking, to databases, to banking systems, to the practical work that paid salaries and built infrastructure. The question of whether I left AI research too early is one I have returned to more than once.

The honest answer is: probably not. The second AI winter arrived within a few years. Without the hardware to support learning at scale, the field stagnated for nearly a decade. The work I might have continued would have found no soil to grow in.

But the deeper truth is that the thinking never stopped. The instinct that led a twenty-something to take on an "impossible" thesis — the refusal to accept that difficulty means impossibility, the willingness to follow a constraint to its logical conclusion rather than retreating to a comfortable approximation — that doesn't switch off. It just finds new problems.

The naive lamb grows up. It learns where the wolves actually are.

It still walks into the field.

---

*The original 1985 thesis, including scanned pages of the typewritten report, hand-drawn figures, and Apple II printer output, is archived at [github.com/emin2010dan](https://github.com/emin2010dan/Graduation-Thesis-1985-Hand-Drawn-Logic-Design-Recognition).*
