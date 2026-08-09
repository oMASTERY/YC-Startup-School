---
title: "The 1% Rule for Building in AI"
speaker: "Jeff Dean"
duration: "57:07"
views: "98K views"
tags:
  - yc-startup-school-2026
  - transcript
---

# Jeff Dean: The 1% Rule for Building in AI
https://www.youtube.com/watch?v=CxXgV54KzpQ&list=PLEb7ftOB0yf0&index=6
## Summary
*(Add summary here)*

## Transcript
*(Add your transcript here)*


Chapters

Transcript
Chapter 1: Intro
Chapter 2: Are AI Models Already Junior Engineers?
0:077 secondsAll right. Should we go Should we get started, Jeff? Sure. Sounds great.
0:1111 secondsAll right. Jeff, welcome. And again, thank you so much for being here.
0:1414 secondsEspecially I just got a cold and thank you for being here.
0:1717 secondsYeah, I'm afraid I've lost my voice. I don't normally sound quite like this, but we'll we'll do what we can.
0:2424 secondsSo, um, you built map reduce, big table, tensorflow, the TPU, Gemini. We could spend a whole hour on all the things
0:3232 secondsyou've done, but what I love is that you're still making bold predictions in public. Last year, yes, last year in May
0:4242 seconds2025 at AI Ascent, you said that AI is at the level of a junior engineer.
0:5050 secondsThat was about a year ago. It's been How close are we to that prediction? Yeah, I
0:5858 secondsmean I feel like uh the models have been getting a lot better at sort of agent-based longer running coding tasks and it seems pretty clear that they are
1:061 minute, 6 secondsnow actually pretty capable and depending on exactly your definition of of junior engineer it seems pretty spot-on I would say.
1:151 minute, 15 secondsWhat did you underestimate from that prediction?
1:191 minute, 19 secondsUm I mean I think the the ability to do more and more complex tasks has been growing faster than I
1:281 minute, 28 secondsthought. Um and I also think uh outside of coding these these agent-based systems are are really starting to shine
1:361 minute, 36 secondsin other domains and I I think uh you know uh that's that's going to be an important trend in the future.
Chapter 3: AI Systems That Improve Themselves
1:441 minute, 44 secondsSo [snorts] give us another bold prediction. What do you think is going to be the 2027 edition?
1:511 minute, 51 secondsUh I think you will see a lot more automation of uh ML systems themselves.
1:581 minute, 58 secondsum basically getting ML systems to improve their capabilities by running lots of experiments, breaking things down into subpros, you know, running
2:072 minutes, 7 secondsthose subpros in a tight automatic experimentation loop, putting the results together and being able to then
2:142 minutes, 14 secondsuh you know, get some improved system uh out from that uh sort of fully automated problem decomposition and and automated
2:232 minutes, 23 secondsexperimentation that I think that's going to be really exciting. M I think that also applies not just to ML but also to other fields of science and
2:302 minutes, 30 secondsengineering. Um basically anything where you can have a measurable objective uh I I think you can uh actually make a lot of progress these days.
Chapter 4: The Google Search Breakthrough That Changed Everything
2:402 minutes, 40 secondsNow let's go back to a little bit in history. Back in way back in 2001 Google search used to run on hard drives.
2:492 minutes, 49 secondsYep. And you and Sanjay did the math and realized that at some point the whole search index would finally fit in all of
2:582 minutes, 58 secondsthe RAM of all the computers you had running and you made that radical realization
3:073 minutes, 7 secondsand you basically in few days with Sanjay shipped in production a whole new search version that worked in RAM rather
3:143 minutes, 14 secondsthan hard drive and that was the thing that got Google to be so fast. Google searches.
3:213 minutes, 21 secondsSo history tends to remix.
3:253 minutes, 25 secondsWhat is the it fits the memory moment right now in 2026 that everyone in this room is still should be thinking about and designing?
3:363 minutes, 36 secondsYeah. Yeah, I mean it's a little different, but I think uh you're going to see more and more
3:433 minutes, 43 secondsuh uh high performance and um low energy uh inference hardware systems because I
3:513 minutes, 51 secondsthink everyone is now realizing that inference is the key to making you know these agent-based systems be available
3:583 minutes, 58 secondsto more and more people and that latency is really important and that specialization of the hardware is a
4:054 minutes, 5 secondsreally key way you can make uh things that are more energy efficient and lower latency than more general purpose uh
4:124 minutes, 12 secondscomputational devices like say GPUs or TPUs because I think all everyone here is used to waiting for responses on on
4:214 minutes, 21 secondsmodels. [clears throat] So waiting is no fun master speed.
4:274 minutes, 27 secondsSo you're saying what if we don't have to wait anymore?
4:304 minutes, 30 secondsYeah. I mean, I think we'll imagine what you could do with something where the latency is, you know, 50x better.
Chapter 5: AI Agents Will Run for Weeks
4:384 minutes, 38 secondsInteresting thought.
4:404 minutes, 40 secondsNow, what's one assumption that perhaps 6,000 people in this room hold that's already false about AI?
4:504 minutes, 50 secondsYeah. Uh, that's that's a good question.
4:514 minutes, 51 secondsI mean I think um probably one thing is people don't quite realize how possible it is to have you
5:005 minutesknow agent-based systems that can run not just for an hour or two hours on a problem you care about but for some
5:085 minutes, 8 secondsproblem domains and with highly capable models underlying them you can get them to run for days or weeks and do really
5:155 minutes, 15 secondsreally complicated tasks and I think that's you know starting some people are starting to see inklings of this but I don't think everyone has really
5:235 minutes, 23 secondsinternalized this and that's going to be really uh a pretty big deal.
5:285 minutes, 28 secondsWhat's a particular task that you have run that has run for weeks? What what was it? What did the tell what did you tell the agents to solve? Yeah, I mean I
5:365 minutes, 36 secondsthink uh you can tell agents to uh go off and implement
5:435 minutes, 43 secondsum you know completely new versions of software in different programming languages that might be you know have better safety properties or better
5:515 minutes, 51 secondsperformance properties uh that and then then they can go off and and actually do that in a you know pretty serious way.
Chapter 6: The Napkin Math That Led to TPUs
5:585 minutes, 58 secondsThat's pretty cool.
6:006 minutes[clears throat] Now, one thing that you've been very well known for is you're really good at napkin math.
6:076 minutes, 7 secondsSounds funny. So, one of the stories about you is that back in uh 2013 when speech recognition started to work at
6:166 minutes, 16 secondsGoogle, you did the nap napkin math where if every Google user used their phone and talked to it and used the
6:246 minutes, 24 secondsspeech recognition system for three minute just three minutes a day, you found that the system requires a Google
6:326 minutes, 32 secondsserver. you would have to double the fleet which would be really really expensive just to do speech translation. Yeah.
6:406 minutes, 40 secondsAnd instead you basically built a custom ship and that was the origin story of the TPU.
6:486 minutes, 48 secondsYeah. Yeah. I mean I I sort of had done you know we were starting to see really good uh quality results on this the sort
6:576 minutes, 57 secondsof deep learning based speech systems uh speech models we were training. um but they were computationally expensive compared to the old speech system but
7:057 minutes, 5 secondsthey haved the error rate. So that was like the equivalent of 20 years of advances in speech recognition in just a few months of like fiddling with the
7:137 minutes, 13 secondsmodel and getting scaling it up a bit and getting better data. And so we started to get worried that if speech
7:207 minutes, 20 secondsworked a lot better, people would use it more. And so that that back of the envelope calculation was really about that like well what if people start
7:297 minutes, 29 secondsstart to use speech recognition more to dictate emails or to talk to their phone or whatever. Um and yeah it turned out
7:377 minutes, 37 secondsthat um we realized that we needed some better solution than running on CPUs at
7:447 minutes, 44 secondsthe time. And so we came up with TPUs which are sort of very specialized for essentially low precision dense linear
7:527 minutes, 52 secondsalgebra which is at the heart of nearly all of the modern machine learning algorithms we we use today. And um if
8:008 minutesyou build a specialized chip for low precision dense linear algebra and can't do anything else that turns out to be really useful for machine learning
8:078 minutes, 7 secondsinference uh even though it can't run Chrome or Word or whatever. Uh, and so that system produced a chip a couple
8:148 minutes, 14 secondsyears later that was uh 30 to 80 times more energy efficient than CPUs and GPUs
8:228 minutes, 22 secondsof the day and also much much lower latency like 20 to 30x lower latency which is incredible what the foundation
8:308 minutes, 30 secondsthat TPU has become today. No way you would have predicted that TPU would be so foundational now with transformer architecture which was invented way
8:388 minutes, 38 secondslater before you actually invented the TPU. Yeah, I mean that's sort of why we built a general purpose linear algebra system, which is what a TPU is really.
8:488 minutes, 48 secondsUm, because we knew ML algorithms were still evolving and you didn't want to over specialize, but you wanted to specialize enough that you got the
8:578 minutes, 57 secondsdramatic performance benefits of we could have very big multiplier units. uh we could have you know high-speed memory we could have high-speed interconnect or
9:069 minutes, 6 secondslater TPUs that like brought many many chips to bear on the same problem efficiently and u you know we've
9:149 minutes, 14 secondscontinued to scale those up and and improve their performance uh for over many many generations now incredible napkin math so
Chapter 7: How to Find Breakthrough Ideas
9:229 minutes, 22 secondswhat's good napkins are good so actually what's a good napkin math that everyone here who wants to be a
9:319 minutes, 31 secondsfuture founder should run tonight to potentially build something as consequential as the TPU.
9:399 minutes, 39 secondsYeah, I mean, uh, it's always hard to say. Um, [clears throat] I think, uh,
9:469 minutes, 46 secondsthink about what problems you see in whatever it is you're thinking about, what what bottlenecks you see, and are
9:549 minutes, 54 secondsthere very different ways of thinking of the solutions to some of those problems that would get you, you know, an order of magnitude or two orders of magnitude
10:0210 minutes, 2 secondsbetter uh, performance or capability or whatever it is. Um, you know, because sometimes if you just squint at a
10:1010 minutes, 10 secondsproblem and you think about not necessarily being anchored on exactly how that problem is solved today, but how you would solve it from first
10:1810 minutes, 18 secondsprinciples, you can come up with really good ideas that are, you know, maybe not what other people are thinking about.
Chapter 8: The AI Engineer’s New Mental Model
10:2510 minutes, 25 secondsThat's a good tip. [clears throat] No. Um, for everyone here who doesn't know, years ago, Jeff wrote a very famous list called the latency numbers.
10:3610 minutes, 36 secondsevery engineer should know and these are numbers around for example how long a cache miss takes uh disk seek
10:4610 minutes, 46 secondsa network package traveling let's say from California to Netherlands um lots of numbers like this about
10:5310 minutes, 53 secondsdistributed systems and systems engineering [clears throat] and it's been sort of taped and become the bible for a lot of distributed systems engineers okay yeah
11:0111 minutes, 1 secondnow fast forward that list is up for an update give us the AI edition for now 2026.
11:0911 minutes, 9 secondsYeah, I mean I think if you looked at what is important in AI systems these days, you would want to know things like
11:1711 minutes, 17 secondsthe bandwidth between you know your main memory system on your accelerator to the
11:2311 minutes, 23 secondsonchip memory to the um you know the multiplier unit or whatever. You want to know how much energy does it take to do a single multiplier operation.
11:3411 minutes, 34 secondsum you know uh what is the interconnect bandwidth between chips and how much does that uh how how many chips can you
11:4211 minutes, 42 secondsconnect with that bandwidth and then if you go beyond that domain like what is the fall off in in uh network bandwidth
11:5011 minutes, 50 secondswhen you need to talk to 10,000 strips instead of instead of uh 500 or something I think these are all really
11:5711 minutes, 57 secondsimportant numbers to to learn and and really affect how you think about solving particular kinds the problems.
12:0412 minutes, 4 secondsH [clears throat] and one interesting thing that I've heard you talk about is that nowadays the unit that you measure everything is energy.
12:1512 minutes, 15 secondsYeah.
12:1512 minutes, 15 secondsYou pointed out that doing a calculation or math costs about one pico.
12:2112 minutes, 21 secondsUh but moving the data and doing data IO costs thousand times that.
12:2612 minutes, 26 secondsYeah. Just bringing it in from HPM on an accelerator into the processor so it can actually compute on it. Yep.
Chapter 9: Why AI Is Really an Energy Problem
12:3312 minutes, 33 secondsThat gap kind of quietly decides what products are possible and how these algorithms in AI are built. So what are
12:4212 minutes, 42 secondsthe kinds of problems that founders keep calling model problems but are in fact actually energy or data IO problems?
12:5112 minutes, 51 secondsYeah, I mean I think the the example you raised of a thousandx difference in bringing mo moving data versus actually
12:5912 minutes, 59 secondscomputing on it uh in in terms of energy is is a pretty significant one and it shapes a lot of aspects of what we do in
13:0613 minutes, 6 secondsmachine learning. Um because if you didn't have that thousandx difference then you know you wouldn't have to do
13:1413 minutes, 14 secondsbatching but you have to do batching of you know many examples or maybe many tokens at once in order to amortize that
13:2113 minutes, 21 secondsdata movement [clears throat] so that you can uh you know not pay a thousandx slowdown but pay a 1000x divided by
13:2813 minutes, 28 secondsbatch size uh energy cost. Um and you know for for really low latency batching
13:3613 minutes, 36 secondsis not really very good. Um so I think these [clears throat] kinds of things and the energy uh behind various decisions in the computer hardware we
13:4513 minutes, 45 secondsuse really affects a lot of decisions we make in building higher level systems.
13:5113 minutes, 51 secondsA very concrete example is just how training models is done. There's this whole whole concept of batching the the
13:5913 minutes, 59 secondsdata sets and running epochs. That's basically people perhaps may confuse that as a model problem, but it's really a systems data IO problem, right?
14:0814 minutes, 8 secondsYeah. Yeah. I mean, you have to assemble batches to get better efficiency in your hardware. You know, ideally you might do
14:1514 minutes, 15 secondsbatch size one training, but uh you know, it's um not as not as good in terms of efficiency. So people use re pretty large batches these days.
14:2614 minutes, 26 secondsDo you think uh it's possible for uh I know you're you're well known for uh taking off uh on a long week or weekend and coming up with this brilliant
14:3414 minutes, 34 secondssolution. Is there such things of Jeff going and working on it for a couple weeks and [clears throat] getting batch size equals one training done.
14:4314 minutes, 43 secondsYeah, I've been thinking more about inference actually. So I think inference is a pretty interesting problem because you do want very low latency. You know
14:5214 minutes, 52 secondstraining you don't necessarily need incredibly low latency. Um and I think there's a lot of room for specializing hardware more for inference than we are today.
15:0215 minutes, 2 secondsWhat are some of those interesting things that are on inference that you're really thinking a lot about?
15:0715 minutes, 7 secondsUm I mean just trying to minimize data movement. uh trying to think about incredibly
15:1415 minutes, 14 secondsuh low precision operations uh and maybe not supporting lots and lots of different kinds of precisions.
15:2115 minutes, 21 secondsUh if you feel like you have a a good answer for what kinds of precision you need, maybe just build that into the hardware and and um not much else.
15:3315 minutes, 33 secondswhich I think it brings down to a core [clears throat] analogy I heard from famous computer scientists that really
15:4015 minutes, 40 secondsthe whole process of u AI is a big compression problem because in order to
15:4815 minutes, 48 secondshave the data to be f fully lossy and compress it and then restore it you basically need to understand it. Yeah, I mean if you truly understand the data,
15:5715 minutes, 57 secondsyou should be able to compress it really well and now transformer architecture is basically one of the ways that has turned out to work really well.
16:0716 minutes, 7 secondsYeah. Yeah, I would say working pretty well so far.
16:0916 minutes, 9 secondsGood work by my colleagues. [laughter] Yes. Now let's zoom out a bit. Um AI progress used to mean just better
Chapter 10: Context Engineering Is the Next Frontier
16:1816 minutes, 18 secondsmodels. You could had more data trainer models with bigger parameters. But increasingly in the last years or so,
16:2616 minutes, 26 secondsit's everything around the model. Not just the model size and number of parameters or more data. It's everything around things like retrieval tools,
16:3416 minutes, 34 secondsmemory, agent tools, and it might kind of get consolidated into what people call uh context engineering, right?
16:4216 minutes, 42 seconds[clears throat]
16:4216 minutes, 42 secondsYeah. I mean I think uh the model is really only one piece of what you're trying to do which is build an overall
16:4916 minutes, 49 secondssystem that can solve really interesting problems and that involves you know a model that knows how to use various
16:5716 minutes, 57 secondstools. It maybe knows how to retrieve relevant information, maybe has a, you know, a history of other uh information
17:0517 minutes, 5 secondsthat it has retrieved for past problems and it can put information into the context of the of the model. And the
17:1417 minutes, 14 secondsnice thing about that is that information is really clear to the model, unlike the training data the model was trained on where it's all kind
17:2117 minutes, 21 secondsof like trillions of tokens stirred together into a soup of of hundreds of billions or trillions of parameters, but
17:2817 minutes, 28 secondsit's all less clear than the actual context uh that the model sees directly for this particular problem or uses use
17:3617 minutes, 36 secondscase. And then I think being able to understand what tools are available, which ones are going to help me solve
17:4417 minutes, 44 secondsthe help the model solve this next you know phase of the problem, how to decompose a problem into a sequence of of tool calls. Maybe trying multiple
17:5217 minutes, 52 secondsapproaches to solve the problem and seeing which ones work and being able to evaluate that. you know this is the whole um you know orchestration of
18:0218 minutes, 2 secondscomplex agent and multi-agent systems that I think is going to be more and more important and uh super exciting times I would say
18:1018 minutes, 10 secondsand I think the fun thing about this particular problem domain set is actually something that everyone in this room can actually do because before to
18:1818 minutes, 18 secondstrain a model you needed incredible amount of resources incredible amount of access of to GPUs and data but for context engineering everyone here could
18:2718 minutes, 27 secondsdo you have you just need the API to something like Gemini and then work on your own setup for your own retrieval
18:3418 minutes, 34 secondsyour own tool calls and etc etc. So how does what are some tips for everyone here? How does everyone get better at
18:4218 minutes, 42 secondsand become exceptional at context engineering? Yeah, I mean I think uh
18:4918 minutes, 49 seconds[clears throat]
18:5018 minutes, 50 secondsa really good way to do it is to use these models and and sort of harnesses and tools and so on to try to solve
18:5718 minutes, 57 secondsproblems and then some sometimes you can actually see where the models are failing. And often you can actually make
19:0419 minutes, 4 secondsthe model work better and succeed at that kind of problem by not just adjusting the model parameters which is
19:1119 minutes, 11 secondshard to do from the outside but from you know creating better guidelines for the model you know writing skills for the
19:1919 minutes, 19 secondsmodel to know how to use different tools that would be incredibly useful for solving this particular class of problem. And I think as you do that, you
19:2819 minutes, 28 secondsend up on this kind of improving self-improving of the setup that you're trying to use to to solve things. Uh,
19:3619 minutes, 36 secondsand you know that that's a really good way to get better at understanding what what additional information the model would want in order to become more capable.
Chapter 11: The Skill That Made AI Better at Optimization
19:4619 minutes, 46 secondsCan you give an example of uh some context engineering you personally have done? um I don't know skills you wrote tools that really made a huge different
19:5419 minutes, 54 secondsin your in your workflow. Yeah, I mean I guess uh Sanjay and I were working a few weeks ago and we you know we often do
20:0320 minutes, 3 secondssome amount of like uh performance improvement for very low-level libraries and we have a microbenchmark library
20:1020 minutes, 10 secondswe've written at Google where you can write microbenchmarks of how how long different kinds of operations take or how long does it take to populate this
20:1820 minutes, 18 secondsdata structure whatever and sometimes those data structures are used on millions of processes across Google. So, it's actually pretty important to make
20:2620 minutes, 26 secondssure they're high performance. And so, you can write microbenchmarks. Um, but then without an agent-based system, what
20:3320 minutes, 33 secondsyou usually do is you measure what the current performance is on some benchmarks you care about. You make some modifications to improve the performance
20:4220 minutes, 42 secondsyou hope. Then you rerun the the benchmarks, see where things improved.
20:4820 minutes, 48 secondsUm, you run a maybe a broader set of benchmarks, measure the cache footprint of things. And so we wrote a skill that
20:5620 minutes, 56 secondsbasically taught the model how to do most of those things in in var in various sequences so that it could actually you know do self-improving uh
21:0421 minutes, 4 secondsbenchmark measurement benchmark improve you know code changes measure the performance improvement and then iterate on that and that that seemed to work uh pretty well for some kinds of problems.
21:1421 minutes, 14 secondsAnd it really just is us giving the approach we would use as people to the model in a form that it could use.
21:2321 minutes, 23 secondsWow, that seems very impressive. So you're saying you have this skill that if someone got access to it, it could do perform optimizations like Jeff Dean.

Jeff Dean
Jeffrey Adgate Dean is an American software engineer. He is best known for his work at Google, which he joined in 1999. He led Google AI from 2018 to 2023 and was Google's chief scientist from 2023 to 2026. Dean co-founded the AI research start-up Discovery Loop in 2026.
...more
21:3321 minutes, 33 secondsSeems like the world would love this and is worth infinite amount of money to someone have access to this.
21:3921 minutes, 39 secondsOh. Uh we actually published a document maybe a few months ago called performance hints that Sanjay and I wrote that's like a 30-page document
21:4721 minutes, 47 secondsabout you know various kinds of performance tricks and some people have taken that and then given it in summarized form to various models and
21:5521 minutes, 55 secondsseen that they that model can now get you know better at uh per reasoning about performance issues in code.
22:0122 minutes, 1 secondSo you heard it all here. You could actually get your own optimize your own code like Jeff Dean if you take this this paper that you published when performance hints. Yep.
22:1022 minutes, 10 secondsIt's all free available, so you should all try it. Very cool. Yeah.
Chapter 12: Why Long-Running Agents Fail
22:1422 minutes, 14 secondsNow, you're talking about agents. Um, everyone here is probably building one or built one at some point. And I'm sure everyone has seen your agent go off the
22:2322 minutes, 23 secondsrail at perhaps like step 30 or 40. Like agents are great for like up to step, I don't know, 10 or something and then
22:2922 minutes, 29 secondsgets shaky at step 50. What do you think is the constraint today? Is it like context evaluators or just errors that compound
22:3822 minutes, 38 secondsbecause it's basically a openloop system?
22:4122 minutes, 41 secondsYeah, I mean obviously we want agents to be able to run for very long periods of time because that's how they're going to solve more and more complicated
22:4922 minutes, 49 secondsproblems. Um but as you as you observe today, you know, they sometimes stop
22:5522 minutes, 55 secondsworking after, you know, 10 10 interactions with the tools and so on.
23:0123 minutes, 1 secondUm, and sometimes that's because the model is trying to do something it doesn't have a lot of experience doing.
23:0723 minutes, 7 secondsSo it's been trained on a whole set of things and as soon as you get a little bit off the distribution of things it knows how to do then like most machine
23:1523 minutes, 15 secondslearning models it will you know its performance will suddenly will start to degrade and the farther you get off the
23:2223 minutes, 22 secondscomfort zone of what it knows how to do the the more likely it is to to not work as well. Um so there's a bunch of things
23:3023 minutes, 30 secondsyou can do. So one is you know give the model skills and hints that kind of tend to keep it in in the uh sort of more
23:3823 minutes, 38 secondsbrightly lit path of things it does know how to do. Um, I think you know having multi- aent systems where you have multiple agents trying different
23:4723 minutes, 47 secondsapproaches and you can evaluate you have maybe another model or another agent that's evaluating which ones of those
23:5323 minutes, 53 secondsseem promising is another way to kind of in some sense search the path of pos
24:0124 minutes, 1 secondsearch the space of possible solutions and stick to the ones that seem most promising and discard the ones that that
24:0824 minutes, 8 secondsdidn't seem to work or maybe that went off the rails. or whatever. Um, and that's a very very useful general technique is you know inference time
24:1824 minutes, 18 secondscompute to perform search over plausible ways of solving the problem that can get much much higher performance or much
24:2524 minutes, 25 secondsmore reliability in longunning agent flows.
24:3024 minutes, 30 secondsHow are some ways you implemented this particular workflow for your agents internally?
24:3524 minutes, 35 secondsYeah, I mean we have uh you know harnesses and then we have a whole set of skills uh particularly in the internal Google development environment.
24:4324 minutes, 43 secondsWe have skills so that the agents can know how to use lots of our internal tooling for coding or for code reviews
24:5024 minutes, 50 secondsor for you know measuring performance or you know fetching log files. And um those are just skills that you can add
24:5924 minutes, 59 secondsto make the base model more capable even though it hasn't necessarily been trained on exactly the way that you know
25:0625 minutes, 6 secondsGoogle internal uh engineers would fetch log files from our you know proprietary system with the right kind of skill uh
25:1525 minutes, 15 secondsdefinition you can actually get it to work uh and that that improves the usefulness of the agents. Now let's talk about uh
Chapter 13: Where Startups Can Still Beat Google
25:2325 minutes, 23 secondswhere startups can can win. This section is one that I personally care a lot about because also everyone here in this
25:3125 minutes, 31 secondsroom needs to decide what to build in the future of your future founder. So the thing about Google is you co-design
25:3925 minutes, 39 secondseverything on the system from the processors to the products.
25:4425 minutes, 44 secondsum which are the layers that someone like Google would keep building and compounding being better and and where
25:5225 minutes, 52 secondsdoes a two three person team can still win?
25:5725 minutes, 57 secondsYeah, I mean I think obviously Google and and our Gemini models and and our hardware infrastructure are really
26:0426 minutes, 4 secondstrying to build very general models that can do almost anything. But in in a lot
26:1126 minutes, 11 secondsof cases that means that we don't have a lot of attention on particular domains where perhaps a really well-designed
26:1926 minutes, 19 secondssurface that and maybe a model and set of skills or maybe a specialized model that uh isn't in sort of a general mix
26:2826 minutes, 28 secondsof of things that our models do well can actually have a significant advantage because you can build something delightful and you know really high
26:3726 minutes, 37 secondsaccuracy. really high quality for a domain that you are really passionate about. And I think that's that's where
26:4426 minutes, 44 secondsyou know the two or three people in a room uh building that that they're really excited about can have an
26:5026 minutes, 50 secondsadvantage. Um but I I would also caution that the general models are definitely getting better at a broader and broader
26:5926 minutes, 59 secondsrange of things. So you have to figure out, you know, is that thing you're working on, is that going to be a durable thing or do you think the models
27:0727 minutes, 7 secondsuh at the forefront are going to get better at that in the next six months or 12 months or is it something they're not going to be able to do for a couple
27:1527 minutes, 15 secondsyears or three years? And you know, you you want to weigh that as you're as you're deciding what to work on.
27:2227 minutes, 22 secondsSo let's uh dive deeper into this. So the general models of course you're going to keep working on and keep making them all better.
27:2927 minutes, 29 secondsAnd how should the audience reason about what are those areas that uh it doesn't I mean h how should founder think about things to pick on and work on.
27:4027 minutes, 40 secondsYeah. I mean I mean the most important thing is to pick something you're super excited about and want to build and you think would be useful in the world,
27:4827 minutes, 48 secondsright? So if you do that um that that's you're already way ahead uh than if you wake up and you're like oh I don't
27:5527 minutes, 55 secondsreally want to do this or whatever or you're going to build something that is actually not that useful to to the world
28:0128 minutes, 1 secondor to to many people. Um so I think that's the number one selection criteria I try to apply for what problem should I
28:1028 minutes, 10 secondswork on next. Um, second, I think you want to look at what the current more
28:1628 minutes, 16 secondsgeneral models can do in that problem domain, right? You can you can test them with like, are they able to do this
28:2328 minutes, 23 secondsthing very well? And if they're completely failing, that's probably a good sign. If they're kind of able to do
28:3028 minutes, 30 secondssome of it but not very well, that's maybe not a great sign because that's a probably a a sign that the capability is
28:3828 minutes, 38 secondsstarting to be present in those models and with more training data or larger scale models or or whatever it's likely
28:4528 minutes, 45 secondsto get better. So um you know look for something where the model succeeds 0% or 1% of the time not not 20%.
28:5428 minutes, 54 secondsHow do you find those? I mean are those things effectively uh out of distribution from the training set and what exactly is the problem shape that fits that?
29:0429 minutes, 4 secondsYeah, I mean I think uh sometimes it's uh a product that you build that might have access to particular kind of data
29:1329 minutes, 13 secondsthat the underlying model might not the a general model. So it might be you're building something to help users organize all their own personal
29:2129 minutes, 21 secondsinformation and the model won't necessarily have access to that. And so there you can have a big advantage because all of a sudden your model has
29:2829 minutes, 28 secondsvisibility or your product has visibility into important data. Um it could be some incredibly hard problem
29:3829 minutes, 38 secondswhere if you get the right training data and you can train a more specific model than a general purpose one, you can actually do that in a very affordable
29:4629 minutes, 46 secondsway. you maybe it doesn't take that much compute to train a a niche model for this particular problem, but you can get something that's highly accurate. That
29:5429 minutes, 54 secondscan sometimes be a a really good uh building block for for solving a important problem that is maybe not handled very well by the general model.
30:0430 minutes, 4 secondsI think that's interesting. I think there are basically two paths. The first path is uh a little bit funny is uh you guys are organizing the world's information.
30:1230 minutes, 12 secondsYeah, that's probably kind of well covered.
30:1530 minutes, 15 secondsYeah. but organizing your personal information that's open which is funny. Yeah.
30:2130 minutes, 21 secondsAnd then the second path um you talked about more specialized models in certain domains. Can you tell us more about what are some of these domains?
30:3030 minutes, 30 secondsYeah. I mean I think like if you look at uh my colleagues work on say alpha fold that was a very specific model for uh
30:3830 minutes, 38 secondsprotein folding and it was highly successful um and was able to really handle that domain quite well so that all of a
30:4630 minutes, 46 secondssudden you now have this amazing tool and model that can give you answers to questions about proteins and their
30:5230 minutes, 52 secondsstructure um really effectively um but it's not a general model it's a very specific one and there are other I
31:0131 minutes, 1 seconddomains where that kind of approach can work really well. Uh maybe in material science or chip design or things like
31:0731 minutes, 7 secondsthat that uh will enable you to leverage the capabilities of a very accurate but
31:1431 minutes, 14 secondsbut niche model uh to do things that are hard today.
Chapter 14: How to Become an AI-Native Founder
31:1931 minutes, 19 secondsThat's a good example. So if some of you find a problem that's similar shape like alpha fold could be a good problem to work on. Now let's assume you found a
31:2631 minutes, 26 secondsproblem to work on. We're going to talk a bit about how do you become a AI native founder? How do you really become good at it? Uh you in the past said that
31:3531 minutes, 35 secondsmanaging a fleet of agents, it's like 50 or 100 agents is all about writing really good crisp design docs or specs.
31:4531 minutes, 45 secondsAnd how do people get good at that? What what do those look like? Yeah, I mean I think uh
31:5431 minutes, 54 secondsit's you you'll have a lot more success when working with your virtual agents if you can clearly specify what it is you want.
32:0332 minutes, 3 secondsAnd the clearer you are on what it is you want, the more the agent will have sort of guidelines and sort of rules of,
32:1032 minutes, 10 secondsyou know, an outline of what it is trying to accomplish. Um whereas if you don't specify very much stuff, the agent
32:1732 minutes, 17 secondshas to sort of infer what it is you meant. And in many cases, it might infer things that are different than what you imagined. So we've always told computer
32:2632 minutes, 26 secondsscientists from the very beginning that really it's really important to specify what it is, what's the software that you're writing is trying to accomplish
32:3432 minutes, 34 secondsbefore then going and writing it. And so now we actually have agent-based systems that can do the writing, but the importance of specifying what what it is
32:4232 minutes, 42 secondsyou want has actually gone up because before you'd be handing it off to a very intelligent human who maybe has context
32:5032 minutes, 50 secondsor can ask you follow-up questions. Um, and agents can sometimes do that, but I I think clear specifications is is a
32:5832 minutes, 58 secondsreally good idea. Um, and to give you an example of a a a use of a coding agent that works extremely well is you can ask
33:0733 minutes, 7 secondstoday's models to translate software from one computer language to another very effectively because in that case
33:1533 minutes, 15 secondsyou actually have a incredibly detailed specification. You have the whole software that says what the system is supposed to do. And so if you have a
33:2333 minutes, 23 secondsPython implementation of something and you want a Go implementation of it, you know, that is something that the models seem incredibly capable at doing these
33:3133 minutes, 31 secondsdays because you can it can sort of take all the tests that are in Python, make sure they pass in the Go version,
33:3833 minutes, 38 secondstranslate the tests to Go, um you know, compare uh behavioral differences between the implementations until there
33:4533 minutes, 45 secondsaren't any um and be you know, highly effective because that spec is so clear.
33:5133 minutes, 51 secondsHm. Now let's assume now every founder gets good at running hundreds of agents at the same time and all the code is written for them by the agents. What becomes the scarce skill?
34:0334 minutes, 3 secondsYeah, I mean I think it's really having incredibly good taste in what you ask your agents to work on, right? That is
34:1134 minutes, 11 secondsthe the crux of you know from my background uh a research problem. You know, a researcher can have all the
34:1934 minutes, 19 secondstools and all the techniques, but often most of the battle is what problem are you gonna spend your time on? And if you
34:2734 minutes, 27 secondspick the problem well and you succeed in in in solving it, that's way better than if you, you know, uh, delightfully
34:3634 minutes, 36 secondsexecute a research investigation into a rather boring problem. And so that high level wisdom of what to work on, I think
34:4434 minutes, 44 secondsis incredibly important. And I think models are not necessarily going to be that good at it. So you're going to have people steering
34:5434 minutes, 54 secondsuh a lot of AI assisted computation in order to accomplish great things and more quickly. Um but that essence of of
35:0235 minutes, 2 secondswhat it is you want your models to do is the the the key thing you should focus on.
35:0835 minutes, 8 secondsSo let's talk a bit more about taste because it gets talked a lot about right now in this current era with agent coding. How do you exactly build taste
35:1735 minutes, 17 secondsand do that? I mean, yeah, that sounds so esoteric. How do you make it concrete? Yeah, I mean it it is a difficult thing.
35:2635 minutes, 26 secondsIt's not like there's a measurable objective of of taste in a lot of cases.
35:3135 minutes, 31 secondsUm, I think some of it is from experience. You know, working on a lot of different problems in the past kind of teaches you about what kinds of
35:4035 minutes, 40 secondsproblems might be interesting in the future or what kinds of things might be just barely possible by cobbling
35:4835 minutes, 48 secondstogether these previous approaches and then some open problems you might have to work on in order to get to something kind of magical or or you know, highly
35:5735 minutes, 57 secondsuseful. Um, another way you can get more experience for yourself is to just write down a
36:0636 minutes, 6 secondsbunch of things you think might be important in the next 12 months. And maybe you pick one of them to work on,
36:1236 minutes, 12 secondsbut go back and evaluate in 12 months of these other things, which ones actually seemed important or which ones did other
36:2036 minutes, 20 secondspeople in the world go out and and create and which ones did they did not seem to do yet. um that can give you a lot more samples for your own sort of
36:2936 minutes, 29 secondstaste creation uh capability. Um and and that's an important skill to have.
36:3536 minutes, 35 secondsI think a third way we were talking earlier was doing very crazy thought experiments.
Chapter 15: Question Your Biggest Assumptions
36:4236 minutes, 42 secondsOh yeah, that's another good way. I mean I think uh sometimes it's good to
36:4936 minutes, 49 secondsnot take as a given things that most people seem to take as a as a given. Um so I was doing a crazy thought
36:5636 minutes, 56 secondsexperiment with some colleagues the other day about you know for 60 years the whole silicon
37:0637 minutes, 6 secondsuh chip design industry uh design and fabrication industry have you know done tremendous work to make
37:1537 minutes, 15 secondssmaller and smaller scale transistors that are uh very low error rate right like because what what the assumption
37:2437 minutes, 24 secondsthat we want is that every chip we manufacture of the same design should be identical to every other chip. You don't want any bits to flip.
37:3137 minutes, 31 secondsEverything no bits should flip. There's all kinds of things you there's all kinds of error margins built into you know memories
37:3837 minutes, 38 secondshave ECC memory these days. um you know at the at the macro scale we don't make that assumption when we're building
37:4637 minutes, 46 secondslarge scale distributed systems right we we build reliable large scale distributed file systems out of
37:5337 minutes, 53 secondsunreliable parts right like individual discs can fail but your data should be safe and so we have mechanisms at a
38:0038 minuteshigher level to enable us to have um you know three copies of the data on three different machines and three different
38:0738 minutes, 7 secondsracks so that if any rack switch or individual ual machine or disk fails, you still have your data. We have read Solomon encoding techniques. Um, but we
38:1738 minutes, 17 secondsdon't seem to do this at a really extreme level in the uh sort of transistor level scale of of the
38:2638 minutes, 26 secondstechnology we're working on. So what would h basically a interesting thought experiment is what would happen if you tried to build a system out of
38:3438 minutes, 34 secondstransistors that might have you know 20 errors per day.
38:3838 minutes, 38 secondsOh my god. rather than one every million years, right? That would be a very different design point and might be might enable you to do really
38:4638 minutes, 46 secondsinteresting things in the fabrication side of things. You have very different kind of design methodologies because if you want to get a signal from here to
38:5438 minutes, 54 secondsthere, you and you have these super unreliable transistors. You might have very different ways of signaling. You might send it along multiple redundant
39:0239 minutes, 2 secondspaths uh in order to make sure that it gets along one of them. Um, and I think that would be a pretty interesting set of thought experiments. I'm not saying
39:1039 minutes, 10 secondswe should go do this, but you know, that's the kind of thing where you do want to, you know, occasionally question
39:1739 minutes, 17 secondsassumptions. Now, oftentimes these thought experiments don't work out because there are very good reasons that, you know, for the last 50 years,
39:2639 minutes, 26 secondswe've done this thing this way and not that way. But it it's good to kind of revisit those every so often.
39:3239 minutes, 32 secondsThat is so wild. Well, I mean, it's starting to rhyme a lot with neuromorphic computing or the human brain and and how nature works.
39:3939 minutes, 39 secondsI mean, exactly like signals in our brain are not especially reliable from getting one place to another. And so, I think in brains when there are really
39:4839 minutes, 48 secondsimportant things you need to get from one place to another, there are multiple pathways that that enable you to sort of do that.
39:5639 minutes, 56 secondsWhat is uh in I mean, you have such an impressive career. What is one of these crazy assumptions that you threw out of the window that actually built a consequential system in the past?
40:0940 minutes, 9 secondsYeah, I mean I guess uh that worked out actually.
40:1340 minutes, 13 secondsYeah, I mean I think uh well TPUs is a good example like being able to specialize hardware for a very niche
40:2040 minutes, 20 secondsproblem domain before that problem domain seemed as important as it is today uh is one thought experiment. Um
40:2840 minutes, 28 secondsyou know I think the the origin of map produce is another good example.
40:3440 minutes, 34 secondsSo we had worked the you know my Sanjay and myself and a number of other colleagues had worked on various iterations of the crawling and indexing
40:4340 minutes, 43 secondssystem at Google and you know we'd sort of written lots of hand parallelized code with lots of checkpointing to make
40:5140 minutes, 51 secondssure it would be robust and reliable if it was running on a 100 computers or a thousand computers and some of those
40:5740 minutes, 57 secondsdied. Um, but that code tended to be intermixed with the actually relatively
41:0441 minutes, 4 secondssimple thing you often were trying to do like I just want to like look at all the contents of all the web pages and then
41:1141 minutes, 11 secondscompute on the side a mapping from URL to you know what language is this page in the text of this page. Um, and it
41:2041 minutes, 20 secondswould get obscured by all this kind of other code for parallelization and reliability. And so we sort of remembered our training in functional
41:2941 minutes, 29 secondslanguages and realized we could squint at those problems and developed this map produce abstraction that you could have
41:3641 minutes, 36 secondsabove this implementation and then below the implementation you could put all the checkpointing and reliability mechanisms
41:4541 minutes, 45 secondsinto that lower level library that everything could then build on. And so that became a hugely successful way of of dealing with very large scale
41:5341 minutes, 53 secondscomputations at Google in a robust and reliable way. From that thought experiment of like well if we squint at it could we find lots of problems that fit into this abstraction.
42:0342 minutes, 3 secondsThat's impressive. So this thought experiment led you to create map reduce. Yeah. Awesome.
Chapter 16: AI That Builds Better AI
42:0942 minutes, 9 secondsNow let's go back to you talked a bit about um about your interest right now working on a lot of customized hardware.
42:1742 minutes, 17 secondsSo right now alpha chip lays out chips. Now you also got alpha evolve that proposes solutions, evaluates them and keeps all the ones
42:2642 minutes, 26 secondsthat work. Seems like you're starting to build all these system that can compound and build AI that builds AI.
42:3242 minutes, 32 secondsYeah. I mean I think more generally there's a there's this sort of the foundation of the scientific method
42:4142 minutes, 41 secondsof you propose an experiment you implement what you need to run the experiment and you evaluate the experiment and then you get results from
42:5042 minutes, 50 secondsthat and I think there are more and more problems that are now possible to implement where that whole loop of
42:5842 minutes, 58 secondsrunning you know not just a few experiments but running many many experiments because you're able to automate that loop and make the latency
43:0543 minutes, 5 secondsof that loop extremely low is going to be really really important. It's going to enable us to tackle you know lots of different problem domains in science and
43:1443 minutes, 14 secondsengineering and machine learning uh model design itself and also in engineering tasks like designing chips.
43:2343 minutes, 23 secondsAnd so if you can actually do those things in an automated way and have some orchestration framework that can take
43:3143 minutes, 31 secondsvery high level objectives and break them down into subpros and each of those subpros can be one of these automated
43:3843 minutes, 38 secondsloop that is exploring the best way to solve that sub problem and then a orchestration framework that can put
43:4643 minutes, 46 secondstogether subpros solutions into a you know the overall solution for the higher level problem that's going to be really
43:5443 minutes, 54 secondsimpactful and it's really really important and I think it'll enable us to do you know accelerate machine learning progress it'll enable us to accelerate
44:0344 minutes, 3 secondsscience and enable us to accelerate engineering and I think that's that's going to be amazing that sounds awesome I mean it sounds like a lot of fields basically where you
44:1244 minutes, 12 secondscan have very good evaluators and maybe adjacent to basically things that can be formally verified right those are ripe
44:2044 minutes, 20 secondsfor AI systems that can self-improve Yeah, I think in a lot of cases sometimes your evaluators need to be made much faster. Mhm.
44:2844 minutes, 28 secondsSo as an example, my colleagues did some work maybe a decade ago on um some uh
44:3644 minutes, 36 secondsproblems in quantum chemistry where you're trying to understand the properties of a particular molecule and you can you know generate some molecule
44:4444 minutes, 44 secondsconfiguration and then you want to understand what properties it has. And so you can run a very computationally intensive density functional theory
44:5244 minutes, 52 secondssimulator which is something that might take like a a night of computation to tell you the answer for one thing. Um
45:0045 minutesbut what my colleagues did was take a bunch of output from those simulation runs the input molecule
45:0945 minutes, 9 secondsconfigurations and the outputs of the the expensive simulator and then use it to train a neural approximation to the
45:1645 minutes, 16 secondssimulator. So this is now a validation device, but instead of it taking a night, they made something that was 300,000 times faster.
45:2645 minutes, 26 secondsWow.
45:2745 minutes, 27 secondsAnd nearly as accurate as running the full scale simulator. So now that completely changes how you would do science, right? Because now you have 10
45:3545 minutes, 35 secondsmillion things to screen. you know, you could do that while you go to lunch rather than it being a six-month endeavor where you could try to scrape
45:4445 minutes, 44 secondstogether enough compute to to run all these simulations. And I think there's a lot of room in a lot of domains for much
45:5345 minutes, 53 secondsfaster validation models, possibly learned valu validation models that can uh you know get you a a approximation to the true answer much much more rapidly.
46:0446 minutes, 4 secondsAnd that changes how those experimental loops can be thought of and how quickly you can go around those loops.
46:1046 minutes, 10 secondsWhat are some of the spaces and problems that you're super excited that this super sped up
46:1746 minutes, 17 secondsscientific method is going to solve or achieve? What particular problems or spaces?
46:2346 minutes, 23 secondsYeah, I mean I think uh well clearly machine learning itself is one, right? So can we have a model that
46:3246 minutes, 32 secondsis able to recursively self-improve itself by running lots of experiments and you know if you think about how models are improved today in large
46:4146 minutes, 41 secondsresearch teams you know what usually happens is people think of some ideas they run a bunch of smallcale experiments they see if those small
46:5046 minutes, 50 secondsscale experiments worked out well if so they take the most promising ones of those they try them at larger scale and
46:5646 minutes, 56 secondsthat gets then evaluated and then the results get integr ated together into you know a new recipe for your model. Um
47:0647 minutes, 6 secondsbut I think there's no uh you know real impediment to making that be a much more automated loop where the model itself
47:1547 minutes, 15 secondsdecides it's going to explore or maybe with a nudge from some people uh at the various highest level like oh why don't you try some new ideas around model
47:2447 minutes, 24 secondsarchitectures that incorporate this and then it will go run lots of experiments uh see which ones work and then those will get incorporated at a much more
47:3347 minutes, 33 secondsrapid rate and uh you know effectively you want to optimize you know your discoveries per unit of compute input.
47:4447 minutes, 44 secondsVery cool. Yeah.
47:4547 minutes, 45 secondsNow going back to the room as all of you will become at some point founders or start your careers you will probably
47:5447 minutes, 54 secondscollect lots of rejections. That will happen. Uh it has happened to you too Jeff. I mean there's a story that in
48:0248 minutes, 2 seconds2014 you with Jeff Hinton and Oral Fin wrote a paper on distillation
48:1248 minutes, 12 secondswhich has to do with taking a big teacher model to train a much smaller and more efficient model that's a lot
48:2148 minutes, 21 secondscheaper to compute less model parameters and it has become a trick that everyone is using right now in industry. Yeah.
48:3048 minutes, 30 secondsAnd the thing is this paper got rejected at Europe.
48:3648 minutes, 36 secondsYeah. I mean Yeah. I mean I think I don't fault the program committee because you know a lot of times a paper
48:4448 minutes, 44 secondsgets three reviews and someone will look at one of the reviewers will look at it and in this case they said oh it's unlikely to have significant impact.
48:5248 minutes, 52 secondsUnlikely to have significant impact. But you know I think you know when we wrote the paper we actually saw this was a super important problem because we knew
49:0049 minutesmaking cheaper highly capable models from larger scale models was something we desperately wanted to do because we
49:0749 minutes, 7 secondswanted to serve models to more and more people in many different domains like speech or vision. Um but you know sometimes the reviewer maybe didn't have
49:1549 minutes, 15 secondsthat that experience because maybe they're not thinking about you know largecale AI services and are thinking
49:2249 minutes, 22 secondsabout you know is this a fundamental advance um so so you know it gets rejected every so often that's fine we
49:2949 minutes, 29 secondsput it on archive people read it people use it it's all good uh and you know we do use it in making our flash models for
49:3749 minutes, 37 secondsexample from our larger scale pro model that's partly why our flash models for example in Gemini are so capable uh relative to their size and and speed.
49:4749 minutes, 47 secondsThey're some of the best in the benchmark for their model size class.
49:5049 minutes, 50 secondsYeah. Just impressive. And I think part of the lesson is that even if you get rejected, keep going.
49:5649 minutes, 56 secondsYeah. That's that's the lesson I would distill from that.
50:0050 minutes[laughter]
50:0150 minutes, 1 secondUm no, I think the fun thing is that you basically join when you when you join Google as a 20 person startup back in 1999.
Chapter 17: Build Something That Truly Matters
50:0950 minutes, 9 secondsNow, if you were to take the young Jeff Dean from way back then to teleransport him to now today.

Jeff Dean
Jeffrey Adgate Dean is an American software engineer. He is best known for his work at Google, which he joined in 1999. He led Google AI from 2018 to 2023 and was Google's chief scientist from 2023 to 2026. Dean co-founded the AI research start-up Discovery Loop in 2026.
...more
50:1850 minutes, 18 secondsYeah. In this era with your skills.
50:2050 minutes, 20 secondsI'm feeling so vigorous and and young now.
50:2450 minutes, 24 secondsUm what would you do? Do you join a frontier lab, start a company? I don't know what what would you do? The c the Jeff theme today 25-year-old Jeff theme.
50:3650 minutes, 36 secondsYeah. I mean, it's always hard to say and it's a very personal choice of what it is you want to spend your time on. Um, to me, some
50:4650 minutes, 46 secondsof the most important questions are, are you going to work on something you really care about, will you're working
50:5550 minutes, 55 secondson that? And if you're able to make progress on it with a bunch of colleagues you like working with uh if you're able to make collectively solve
51:0451 minutes, 4 secondsit or make progress on it, will that make a difference in the world in some positive way, right? Like will you suddenly be able to do something and
51:1251 minutes, 12 secondsoffer that service to you know partically help biochemists or something or maybe
51:2151 minutes, 21 secondsit's a broader thing. It'll help programmers or it will help all consumers. uh on the internet or or
51:2751 minutes, 27 secondsother things. Um what you you know what you should strive to do is to have impact in the world that is positive and
51:3651 minutes, 36 secondsto work with people you enjoy working with and to you know uh work hard and and do your best. Um so in terms of say
51:4651 minutes, 46 secondsthe particular trade-off you offered joining a frontier lab versus say starting a company with just one or two or three of you you and your close
51:5451 minutes, 54 secondsfriends. Um, I think those are different experiences, right? In a in a large established organization, you have some
52:0252 minutes, 2 secondsstructure. You have lots and lots of amazing colleagues who know lots of things you don't. Um, you have lots of
52:1052 minutes, 10 secondsinteresting problems that uh you can work on and h you already have a platform for impact by your work, you
52:1852 minutes, 18 secondsknow, influencing lots and lots of people in the world already. Um and then as a very small startup,
52:2652 minutes, 26 secondsyou know, you have to have something you're passionate about and there's a lot of risk in taking on, you know,
52:3452 minutes, 34 secondsworking on that particular problem in a way that uh you're going to succeed and you're going to grow a, you know, an endeavor in order to do that. But that
52:4252 minutes, 42 secondscan also be incredibly rewarding, I would imagine. So I I think um you know it's really up to personal taste but but
52:5052 minutes, 50 secondsat the very least regardless of what path you take ask yourself if I work on this problem and the best possible
52:5852 minutes, 58 secondsoutcome happens you know will the world be a lot better in some way or will the world go eh that's kind of cool but whatever.
53:0653 minutes, 6 secondsUh that's not the kind of thing you should spend your time on.
53:1053 minutes, 10 secondsNow let's talk a bit about more about that second path of working with people that you really like in a small team.
53:1853 minutes, 18 secondsYou've been able to be an incredible mentor and manager to many many engineers and you've been able to build
53:2553 minutes, 25 secondshuge systems and what are some some of the lessons for everyone here on how to
53:3253 minutes, 32 secondsget the most and how to work with smart people or find smart people?
53:3653 minutes, 36 secondsYeah, I mean, you always want to find people who have really good skills in some some area
53:4553 minutes, 45 secondsthat's needed in, you know, a team you're trying to form, whether that's inside a company or uh starting a
53:5253 minutes, 52 secondscompany. Um, but you also want to find people that are people you delight being around, right? because you're going to
54:0054 minutesspend a lot of time around people working on really hard problems and you want people who are low ego that are
54:0854 minutes, 8 secondsteam players that you know have complimentary skills to your own perhaps um I always find working in a small team
54:1654 minutes, 16 secondswhere people know things that I don't know and where maybe I have some skills that other people don't have as much of you know is super fun because you're
54:2454 minutes, 24 secondscollectively building something or working on something that none of you could maybe do individually. ually, but in the process of working on that, you
54:3454 minutes, 34 secondsactually gain a lot of new knowledge and new skills uh for yourself and so do they. And you you kind of want to view
54:4154 minutes, 41 secondsyour engineering or research career as you have an amazing tool belt of techniques. And you always want to be
54:4854 minutes, 48 secondsadding new tools to that tool belt because you never know when you might come across a problem where you need these four specialized tools rather than
54:5754 minutes, 57 secondsthese three. And adding more tools makes it more likely that the problems you you encounter in the future will be solvable by you.
55:0755 minutes, 7 secondsNow, one last thing. I'm pretty sure someone in this room or multiple people will eventually build something as
55:1555 minutes, 15 secondsconsequential as you've done with map reduce, TPU, distillation, etc., etc. What problem do
55:2455 minutes, 24 secondsyou hope they would be working on? Oh yeah. I mean I I think there's a lot of interesting problems in the world and
55:3255 minutes, 32 secondsI'll just rattle off a few. This is not exhaustive because the world is a very big place and full of problems. You know I'm particularly excited about new
55:4155 minutes, 41 secondsapproaches to hardware. You know we that thought experiment there was kind of you know a you know a indication of that or much
55:5055 minutes, 50 secondsmore efficient inference hardware. You know, I think there are radically different kinds of algorithms for machine learning that might be much much
55:5855 minutes, 58 secondsmore data efficient than the approaches we're using today. If you think about our large scale models today, they probably see a thousand times as much data as a human does by the age of 18.
56:0956 minutes, 9 secondsYet, the human by the age of 18 is better in a lot of things and, you know, on par uh with those frontier models that have seen way more data. So could
56:1756 minutes, 17 secondsyou come up with much more data efficient systems that can learn continuously learn from their own actions? Uh continual learning is a
56:2656 minutes, 26 secondsreally interesting thing. I think multi- aent interactions is an interesting thing. Um you know I think you know
56:3556 minutes, 35 secondscreating ways of having better discourse among people in the world uh could be interesting. Are there ways to have much
56:4156 minutes, 41 secondsmore civil conversations and you know helping people meet other people are all over the world that they should know based on their interests. You know these
56:5056 minutes, 50 secondsare kind of interesting things. I think there there's lots of cool things in the world and we should all go and strive to make even cooler things occur.
56:5956 minutes, 59 secondsThat sounds wonderful. Thank you so much Jeff Dane. That's all we have today. Appreciate it. Thank you all.

Sync to video time