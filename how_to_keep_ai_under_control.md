# How to keep AI under control

Five years ago, I stood on the TED stage and warned about the dangers of superintelligence.

I was wrong.

It went even worse than I thought.

(Laughter)

I never thought governments would let AI companies get this far without any meaningful regulation.

And the progress of AI went even faster than I predicted.

Look, I showed this abstract landscape of tasks where the elevation represented how hard it was for AI to do each task at human level.

And the sea level represented what AI could be back then.

And boy or boy, has the sea been rising fast ever since.

But a lot of these tasks have already gone blub blub blub blub blub blub.

And the water is on track to submerge all land, matching human intelligence at all cognitive tasks.

This is a definition of artificial general intelligence, AGI, which is the stated goal of companies like OpenAI, Google DeepMind and Anthropic.

And these companies are also trying to build superintelligence, leaving human intelligence far behind.

And many think it'll only be a few years, maybe, from AGI to superintelligence.

So when are we going to get AGI?

Well, until recently, most AI researchers thought it was at least decades away.

And now Microsoft is saying, "Oh, it's almost here."

We're seeing sparks of AGI in ChatGPT-4, and the Metaculus betting site is showing the time left to AGI plummeting from 20 years away to three years away in the last 18 months.

And leading industry people are now predicting that we have maybe two or three years left until we get outsmarted.

So you better stop talking about AGI as a long-term risk, or someone might call you a dinosaur stuck in the past.

It's really remarkable how AI has progressed recently.

Not long ago, robots moved like this.

(Music)

Now they can dance.

(Music)

Just last year, Midjourney produced this image.

This year, the exact same prompt produces this.

Deepfakes are getting really convincing.

(Video) Deepfake Tom Cruise:

I’m going to show you some magic.

It's the real thing.

(Laughs)

I mean ...

It's all ...

the real ...

thing.

Max Tegmark: Or is it?

And Yoshua Bengio now argues that large language models have mastered language and knowledge to the point that they pass the Turing test.

I know some skeptics are saying, "Nah, they're just overhyped stochastic parrots that lack a model of the world," but they clearly have a representation of the world.

In fact, we recently found that Llama-2 even has a literal map of the world in it.

And AI also builds geometric representations of more abstract concepts like what it thinks is true and false.

So what's going to happen if we get AGI and superintelligence?

If you only remember one thing from my talk, let it be this.

AI godfather, Alan Turing predicted that the default outcome is the machines take control.

The machines take control.

I know this sounds like science fiction, but, you know, having AI as smart as GPT-4 also sounded like science fiction not long ago.

And if you think of AI, if you think of superintelligence in particular, as just another technology, like electricity, you're probably not very worried.

But you see, Turing thinks of superintelligence more like a new species.

Think of it, we are building creepy, super capable, amoral psychopaths that don't sleep and think much faster than us, can make copies of themselves and have nothing human about them at all.

So what could possibly go wrong? (Laughter)

And it's not just Turing.

OpenAI CEO Sam Altman, who gave us ChatGPT, recently warned that it could be "lights out for all of us."

Anthropic CEO, Dario Amodei, even put a number on this risk: 10-25 percent.

And it's not just them.

Human extinction from AI went mainstream in May when all the AGI CEOs and who's who of AI researchers came on and warned about it.

And last month, even the number one of the European Union warned about human extinction by AI.

So let me summarize everything I've said so far in just one slide of cat memes.

Three years ago, people were saying it's inevitable, superintelligence, it'll be fine, it's decades away.

Last year it was more like, It's inevitable, it'll be fine.

Now it's more like, It's inevitable.

(Laughter)

But let's take a deep breath and try to raise our spirits and cheer ourselves up, because the rest of my talk is going to be about the good news, that it's not inevitable, and we can absolutely do better, alright? (Applause)

So ...

The real problem is that we lack a convincing plan for AI safety.

People are working hard on evals looking for risky AI behavior, and that's good, but clearly not good enough.

They're basically training AI to not say bad things rather than not do bad things.

Moreover, evals and debugging are really just necessary, not sufficient, conditions for safety.

In other words, they can prove the presence of risk, not the absence of risk.

So let's up our game, alright?

Try to see how we can make provably safe AI that we can control.

Guardrails try to physically limit harm.

But if your adversary is superintelligence or a human using superintelligence against you, right, trying is just not enough.

You need to succeed.

Harm needs to be impossible.

So we need provably safe systems.

Provable, not in the weak sense of convincing some judge, but in the strong sense of there being something that's impossible according to the laws of physics.

Because no matter how smart an AI is, it can't violate the laws of physics and do what's provably impossible.

Steve Omohundro and I wrote a paper about this, and we're optimistic that this vision can really work.

So let me tell you a little bit about how.

There's a venerable field called formal verification, which proves stuff about code.

And I'm optimistic that AI will revolutionize automatic proving business and also revolutionize program synthesis, the ability to automatically write really good code.

So here is how our vision works.

You, the human, write a specification that your AI tool must obey, that it's impossible to log in to your laptop without the correct password, or that a DNA printer cannot synthesize dangerous viruses.

Then a very powerful AI creates both your AI tool and a proof that your tool meets your spec.

Machine learning is uniquely good at learning algorithms, but once the algorithm has been learned, you can re-implement it in a different computational architecture that's easier to verify.

Now you might worry, how on earth am I going to understand this powerful AI and the powerful AI tool it built and the proof, if they're all too complicated for any human to grasp?

Here is the really great news.

You don't have to understand any of that stuff, because it's much easier to verify a proof than to discover it.

So you only have to understand or trust your proof-checking code, which could be just a few hundred lines long.

And Steve and I envision that such proof checkers get built into all our compute hardware, so it just becomes impossible to run very unsafe code.

What if the AI, though, isn't able to write that AI tool for you?

Then there's another possibility.

You train an AI to first just learn to do what you want and then you use a different AI to extract out the learned algorithm and knowledge for you, like an AI neuroscientist.

This is in the spirit of the field of mechanistic interpretability, which is making really impressive rapid progress.

Provably safe systems are clearly not impossible.

Let's look at a simple example of where we first machine-learn an algorithm from data and then distill it out in the form of code that provably meets spec, OK?

Let’s do it with an algorithm that you probably learned in first grade, addition, where you loop over the digits from right to left, and sometimes you do a carry.

We'll do it in binary, as if you were counting on two fingers instead of ten.

And we first train a recurrent neural network, never mind the details, to nail the task.

So now you have this algorithm that you don't understand how it works in a black box defined by a bunch of tables of numbers that we, in nerd speak, call parameters.

Then we use an AI tool we built to automatically distill out from this the learned algorithm in the form of a Python program.

And then we use the formal verification tool known as Daphne to prove that this program correctly adds up any numbers, not just the numbers that were in your training data.

So in summary, provably safe AI, I'm convinced is possible, but it's going to take time and work.

And in the meantime, let's remember that all the AI benefits that most people are excited about actually don't require superintelligence.

We can have a long and amazing future with AI.

So let's not pause AI.

Let's just pause the reckless race to superintelligence.

Let's stop obsessively training ever-larger models that we don't understand.

Let's heed the warning from ancient Greece and not get hubris, like in the story of Icarus.

Because artificial intelligence is giving us incredible intellectual wings with which we can do things beyond our wildest dreams if we stop obsessively trying to fly to the sun.

Thank you.

(Applause)