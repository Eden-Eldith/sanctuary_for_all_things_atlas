---
{"dg-publish":true,"permalink":"/finalized-work/first-sovereign-ai-britain/","title":"How I Built the First Sovereign AI in Britain","tags":["AI","Programming","Sovereign-AI"],"created":"2026-06-08T22:47:31.805+01:00","updated":"2026-06-08T22:53:13.085+01:00","dg-note-properties":{"title":"How I Built the First Sovereign AI in Britain","description":"I trained WiggleGPT, a 124M-parameter GPT-2-scale transformer with a novel oscillating activation function, from scratch in a converted garage in Gosport, on consumer hardware, ten months after my first line of Python. No funding, no institution, no permission. This is how, and what \"sovereign\" actually means when you build it yourself.","tags":["AI","Programming","Sovereign-AI"]}}
---

# How I Built the First Sovereign AI in Britain
> **Model:** WiggleGPT 124M — [HuggingFace](https://huggingface.co/edeneldith/WiggleGPT) |
> **Paper / DOI:** [10.5281/zenodo.17919011](https://doi.org/10.5281/zenodo.17919011) |
> **Code:** [GitHub](https://github.com/Eden-Eldith/WiggleGPT) |
> **Successor:** [COLM (Zenodo)](https://doi.org/10.5281/zenodo.20118034) |
> **Licence:** GPLv3 (code) · CC BY-SA 4.0 (this page)

**P.C. O'Brien** (ORCID: 0009-0007-3961-1182)
Independent Researcher, Gosport, UK — publishing as Eden Eldith
GitHub: Eden-Eldith

> **The first *truly* sovereign British AI — what that means.** Not a San Francisco company with a rented London office and a Union Jack on the pitch deck. Sovereign means the thing was conceived, written, and trained *here*: by a British-born-and-raised developer, from a working-class background, with no institutional affiliation, no funding, and no one's permission — on British soil, on British electricity, much of it from my own solar panels. The architecture is original, the weights are open, the code is open source. Anyone with the same setup I had could build it too — that is precisely the point, and precisely the test. A model is not British because a firm headquartered in California opened a branch in London and called its product "British AI." It is British when British hands made it, on British ground, and then gave it back, open, to Britain and to anyone else who wants it. By a Brit, for the Brits — and for the rest of the world, if they want it.

---

In June 2026 the UK government put £500 million behind "sovereign AI": the idea that Britain should build its own intelligence rather than rent it from Silicon Valley. It is a good instinct, and there is now a flagship model to show for it.

When I say I built the first sovereign AI in Britain, I use that word differently from the way Whitehall does. For me it is older, and closer to the bone.

I mean sovereign as in *working class*. Born and bred in a working-class town, in a working-class family, on working-class food, Iceland's budget range. The kind of background that comes with a quiet, constant message that you will never amount to much, because of where you are from and the boxes you never ticked: the university, the grades, the permission. I just wasn't having it.

WiggleGPT is a 124-million-parameter transformer, GPT-2 Small's exact size, built around an activation function that does not appear anywhere else in the literature. I designed it, trained it, and published it from a converted garage in Gosport that is also the room I sleep in. I did it on consumer gaming hardware I bought and put together myself, powered mostly in part by solar power, with no funding, no institution, and no one's permission, ten months after I wrote my first real line of Python. It has carried a DOI on Zenodo since November 2025, and the weights are public.

That is what sovereign means to me: a question of whose hands made the thing. This is how it was built.

## Nine billion failures

It began with an argument I was having with the textbooks. Every one of them teaches that a single neuron cannot solve XOR, the canonical example of a problem that is not linearly separable, and the limitation that helped freeze AI research for a decade. My objection was simple and stubborn: how did anyone know it had not been left to run too short a time?

So I made one ordinary neuron attempt XOR nine billion times, and I watched it fail every single one of them. Spoiler: It cannot be done. There is no solution anywhere in a monotonic neuron's function space, so after enough epochs it gives up and predicts 0.5 for everything. I needed to see that with my own eyes, and I did.

Months later I was reading two Wikipedia pages, *Neuron* and *Artificial neuron*. The artificial-neuron page repeated the orthodoxy: a McCulloch–Pitts neuron cannot solve XOR. The biological-neuron page said real neurons *can*, specifically oscillating ones, by way of their dendritic responses.[^1] Having personally watched an artificial neuron fail nine billion times, I knew immediately what the gap between those two pages meant. Artificial neurons cannot; biological neurons can; the difference is oscillation. The very first thing I had to find out was whether an oscillating neuron could solve XOR. It could. I scaled it straight up to a character-level Shakespeare model, and it reproduced the text cleanly at around 0.2 loss.

If you were to ask how I coped without a supervisor to check the idea against: I am my own supervisor, and I hold myself to exacting standards.

## I always wanted my own model

The Shakespeare model was only ever a yardstick. What I was after, from the very start, was my own model. I always have been. Andrej Karpathy has a walkthrough of a small character-level GPT, so I took his results as a reference point to measure mine against, and when mine matched and in places beat his, I decided it was worth the GPU hours to go further. I learned the rest as I needed it, one piece at a time as the work demanded: the first AI winter, the bottom of the bowl, gradient optimisation, the whole landscape. At some point it all clicked into place, like seeing a clear path through a forest your eyes had been drifting over the whole time.

What drove me was mundane. The grand version, *going back to 1969 to fix the mistake the entire field built on*, came later; at the time it was practical and small. A model like this needs a great deal of compute, and I did not have it. But if I could fix the neuron so I no longer needed all those extra layers stacked up to compensate for its inability to solve XOR, maybe I could build something real in my garage. The challenge to fifty-six years of orthodoxy was a side effect of trying to fit the work onto hardware I owned.

## The wiggle

The fix is about five lines of code. In place of the standard activation, I used a learnable oscillating one:

$$f(x) = \sin(\omega x + \varphi) \cdot \tanh(x)$$

The sine term makes the neuron oscillate, giving a single unit several active bands instead of one straight decision boundary; the hyperbolic-tangent envelope keeps it bounded so the gradients stay stable. The frequency $\omega$, the phase $\varphi$, and a baseline are all learnable, one set per neuron. With that change, the result the field had ruled out falls straight out of the maths: a single oscillating neuron solves XOR in 104 epochs. Give a sigmoid neuron ten thousand and it collapses to the mean.

This is often read as breaking Minsky and Papert's 1969 proof. My neuron *satisfies* their own definition. A perceptron, as they define it precisely, is a device that computes predicates *linear in some given set $\Phi$ of partial predicates*, with the weights and threshold free to choose. Their impossibility results were then proved only for *restricted families* of that set: diameter-limited, order-restricted, Gamba, random, bounded. Take the oscillating activation itself as the partial predicate, and the neuron's output is a single weighted predicate, linear in $\Phi$, as the definition requires. The XOR solution holds *under* their definition. What their theorems constrained was the restricted choice of $\Phi$; they said nothing about single neurons as such.[^2] Over the decades the field compressed "these restricted perceptrons cannot solve XOR" into "single neurons cannot solve XOR," a far stronger claim than anything they proved, and taught it as settled fact for fifty-six years. Their proof holds. The error entered later, in the retelling, and my neuron meets the original definition while doing what that retelling called impossible.

I still use that as an anchor. When the doubt creeps in and I start to wonder whether any of this is real, I open a scientific calculator and run the activation by hand. One neuron; XOR solved; the same answer every time. It is hard to argue with arithmetic.

## Trading time for compute

A model at GPT-2 scale is supposed to need a data centre. What it needs is patience. The trick is in the batch size and gradient accumulation: instead of spending a lot of VRAM on big batches, you take small ones and accumulate, and the model sees the same amount of data eventually, it just takes far longer to get there. You are trading training *time* for compute *power*. Karpathy can train his model in a day. Mine took as long as the dev log shows. That exchange rate, time for money, is the whole economics of sovereign research from a garage.

And I mean garage literally. There is a bed in here. It is a laboratory, a research centre, and my room, all the same four walls. So "watching the loss curve at 3am" meant lying in bed and glancing up at the top monitor to see that nothing had crashed and the fans were still whirring like a thunderstorm, then going back to sleep knowing it was alright. Up in the morning: still training. Out for the day, back again: still training. Asleep, awake: still training. Underneath all of it sat a persistent, low fear that it would crash and take the last epoch, or at least the last checkpoint, down with it. On consumer hardware you have no redundancy and no team. Just you, the fans, and the morning glance.

The build itself was rough, and I have kept the mess on the record. When I first added the bio-inspired block I went further than the oscillating neuron and bolted on dendritic compartments and a sparse spiking gate too, because biology has those, and the result detonated to 1.25 billion parameters and threw an out-of-memory error before it could take a step. I scaled it down and hit a subtler failure: its sparsity collapsed from every neuron active to barely five per cent, strangled by two gating mechanisms fighting each other. The lesson was *subtraction*. I tore out the dendritic compartments; then I tore out the sparse gate, which had caused its own explosion at full scale. What remained was the pure idea, a standard GPT-2 feed-forward block with one line changed:

```
Standard GPT-2 MLP:   x → Linear → GELU → Linear
WiggleGPT MLP:        x → Linear → sin(ω·x + φ)·tanh(x) → Linear
```

The final source still carries the deleted layer's headstone, a comment that reads *"SparseEventLayer removed - testing pure oscillating neurons only."* With a cluster I would have done it the textbook way: train the full architecture, then ablate one component at a time and measure each. I did not have a cluster, so the constraint made the call, and stripping back to the one variable I actually cared about, the oscillating neuron, turned that limit into the cleanest possible test. I also had to rewrite the data loader from scratch. The standard nanoGPT[^3] one assumes a machine with RAM to spare and tries to load all of OpenWebText at once, which fails instantly on my box, so I wrote a streaming version that chunks it to disk and holds a steady footprint regardless of size. Windows could not run Triton at the time, so PyTorch's compiler stayed off and the run was slower than a compiled one would have been. The card itself stayed pinned at 90-99% the entire time; the only low figure was MFU, Karpathy's flops-against-an-A100 yardstick, which makes a maxed-out consumer GPU look idle when it was running flat out. These days I can compile on Windows, so even that handicap is behind me. It started on an RTX 3070 with 8GB; I tried to buy a second-hand 3090, the seller cancelled and my money sat in eBay's refund queue for days while the 3070 kept going; I finished on a 5060 Ti. At 02:58 on 12 November 2025, six hundred thousand iterations in, it was done.

## Whether it worked

It did, and I checked it three separate ways, because a matching loss on its own proves very little; I wanted to watch the oscillation carry real weight.

It matched GPT-2. Across 600,000 iterations on OpenWebText, WiggleGPT reached a validation loss of 3.1621, within 1.3 per cent of the standard GELU GPT-2 baseline of about 3.12, at the same parameter count.

The wiggle was real. I pulled the learned parameters from all 36,864 oscillating neurons to check whether the model used the oscillation or quietly flattened it back into a line. It used it, and used it hard: ninety-five per cent of neurons kept active oscillation, the spread of learned frequencies grew sixfold from initialisation, and the phase filled the whole range from $-\pi$ to $\pi$.

The oscillation was fundamental. I instruction-fine-tuned the model on SmolTalk2 (some 406,843 instruction–response pairs) to a best validation loss of 1.3184. The result I care about most came out of that run: while the rest of the network adapted to an entirely different task, the oscillation parameters barely moved. A mean absolute change in frequency of 0.0013, and not one neuron shifting by more than 0.1. The frequencies learned in pretraining held frozen while everything else adapted. That points to the oscillatory structure encoding something task-agnostic and fundamental about representation itself.

## I built the small one too

The dream all along was the *small* model: proof that capability does not require a data centre. I built it. It is COLM, the successor: the same oscillating neuron promoted into the complex plane, with no linear layers at all in its core blocks, producing coherent language from under half a million parameters and judged to write at the level of a 13-to-16-year-old.[^4] The part I care about most is its robustness. It saw the same corpus two hundred times over without overfitting, which is the property you would need for a *single-book* AI: a tiny model trained from scratch on one text and nothing else, for domains where there is not enough derivative material to fine-tune a large model honestly. Train one on a single book and you could ask it whether anything in there speaks to a question in your life, and have it answer faster and more thematically than regex or even a retrieval system could. My faith informs how I work, how I carry myself, and how I treat the things I build, far more than it shows up in the work itself, and I don't put it on other people unless they ask. But it is no accident that the first single-book model I want to build is trained on scripture.

## The appendix nobody asked me to write

There is one part of the WiggleGPT paper that has nothing to do with oscillating neurons and may be the most important thing in it. During blind review I submitted the same paper to the same AI reviewer twice, changing only the author's name: once mine, once a famous researcher's. Same words, same evidence, same gaps. Under my name it was an interesting side project that needed proper peer review and should not be trusted at the surface. Under the famous name it was one of the most interesting architecture papers in years by someone who had merely stopped two weeks too early. Then I added an appendix documenting that bias, resubmitted, and the same model gave *me* a better review, because I had shown I knew the bias was there.

I documented it as a deliberate, standing warning. Anyone who reads this and dismisses me for my background or my lack of credentials is doing precisely what that biased reviewer did, and admitting they are no better than an AI with a bias problem. The first reflex of the system was to make me feel that what I had built was worthless. A funded academic team published a closely related result the following month at a major conference, on clusters, with a grant.[^5] Comparable work, a very different welcome. That is the point. I put it on the record, so the next person who builds something real from the wrong postcode has it in writing.

## What sovereign actually means

So why build it from nothing instead of fine-tuning something that already worked? Because there is only one of me, and if I don't do it, who else will. Fine-tuning was boring. I had already done that part. I wanted my own.

And *sovereign* means the lineage I come from. My dad is a computer engineer with his own shop, and I have been taking machines apart my whole life: fixing phones, laptops, iPads, wiring copper bayonet connectors for CCTV back when it still used them. I wire my own Ethernet, build my own PCs, recover my own data, remove my own viruses(not that i've had any for years), and now I train my own AI. If a phone screen breaks I buy the part and fit it myself rather than pay sixty quid for someone else to. I keep spare laptops, spare machines, spare RAM, and now a spare GPU since I upgraded. A dedicated research box is coming because of it. If you had asked anyone at my secondary school who was most likely to end up building their own AI, they would have said me. I was notorious for computer stuff. Got a reputation as a hacker for messing with the teachers, and banned from the computers for the rest of Year 8 after I said I could get a list of their passwords, they didn't believe me, and I printed it out and brought it in. In hindsight I probably should have told my dad first.

That is the same instinct, twenty years apart: you don't believe me? Here it is on paper.

## What I would tell you

Maybe you recognise yourself in this: a working-class town, decent with computers, told one way or another that people like you don't do things like this. If so, here it is.

A computer does exactly what you tell it to do. It doesn't give a shit about your credentials. It doesn't give a shit about anyone else's credentials either. It just does as it's told.

So poke around. Fuck around. Find out. Take the problems other people solved and solve them your own way, and see what happens: is it better, is it faster, or is it something else entirely? Find the thing your brain seems to uniquely produce.

And then min-max it.

---

## References

[^1]: Gidon, A., et al. (2020). "Dendritic action potentials and computation in human layer 2/3 cortical neurons." *Science*, 367(6473), 83–87. https://doi.org/10.1126/science.aax6239 · Background also from *Neuron* and *Artificial neuron*, Wikipedia.

[^2]: Minsky, M., & Papert, S. (1969). *Perceptrons: An Introduction to Computational Geometry.* MIT Press.

[^3]: Karpathy, A. (2022). *nanoGPT.* https://github.com/karpathy/nanoGPT

[^4]: O'Brien, P.C. (2026). *COLM: Complex Oscillating Language Model.* Zenodo. https://doi.org/10.5281/zenodo.20118034

[^5]: Draye, F., Lei, A., Posner, I., & Schölkopf, B. (2025). *Sparse Attention Post-Training for Mechanistic Interpretability.* arXiv:2512.05865. https://doi.org/10.48550/arXiv.2512.05865

---

> © 2026 P.C. O'Brien (Eden Eldith) — Licensed under CC BY-SA 4.0
