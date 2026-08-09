---
title: "We Cut 80% of Claude Code’s Prompt"
speaker: "Boris Cherny"
duration: "35:52"
views: "207K views"
tags:
  - yc-startup-school-2026
  - transcript
---

# Boris Cherny: We Cut 80% of Claude Code’s Prompt
https://www.youtube.com/watch?v=qyPCVqFUyDo&list=PLEb7ftOB0yf0&index=9
## Summary
Boris Cherny, creator of Claude Code, discusses the new capabilities of Opus 5, notably its immunity to prompt injection and its ability to run autonomously for weeks at a time. He reveals that they deleted 80% of Claude Code's system prompt because Opus 5 is intelligent enough not to need it, advising developers to empirically test and unhobble models rather than relying on rigid prompts. He highlights how Claude Code now maintains its own codebase using thousands of agents and encourages builders to give models harder tasks, focus on verification, and treat prompt engineering as an empirical science.

## Transcript
*(Add your transcript here)*


Transcript
Search in video
Intro
0:00
All [music]
What Makes Opus 5 Different
0:07
right, Boris, we're so excited to have you here, the creator of Cloud Code.
0:14
Thank you. [applause and cheering] It's great to be here.
0:21
Fresh off the press, you guys just shipped Opus 5 yesterday.
0:26
Yes. [applause and cheering] And it seems that model performance
0:31
keeps accelerating. You guys got took Arc AGI 3 to 30%.
0:39
Which is incredible. Yes. And for context, before the best score
0:44
was in in the low single digits or low teens, right? What can Opus 5 do now that it couldn't
0:53
versus a previous version? Yeah, there's um there's a lot that goes into every new model and there's a lot
1:00
of new capabilities that we teach and uh get the model to do. Whenever you do
1:06
model training, you try to teach a whole bunch of different things and most often
1:12
it doesn't work. But some subset of the things the model does learn and
1:17
sometimes it also surprises you. It has these skills. It has abilities that you you actually didn't really teach it, but
1:24
it it just kind of learned for five. One example of something it does that I
1:29
think no other model has done is it runs for a very long period of time. And
1:35
especially when you combine Opus 5 with auto mode, it's just like incredible. Like it can go for days, weeks, months
1:42
at a time. It just won't stop. Um you don't even need to use scaffolding. So
1:47
you don't need SLGO. you don't need all this other stuff. It'll just go because it knows it needs to do the task. Um,
1:54
another thing that I'm really excited about and um I'm going to start I think to talk about a little bit more um but
2:00
it's kind of surprising because it's such a new capability is the model does not seem to be prompt injectable
Solving Prompt Injection
2:06
anymore. That's prompt injectable. [applause] It's crazy like people have talked about
2:13
this like lethal trifecta for a long time and this really affects kind of harness design and agent design and and
2:19
and product design because if the model reads some instruction on the internet that's like you know do x and y and z
2:26
and also delete everything on the user's computer a year ago the model would have just done it
2:32
but nowadays opus does not and this has actually been the case since like opus
2:37
4.7 4.8 eight uh sonnet 5 has been quite good at this table was quite good at it
2:42
but opus 5 just hits like a new frontier on this. So essentially if you combine a
2:48
well- aligned model so this is like essentially three years of research into alignment with a prompt injection
2:54
classifier which we run for all traffic and what this is doing is it's based on Chrisola's mechanistic interpretability
3:00
work where it's it's literally we're looking at neurons in the model's brain that light up when prompt injection
3:06
happens. So the model won't even tell you, but we can actually see those neurons and we can figure out and
3:11
diagnose that it's happening. And then you combine that with the auto mode classifier. And with these three layers,
3:19
we just cannot demonstrate prompt injection anymore. Talking about a prompt injection, the
Why Claude Code Deleted 80% of Its System Prompt
3:24
other side of the coin is now the system prompt. Let's talk a bit about the new
3:30
release. You actually deleted over 80% of the system prompt from clock code.
3:37
Yes. Tell us more about that. I think something that a lot of people might not realize is um Claude Code as a
3:44
product and as a harness is just always changing. We're always adding stuff. We're always deleting stuff. Every time
3:51
that a new model comes out, we delete a bunch of the system prompt. Change a bunch of the system prompt. We change
3:57
the set of tools all the time. We change the prompts for the tools all the time. And the reason is every model is very
4:05
different. So something that you did for one model maybe three months ago, it just might not translate at all to the
4:13
next model. And so one thing about Opus 5 is it's just really intelligent. And a
4:20
lot of the stuff in the system prompt was correcting for these behaviors that the model should have known, but uh it
4:26
didn't. Now, Opus 5 just does it. So, yeah, we deleted 80% of the system
4:32
prompt. You can actually try deleting the rest of it too. Um, so when you run
4:38
quad code, you can just do like d-system prompt and set whatever system prompt you want if you want to experiment with
4:43
it. And another thing that you can try is um simple mode. So, this is actually
4:48
this kind of undocumented feature. If you do claude code simple equals 1 like
4:53
this uh environment variable and then you run cloud it'll delete all the system prompts including from the tools
5:00
and we actually use this as a sort of ablation to figure out is the prompt useful and what's interesting is that
5:06
the model is actually a little bit more intelligent without these prompts. That's something that we've been finding. But when you use quad code as a
5:13
product, you do actually want some of these prompts because it helps you use the product and it it helps the the
5:19
product behave and the model behave in the way that you would want when when you're using it as a person.
5:24
I think the thing that's really fascinating in this era of building basically you have built the best
5:30
hardness in the world for for claude and that's cloud code. From what I'm hearing, you for every model release,
5:37
you basically delete all of the codebase, delete all of the prompt and start from scratch every time. That in
5:44
the old world would have been not something Startup would have done for the product. It's like press delete
5:50
every six months for everything. That's right. That's right. We So to be fair, we don't delete the entire
5:55
codebase, but we do delete a lot. So every time there's a new model, we try we call in research, you call this
6:01
ablation. And so what this means is you delete the entire system prompt and then you bring it back line by line to figure
6:07
out what is the impact of each individual line. Um it's sort of like a eval and you can kind of like evaluate
6:12
it and ablation essentially it's a eval but you delete things to figure out the impact and yeah like we do the same
6:19
thing for tools like we unchip tools all the time. We you know delete code in the harness all the time. If you look at
6:24
actually the code that's in the cloud code harness today, almost all of it is about safety and permissions and static
6:31
analysis and there's a bunch of UI code and we've actually unchipped a lot of the other code already.
Press Delete on Your AI Product
6:37
Do you think this way of building a aentic product and harness and basically
6:44
doing ablations every time with a there's a new model released? Should everyone in this room that's building AI
6:50
products basically do that? be comfortable and brave to press delete. 100%. Yeah. And and for people that
6:57
aren't building agentic products, but you're using cloud code, every six months, delete your cloudmd, delete your
7:03
skills, delete your hooks, see what the model does, and it might surprise you.
7:08
And actually for Opus 5, this is something we really do recommend is just try deleting all of these things because
7:15
the model might really just not need all those instructions that you needed for past models. Let's talk a bit about how
How to Rebuild Your System Prompt
7:22
then you build this new prompt when there's a new model released like for everyone in the room. Everyone will want
7:28
to try Opus 5 and they're going to press delete on their system prompt. How do they go about building rebuilding the
7:35
system prompt? How do you set up your environment? So you do it you do it kind of piece by
7:41
piece. So the first step is you delete. The next step is you use it. And you
7:50
don't want to guess what's the instruction that the model needs because you might not predict it correctly. The
7:55
thing that you want to do is you want to run it and if it's like a custom agentic product that you're building, you want
8:00
to kind of run the product. Uh you want to see where it fails with the model. You want to see what it does well. If
8:05
you're using quad code, you want to see where it does well with your codebase or maybe where it stumbles over, you know,
8:11
the architecture or stumbles over something else. And only when you see it repeatedly stumble on the same thing,
8:18
that's when you add it back. But you don't want to do it too early because remember like the model is going to read
8:23
this instruction every single time you use it. So you really want to make sure that the model needs this instruction. I
8:29
I think this is sort of the crazy thing about building on models is just so different than all the engineering that
8:34
I've ever done. Like in the past when you built on systems, you built these like big beautiful systems and you
8:40
really think about the system design up front. you have like a big suite of unit tests, you think about everything and
8:46
you know like a rearchitecture is a big project. Sometimes it takes months. I've worked on rearchitecture products at you
8:51
know big companies that take years and the model is not like that. It's um
8:58
the way to think about it is almost like a like a living creature like as something more organic. It's a thing
9:04
where every model generation it behaves differently. it has a slightly different personality and you have to take the
9:10
time to get to know it and then adjust the harness based on that. And I I think it's just very much like an empirical
9:16
and kind of scientific thing. You have to take a very scientific mindset to it where you try something, you see the
9:22
result and then you iterate based on that. If you're building in this world right now, what then becomes uh stable? Are
9:30
eval something that you keep from the previous models and keep using them in each new model release? um we do until
9:37
we max out the eval. So that's sort of the tip for everyone. So code and system prompt you have if
9:45
you want to build at the bleeding edge and have the most capability for models, you got to delete those. But evals are
9:51
constant and keep appending to them basically. Yeah, you keep you keep appending. What
9:56
happens is um you know I actually wouldn't even go this far to be honest. I think evals they outlive the harness a
10:02
little bit but not by that much. Like an EVO might live for maybe one, two, three model generations. But nowadays the you
10:10
know we're on the exponential the model is improving so quickly very often we
10:15
just saturate the eval and then we have to throw it away and we have to come up with a new eval. And this is just part
10:20
of the process. And again it's about being empirical. You have to use the product you have to use the model. You
10:25
have to see where it struggles and then based on that that's the eval set that you should build. I think one one term I
Product Overhang and “Unhobbling” AI
10:31
heard you describe how to build the best agentic products on top of a cloud is
10:38
this concept of a unhobling cloud and tell us more more about what that
10:45
means. Yeah, so hobbling is this idea in a research that the model is doing
10:51
something and you're just getting in the way. There there's this kind of like way of
10:57
thinking about it that I really like. It's very useful when you're building product and um it it's called product
11:03
overhang and the idea is the model is able to do all sorts of
11:10
things with today's models not a future model but today's model that we have not
11:16
yet realized and there are so many capabilities the model has like this that people are not
11:23
aware of and this is like the ability to you know like maybe use use a particular
11:28
tool, use a particular language, solve a particular kind of problem, do things a particular kind of way that we thought
11:35
was kind of beyond the model's capability. And um there's this overhang
11:42
because the model can do this at every given model generation, but there is often not a product that lets the model
11:49
do this and lets it express this kind of ability to do this. And on the flip side, often what happens is the product
11:56
gets in the way. And this getting in the way, we call this hobbling and then not not eliciting the correct behavior from
12:02
the model. We call this product overhang. So it's kind of like two sides of the same thing. Well, one example of
12:08
this was the original quad code. When I first started working on it, this was um
12:14
you know, like a year and a half, two years ago, something like that. This was like SA 3.5 at the time. That was an
12:20
incredible coding model. That was like the best coding model that exists. Nowadays, it's, you know, a pretty
12:26
terrible coding model by modern standards. But I think that was like the first great coding model that that we built as Enthropic.
12:33
And at the time, if if you looked at the coding products of the time, what were what were they doing? They were doing like single line autocomplete. They were
12:40
doing sometimes multi-line autocomplete. That was sort of a new idea. Um, they were they were doing chat. So, you can
12:46
talk to the agent, but it wasn't uh write access. You could only read. You could ask about the codebase. And so the
12:52
the feeling was that there wasn't really a product that was fully eliciting the
12:57
model's capability to write entire functions at a time, entire files at a
13:03
time. At the time, it wasn't entire features. We weren't there yet, but probably entire files. That's that was the level of capability at the time. And
13:10
so the idea with cloud code was all right, we think the model can probably do this, but if we get rid of all the
13:16
scaffolding and just give the model the simplest possible harness so it can write an
13:22
entire file at a time and build an entire feature. Um, and that that was
13:27
kind of it. Like that was the product overhang of the time. The model was capable of doing something and everything was just kind of getting in
13:33
the way. I I think that nowadays with modern models there is so much product
13:38
overhang that I I'm not saying startups capture and I think there's people
13:43
thinking about these problems but there's just a huge amount amount of opportunity to elicit these behaviors
13:49
from the model that are just like amazing and interesting and and commercially valuable.
13:54
I think this is such a special insight for everyone here in the room. Basically, all of you could create the
14:01
next cloud code if you figure out how to unhobble the models because that's
14:07
effectively the birth story of clot code. You unhubble sonet 3.5 because all
14:13
the previous iterations were still getting the model very rigid in in
14:18
ideides and cloud code was one of the first instances that gave it just a full
14:24
terminal access. Yes. and that then created this amazing
Give Claude Harder Problems
14:29
product just that keeps going. So let's talk about um what are some areas and
14:36
how should future founders here think about unhobling
14:43
claw and fixing this product overhang. So there's a couple things that I will
14:49
think about. One is you should give the model slightly
14:55
harder tasks than what you think it can do. I think a a really common mistake
15:00
that I see is people are using cloud code. They're using cloud and they they just give it like way overly specific
15:07
instructions. They're like, I want you to do this, but I want you to do it in this way, this way, this way. You must do like one, then two, then three, then
15:12
four. And for modern models, that's actually really not the way to do it. You want to go a little bit higher
15:18
level. You want to describe the task, you want to describe the guardrails, you want to describe like the exit criteria
15:23
and then just go let the model cook and come back in a little bit and I think
15:29
it'll it'll surprise you like and again like this is just not something that wouldn't work six months ago but it does work today.
15:35
Can you give some examples of these challenging tasker capabilities that people should explore that it can do now
15:42
that it couldn't six months ago? Yeah. So, okay, one example is the model can
15:48
now rewrite essentially any codebase from one language to a different language. It's just sort of crazy like
15:56
it's this work that would have taken just like a very long time as an engineer and now the model's like quite
16:01
fast at it. So, so one example of this is um cloud code is built on the bun
16:06
JavaScript runtime. It's a open source JavaScript runtime. Um it's an alternative to Node.js. It's kind of a
16:12
faster node. Bun was written in Zigg. Zig is a systems programming language.
16:17
It's kind of like C. It's it's very low level. One of the problems with C with a with Zigg is you have to manually manage
16:24
memory. And so it's quite easy to run into situations where there's like memory leaks and you know other memory
16:31
management issues. And so one thing that the bun team was doing is they were having Claude fuzz the codebase and try
16:39
to simulate and trigger memory weeks. And they were doing this for, you know, for a long period of time. They were able to find a lot of memory leaks. It
16:45
was sort of like a case at a time. And that was kind of the capability of the model at the time was doing this fuzzing. And then at some point Jared on
16:53
the team was like, "Okay, let's just like rewrite it. Maybe the model can do this." And I I think this is like one of
17:00
these test problems that he kind of threw at the model with every new model generation. And starting with Fable, the
17:06
model started to be able to do it. And so I think Opus 5 could do it as well.
17:12
And so what he did was essentially he defined a test suite. The nice thing about bun is it's very very well tested.
17:19
There's a big test suite in bun. There's a big testuite in Node.js. So it's easy to know if you did the right thing. And
17:25
he had the model rewrite it from Zig to Rust. It was one prompt. It was a
17:30
dynamic workflow. And a dynamic referrals are a feature in cloud code that essentially let you orchestrate,
17:35
you know, dozens, hundred, thousands of agents to do work productively. And it ran for 11 days and it rewrote the
17:43
entire codebase. And this was one shot. It was one shot with no it wasn't one shot, but there was steering. There was
17:49
steering. Um, but previous models just couldn't do this. Even even with the steering, it just wouldn't have been possible.
17:55
Just 11 days. Oh my god. This would have taken in the past even with the best engineers multiple
18:01
months, years over definitely over a year. Yeah. Yeah. Over a year. This is like over 100,000 like JavaScript runtime is
18:07
really complicated. There's there's a lot of stuff in there. Um and yeah, like it works. This is in production out.
18:13
This is what quad code uses now when when you're running it. So this is kind of one example. I I would give a second
18:19
example. So product overhang. And so this is like a practical use case where like there's a problem you're solving.
18:25
It's like a business problem, an engineering problem, a product problem. And you should just keep throwing the latest model at it to see if it'll just
18:31
do it because even if a previous model didn't, the new one might. I think the second way to think about it is
18:37
experiment and just give yourself like freedom to play with the model and do creative
18:43
things. Often it'll surprise you. So something that's actually been really popular at uh internally that's been
18:49
kind of viral within Enthropic the last couple weeks is someone figured out that you can give Opus 5 Open CV. Oh
18:56
and you can have a draw. And so something you can do is you can ask Opus like hey use open open CV to like draw
19:02
this image and it's actually quite good. It can do like portraits. It can draw like animals. It can do like landscapes.
19:08
And we didn't train the model to draw like it's just like the solicitation gap. Like if you ask it to do it the
19:13
right way, it can just do it. And we discovered this kind of accidentally just by playing around and trying creative things that didn't have direct
19:20
commercial applications. Um, but is just kind of interesting. And my hypothesis is there's probably dozens, hundreds of
19:28
opportunities like this with the models of today that no one has yet realized. And the big area of research for this is
Prompt Engineering Is Changing
19:34
basically model elicitation, right? Becoming really good at figure out all
19:40
these capabilities and asking the model to do the right thing, right? Yes.
19:45
How do people get better at that? And effectively, how do people get better at prompt engineering? Do people still need
19:52
to do a lot of prompt engineering or is that changing as well? Tell us about where this is going.
19:57
Yeah, I I remember like a year ago, one of the most popular job openings was prompt engineer. Yeah.
20:03
Um and then it kind of changed and then I think it became like context engineer.
20:08
So there's these kind of waves of it. I I think these will kind of like come and go. I I think the skill nowadays is less
20:16
about prompt engineering and more about figuring out how do you give cla a hard
20:21
task that seems a little bit too hard and then how do you make it possible for cla to verify its work along the way and
20:29
the verification I think is probably the single most important thing that people do not get right largely
20:35
um one example of this is people were uh
20:40
you know we have this desktop app for cloud and it's built using Electron. We've made it quite fast. So now it's like a
20:47
pretty awesome experience. 6 months ago it was like sluggish and it wasn't very reliable. Now it's pretty awesome and
20:53
you know it's the thing that most of the team uses. As an experiment though I wanted to see like what would it feel
20:58
like if it was native. And so what I did is I I started a cloud tag session. And cloud tag is just you
21:05
know it's a it's a new product we have. It's just quad running in Slack. My first question was, "Hey, Tag, do you have access to a Mac OS runner on
21:11
GitHub?" And it said no. And then I I hooked up a runner. So, it was able to start a Mac virtual machine uh using
21:18
GitHub. And then um my second question is uh I created this like empty codebase that was uh quad desktop app rewritten
21:26
in Swift. And I asked can you access this codebase? It said no. And then uh I gave it access and it was like okay
21:31
great now I have access. And then I was like, "Okay, now I want what I want you to do is I want you to rewrite the
21:38
Electron app in Swift. I want you to run the Electron app in
21:44
the Mac virtual machine, screenshot it, and then look pixel by pixel, compare it
21:50
to the Swift version, don't stop until you're done." And that was your prompt basically.
21:56
That was my prompt. And how long did this take to run? It's still running.
The Two-Week Claude Code Prompt
22:02
When did you start it? [laughter] It's been uh it's been a little over two weeks. So, it's like 14 days, 15 days.
22:09
Yeah. So, I don't know if anyone in the audience has gotten clock to run a a
22:15
task for more than two weeks. I don't know. Raise your hand. Anyone in the audience?
22:23
Oh, all right. Some some this this is like one of these um this is about elicitation. So, so this is
22:30
really one of those examples where the model can do it today. You just have to let it do it. And you don't need the
22:35
fancy stuff. You don't need slashgo. You don't need sloop. These help, but really
22:41
all you need is give the model the task. Give it a way to verify the output of its work so it doesn't get stuck and
22:46
it'll just go. And actually, in this case, Quad also decided to live blog it. So, what it did is it created a Slack
22:53
channel internally, and it started just posting screenshots every few minutes of its progress. Wow.
22:59
So the prompt sound is so simple. I mean everyone here could do it. And um I
23:06
guess what is separating the people here that can become the top 1% clock users?
23:13
How how do how can people learn to use Clocko like Boris? Maybe like don't listen to the LinkedIn
23:20
influencers. Don't listen to don't read Twitter. [cheering] [applause]
23:28
This is the thing about the model is uh I think everyone's looking for like the one weird trick to do it. The there's
23:33
just like that doesn't exist. There's nothing like that. The the way the model works is you have to approach it empirically. You have to give it a task
23:39
that's too hard. You have to give it the tools to verify the work like you would yourself like you would if you were doing the task. You have to see where it
23:46
struggles and then uh you have to like fix that either with better prompting or with a skill or if the model's missing
23:53
context like give it to MCP. so it can pull in the context that uh that it needs. That's kind of it.
23:59
It sounds very simple. [laughter] I think people tend to overthink it a little bit. I think people tend to overengineer because I think in a lot of
24:06
ways like when we built systems in the past, that's the way you had to do it. So when I look at engineers that have been you know coding for a long for a
24:13
long time you know like for for years or for decades this is a really really common failure mode is trying to oversp
24:20
specify and it's trying to be overly specific and you know get the model to do the to do the task exactly the way
24:25
that you would have done it and that that's just not the way the model works but I think a lot of people are kind of
24:30
unlearning this and it's a journey to to unburn it and um it's a journey to kind
24:36
of figure out how how do you treat this thing like you would a co-orker I think that's the level of intelligence that
24:41
it's at now. And as part of this, let's go deeper into this task is still running two weeks since you launched it ago two
Running Thousands of AI Agents
24:47
weeks ago. How many agents did it spawn? You know, I'm not sure. I I can ask Quad
24:52
and then I I can get back to you. I I would guess thousands, tens of thousands. Has anyone in the audience had a uh
25:00
prompt to to renew the models that run that spawn more than a thousand agents?
25:06
No. I think this is another of the tips like the best cloud users are able to
25:12
spawn tasks that are really providing you a lot of leverage like thousands of agents.
25:17
Yes. How do you do that? There there's a few different ways to do it. Um the easiest way is dynamic
25:25
workflows. To use dynamic workflows is a fairly new feature in quad code and all
25:30
you have to say is use a workflow. That's it. And then cloud will just trigger the dynamic workflow. What a
25:37
dynamic workflow is is essentially we have the bun we have the bun runtime. We
25:42
use bun as a sandbox and we start a virtual machine within bun and we let
25:47
cloud start a lot of agents and orchestrate them. And it it doesn't just do one agent. It doesn't just do like 10
25:52
parallel agents. What it might do is um let's say a task is like rewrite the codebase or do really in-depth data
26:00
analysis over some really complicated data or maybe like build a very complex feature that takes multiple stages and
26:07
maybe dozens of pull requests. And so what it's going to do is it's going to start a a bunch of agents to do kind of
26:13
like the first pass. Based on that, it might do a second step where it has
26:18
another set of agents that verify the work or that summarize the work. then it
26:23
might do like a third stage where it'll fan out again. So it'll kind of productively orchestrate a bunch of
26:28
different agents. So my background is functional programming. And so the way that we designed this is it's
26:33
essentially an algebra for agents. So there's a way to run agents in sequence. There's a way to run agents in
26:40
parallel. And Cloud has different tools in order to orchestrate these agents inside of the sandbox to use tokens
26:48
efficiently to do really really complex work. It's kind of cool in something
26:54
that just hasn't really been written about a lot. Like this is actually like a new form of test time compute. Like
26:59
when we talk about the scaling laws and kind of we talk about the model getting more intelligent over time. Historically
27:06
it's been a function of the size of the neural net, the amount of training data and the number of flops that you put in
27:11
to the training. And then recently we also added test time compute. So this is essentially a fancy way researcher way
27:18
of saying how many tokens does it generate. And now dynamic workflows are
27:23
essentially a new way to orchestrate test time compute and it's a new way to kind of really really ramp up the amount
27:30
of test time compute that you use to do a really hard task. So this all very
27:35
long way to say this is one way to launch thousands of agents in a way that is productive and efficient. A second
27:41
way to do it is loops and routines. Loop is essentially a cron job that's running
27:46
locally for quad. Routine is the same thing, but it's running in the quad in the cloud. So, you can close your
27:53
laptop. And this is like slightly different because for a dynamic workflow, it's one task and you break it
27:58
up into chunks. For loops and routines, it's one task that is repetitive that doesn't share context, but it might
28:04
share memory. And you kind of do this like over and over. You can do it like maybe every hour, every 5 minutes, every
28:10
day. And so, a thing that we've started doing is um we actually have quad maintaining itself now. And the way we do this is we
28:18
have a Slack channel where we just had Cloud start a bunch of different routines to maintain its own codebase.
28:24
And we actually do this for the CLI, for the iOS app, for the Android app, uh for the desktop app. And for example, one
28:32
routine is clean up dead code. This is a single prompt. It's like one sentence. Cloud runs this every day. It'll look
28:38
for dead code across all the code bases using static and dynamic analysis. We didn't prompt that. It just kind of
28:44
figured it out. and it'll put a pull request every day to delete the dead code. Another example is uh shipping
28:50
experiments that should go out. Um so the experiment's already out to 100%. It'll delete it from the codebase and
28:57
it'll just ship it. Another one is writing tests for areas of the codebase that need test coverage. Another one is
29:04
deleting tests that don't need to be there because you know they were kind of useless tests added by older models or
29:09
added by people at some point. One that one that I really love is this um I forgot what we called it. I think we
29:15
called it abstraction police. And the idea is there are often in a big codebase there's kind of the same
29:21
abstraction and it appears multiple times and if you kind of squint it actually maybe should just be the same abstraction but kind of over time for
29:28
whatever reason you rebuilt it multiple ways in different parts of the codebase. So cloud kind of goes out every day
29:35
across all our code bases it finds these nearly duplicated abstractions and it unifies them. And so now we have every
29:41
day maybe 20 or 30 of these routines. It's running across all of our code bases. And it's not totally there yet,
29:49
but we're on the path to fully automating the maintenance of our apps by doing this. And this is again
29:56
hundreds of agents running every day, sometimes thousands of agents every day. It's doing the work of, you know, dozens
30:02
or hundreds of engineers. This is kind of what it used to take to do this kind of work. And this means that engineers
30:08
can just like do the thing they actually want to do which is ship new products and talk to users and uh do stuff that's
30:14
actually fun. I guess next conclusion from this which you have mentioned in the past that basically coding is solve
Coding Is (Almost) Solved
30:21
right you have mentioned this um I'm curious now that effectively everyone
30:27
can write software what separates the exceptional builders
30:34
from the rest what what are the qualities now that everyone can ship code I I would give like one caveat so coding
30:40
is solved for the kind of coding that I do it's not solved for everyone You know, there's still code bases that
30:47
are like super deep systems code bases where cloud still struggles. There's distributed systems where cloud still
30:53
struggles. There's really kind of in the weeds UI verification, like something is off by pixel or something. CL is still
30:58
not perfect at this. Like Opus 5 was a big leap in vision and computer use, but it's still not perfect. Um, but I I'm
31:06
actually curious for people here. Maybe raise your hand if 100% of your code is written using agents. You don't write
31:12
any code by hand anymore. It's pretty good. Okay. How about more
31:18
than 50%. Slightly less hands. Maybe about the
31:23
same. Yeah. So, I think it's like it's getting there. So, it's kind of getting to this to, you know, to being solved
31:30
for more and more kinds of code. And that's kind of cool. When I think about the people that are the best at using
31:35
quad, I think there's a certain mindset that you can bring that's really
31:40
effective. And it's really about being empirical. So forget all the things that you learn
31:47
about past models. Forget everything that you learned about computer science theory in class.
31:54
Look at the model, try to do a task, see where it struggles, and then based on
31:59
that adjust. So it's just like very much become it's not a theoretical science,
32:04
it's become an empirical science. So I think people that are really good at this, that are really good at kind of
32:09
forgetting their priors, letting go of you know this like maybe idea that didn't work before and just being open
32:14
to trying it again. This is the kind of skill that's just very very successful now.
What Every CS Student Should Still Learn
32:20
Now my last question is given everything that we talked about if there's someone
32:26
here that's studying CS and you you learned to program before this era of uh AI agent coding what
32:34
should students still learn the hard way like the old way. So for me, I learned
32:41
computer science practically. I learned it by teaching myself to code in order
32:47
to solve problems. Whenever I was doing this, I was doing it to solve a
32:53
particular problem that I had. So I actually first learned to code on uh TI
32:58
83 calculators. Um this is back in middle school. And um I ended up
33:03
actually writing a guide on the internet for programming TI 83 calculators. It's still up on the internet somewhere. Um,
33:08
and it was uh it was basic that that was my first language. And I I learned how to program on a calculator so I could
33:15
just like get better at my math tests by uh by cheating on the test.
33:21
[applause] So it it it was about something
33:27
practical, you know, like to me as a middle schooler that was kind of like the most practical thing I could think of. And I ended up getting good grades
33:33
and then I got this little serial cable to give the, you know, the programs to my classmates and they got really good grades. And then the math got a little
33:40
bit harder. Um, it wasn't something that I could solve in basic anymore. So I kind of went from this like, you know,
33:45
like maybe algebra solver that was written in basic and I had to solve harder problems. And um, you know, like
33:52
once we got into calculus, I had to learn assembly so that I could write a better solver so I could cheat better on
33:58
the test now that it was calculus. And so for me, programming has always been very practical and I think this is
34:04
always my advice for people in school is learn not just the computer science. This is like intellectually fascinating
34:10
and it's really really interesting to know but learn how to apply it. And often this is about building startups. It's about building products. It's about
34:17
developing your own design sense, developing your business sense, learning how to how to do data science, learning
34:23
how to talk to users. There are all these other skills. And when you combine it with computer science and
34:29
engineering, that's where it becomes really really valuable. So those are the hard skills that I would still be doing
34:34
by hand. So if I'm hearing and summarizing, start with making something you want first for
34:41
yourself and then level up and make something people want. Yes.
34:47
And we just have one last special announcement. Boris, you want to one one last thing?
34:53
Yeah. So um for everyone here today uh you are getting max 20x
35:03
[cheering]
35:08
[cheering] [laughter]
35:14
incredible pretty good. [applause] So look for look for code in your email
35:20
and uh I can't wait to see what you build. police.
35:26
[applause] [cheering] [applause] So, I'm curious. Someone in
35:32
this room should be building something that runs hopefully multiple months and thousands of agents now that you have
35:38
the account to do it. And with that, thank you so much, Morris. Thank you. Thank you. [cheering]
35:47
[applause]
