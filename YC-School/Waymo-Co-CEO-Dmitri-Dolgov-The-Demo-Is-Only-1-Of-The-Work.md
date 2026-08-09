---
title: "The Demo Is Only 1% Of The Work"
speaker: "Waymo Co-CEO Dmitri Dolgov"
duration: "49:24"
views: "25K views"
tags:
  - yc-startup-school-2026
  - transcript
---

# Waymo Co-CEO Dmitri Dolgov: The Demo Is Only 1% Of The Work
https://www.youtube.com/watch?v=Gp4zrV3-6N8&list=PLEb7ftOB0yf0&index=4
## Summary
*(Add summary here)*

## Transcript
Chapters

Transcript
Search in video
Seven Lessons From Building Waymo
0:07
Good afternoon everyone. It's great to be here. Uh we talk a lot about AI that
0:15
lives on your screen uh lives in the digital world. And today I'd like to
0:21
talk to you about a different kind of AI that we've been building at Whimo. AI that lives in the real physical world.
0:31
How many of you by the way have been in a Whimo? Just raise your arms.
0:36
Wow. Okay, that is impressive. Especially I understand many of you are out of town. Uh the folks who are
0:43
visiting and have not had a chance to check out Whimo, I hope while you're here in the Bay Area, give it a try. Uh
0:50
so this being a startup school, I structured this presentation as a
0:55
sequence of lessons, seven lessons that we've learned over the years at Whimo
1:02
around what it takes to build and safely ship today's most mature application of
1:09
AI in the physical world, the Whimo driver. Uh let me start with a short video. Uh
1:19
this is a clip from a ride that I recently took in a Whimo with my kids.
1:26
Uh so as you see here, you know, we're moving uh forward. We're proceeding through an intersection and a couple of
1:32
human drivers just decide to cut in right in front of us and the Whimo driver reacted safely, reacted smoothly.
1:40
In fact, so much so that the kids, my kids were preoccupied in the back seat. They didn't even notice that anything
1:45
happened. And to me, this was a pretty powerful moment. I've been working on this technology and this product for
1:52
close to two decades, and you know, it just did something fairly important. It
1:58
acted safely. It kept my kids safe. It kept everybody safe and nobody noticed.
2:04
And that I think will be a bit of a theme in general when it comes to physical AI that the best AI moments
2:13
will look like nothing happened. It's just the task got done safely and smoothly.
Why Physical AI Is Different
2:21
And these sort of moments where the Whimo driver kept everyone safe are
2:27
happening daily across our fleet. Today the Whimo driver is serving around 500
2:34
trips per week and driving over 4 million fully autonomous miles every week in 15 cities across the United
2:41
States. Just for a comparison, that's over 300 years every week of an average American
2:48
driver per year. And the Whimo driver is accomplishing that with a superhuman safety record.
2:57
So what what does it take to build and deploy an AI agent in the physical world
3:03
at scale? Now in Silicon Valley there's a common
3:10
mantra to move fast and break things.
3:15
However, when you're dealing with atoms instead of bits, breaking things is not really okay.
3:21
So the thing you have to do is to move fast and ship safely.
3:29
And that's a much more difficult thing to do. You have to build systems that are robust from day one. You have to
3:36
build AI models and you have to build training recipes where safety is the foundation and not an afterthought, not
3:42
an add-on. And by the way, the problem itself of physical AI is different from digital
3:48
AI. There are four main gaps that you have
3:54
to contend with if you're building AI for the physical world versus the digital world.
3:59
First, there is the cost of error gaps. have a language model or a chatbot or a
4:06
co-pilot and it makes a mistake, you know, usually it costs you a retry.
4:11
In the physical world, the cost of a mistake can be measured in human lives,
4:17
not tokens. There's simply not an undo and a retry button.
4:23
Secondly, you have the latency gap. And typically when you're running a VLM uh
4:28
or you know a digital assistant, it can take many seconds, sometimes minutes to
4:36
come back with an answer to you. A car traveling at freeway speeds moves
4:41
about 100 feet in 1 second. So their milliseconds really matter. And you have
4:47
to run all of your inference, make all of your decisions on board a compute that fits in a trunk of your car.
4:56
Next, there's the data gap. Uh, digital AI had the internet of this wonderful
5:03
immense cache of pre-labeled human knowledge and human thought that we've
5:08
ever assembled. There's no digitized version of the
5:13
internet for the physical world. And lastly, there's the validation gap.
5:19
In digital AI, often you can ship something that's good enough and that
5:26
you let your users you uh use your product, they find the edge cases and
5:31
that allows you to deploy on day one practically at unlimited scale and then
5:36
you can just iterate and hill climb on quality from there. In physical AI, the situation is
5:42
different. Given the high cost of errors, you need to have a very high
5:49
level of safety and a very high level of confidence on day one before you deploy
5:54
your first robot, before you drive your your first autonomous mile.
5:59
Now, at the same time, when you're dealing with physical AI,
6:04
uh the actual experience of having your agent in the real world is invaluable
6:10
and it's irreplaceable. uh these systems are not just something that you can build in the lab you know
6:16
get it perfect and then deploy at full scale overnight. So given those two
6:22
factors you really need to super clearly and super crisply define the operating
6:29
conditions and the deployment parameters of your agent and then build a rigorous
6:34
framework to guide your deployment so that you can scale in a responsible manner. And this is
6:42
absolutely critical. Uh this is how you earn trust from your customers, from the
6:48
communities, from the regulators and yourself. Uh so at Whimo, we see these gaps of
Lesson 1: The Gap Between a Demo and a Product
6:54
course in the context of autonomous vehicles. Uh but these gaps uh will show up in practically any sort of
7:01
non-trivial physical agent that we will deploy uh in some shape or form. and driving is just simply the first domain
7:08
where AI has crossed these four gaps at scale with the public interacting with our product.
7:15
So let's dive into those lessons that we've learned over the years at Whimo from uh working on this problem and uh
7:21
talk about how we address those gaps. Uh I have seven lessons in this talk. Um I
7:26
they're all technical. There's a lot more that goes into building a company and building a product. Uh but today
7:32
I'll just focus on the technical aspects of building AI for the physical world. Uh and each one of those lessons I think
7:39
by itself will not be exactly earthshattering. Uh you know a lot of it will overlap with likely things you've
7:45
heard elsewhere. But I hope that the grounding of these lessons in our experience and some of the nuance that I
7:53
can add about how they showed up uh in our experience of deploying a physical
7:58
agent in the and scaling it safely will be interesting and useful for many of you who are in the space as you build
8:05
your product as you build your startup. Uh so let's dive in. And the first lesson has to do with this uh massive
8:14
frustrating sometimes soul crushing difference between a demo
8:20
and a real product. And a working demo is 1% at best of the work that you have
8:25
to do. The many nines of performance, the many nines of reliability that follow, that's where the real work
8:30
happens. And if you're a founder in the room, uh, chances are you are focused on getting that first prototype, that first
8:37
demo, uh, off the ground. And when you hit that first version of a system that
8:43
works, that first 90%, when the demo actually works, it feels incredible. You feel like you solved it, the sky's is
8:49
the limit, you're extrapolating forward. And in our world, we hit that first
8:54
milestone, that first 90% back around 2010. So when this project started uh in
9:02
2009 before we started building the system we set a couple of pretty ambitious goals
9:08
for ourselves. One was to drive a 100 autonomous 100,000
9:14
miles in autonomous mode. The second goal was to drive 10 routes. Each one
9:20
was 100 miles long uh chosen to cover a v variety of conditions across the Bay Area. And we had to do each one from
9:27
beginning to end without a human intervention. We had at the time a team of about a dozen engineers and we
9:35
accomplished both of these goals in about a year and a half. And keep in mind this was well before any of the AI
9:41
breakthroughs before connes before transformers before BLMs before any of the stuff that we talk about today. Uh
9:48
and yet you know we got it done and kind of by demo standards we driving
9:53
autonomous driving was solved in 2010 right we handled everything we handled
9:59
we could drive during the day during the night we handled traffic pedestrians cyclist traffic lights construction
10:05
zones on freeways on surface streets so we were quote unquote capability complete and you know at the time we
10:11
felt like we're on top of the world but then we quickly ran as we started building towards a product we quickly
10:17
ran into a brutal reality that there's a massive difference between doing
10:22
something once or driving 10 routes once and building a scalable service with nobody behind the wheel.
10:30
It took us about 10 more years to begin providing a service and then five more
10:37
years to scale to half a million trips per week. So the demo took 18 months, the product took about 15 years, but now
10:45
we're scaling exponentially. To date, we've served well over 20 million fully autonomous trips, and we've driven well
10:52
over 200 million fully autonomous miles. And we have rider only vehicles operating in 15 cities across the United
10:59
States. And we're scaling exponentially. It took us uh 15 years to get to that first 100
11:08
million miles and about 7 months to drive the next 100 million. It took us
11:14
about 8 years to go from the time when we started our initial rider only
11:20
operation to the time when we had uh when we were serving riders uh in four
11:26
cities. Earlier this year we launched four cities in just one day.
11:33
So why does bridging that gap from demo to product take so long? Well, because
Why Reliability Lives on an Exponential Curve
11:40
there's this harsh engineering reality that you can't really cheat. That reliability and performance lives on
11:46
this exponential ladder of nines. So getting to that first 90% or 99% that's the easy part.
11:53
But then every next nine that you want to add, that takes about 10 times more effort. So you need to know upfront
12:00
exactly how many nines your product actually needs.
12:06
So demo might need, you know, one nine. An assist product or, you know, co-pilot
12:11
might need a few, but a fully autonomous AI agent that we're going to be putting out in the physical world that engages
12:17
with the public, you know, with kids running around, that needs a whole stack of them. And at scale, the long tail is
12:25
the problem space. It's your entire problem statement. When you drive millions of miles per week, a rare event
12:32
that might happen once in a million miles, that just becomes your daily reality. And getting those next nines
12:40
means doing something different every time. So you don't get to say six nines
12:45
of performance or reliability by doing the same thing that you did for you know to achieve the first two but longer. You
12:53
have to do fundamentally different things. You requires a fundamentally different approach. For example, we can take reliability. You can, you know, get
12:59
to the first couple of nines by just doing proper engineering and uh doing, you know, uh some bug fixes, but to get
13:06
to the next few, you need to have you need to invest in fundamentally different approaches. You need to build
13:12
fully redundant systems, uh have tiered fallback architectures and so forth and
13:17
so on. And the same thing holds for the performance of AI models.
13:23
So what that actually means is that in this space it's incredibly easy to get
13:29
started but it can be excruciatingly difficult to get to the real product and
13:34
that effect is only amplified with every wave of technological breakthroughs and
13:41
that naturally leads to hype cycles. So every AI breakthrough from you know deep
13:46
learning to condors VLAMs you name it it makes it that much
13:52
easier to get started your demos your prototypes they get a 100 times easier but the tail that's where the hard
13:58
problems are that moves much less it moves but the effect is muted and that's why every hype cycle produces a wave of
14:05
absolutely spectacular demos and very few real products and the recurring mistake of every cycle is spending on
14:12
the demo what you should be saving for the eyes. Now, you know, this being a startup
Lesson 2: Pick the Right Technology Curve
14:18
school, the last thing I want to do is throw too much cold water on the magic and the excitement of those early days.
14:24
This this time is absolutely magical. It's amazing. Cherish it, leverage it.
14:29
But the key is to remain honest about the product that you're building, the number of nines and performance and
14:35
reliability that that product demands, and not cutting corners to get there. uh
14:40
otherwise you might be in for a pretty rude uh awakening later. So count your nines before you count your demo views.
14:48
Uh and this brings us to the second lesson. Once you know how many nines your product actually needs, it
14:55
fundamentally dictates the architecture and the core technical approach that you need to pursue.
15:02
Now every technology has a performance versus effort curve, right? They all
15:07
tend to start fairly steep and go up and then they flatten out. And you know, as I just mentioned, every other nine gets
15:14
an order of magnitude more difficult. So common failure mode is picking the tech
15:20
that gives you the fastest early ramp, riding that steep curve, feeling like
15:26
you're winning, projecting that, you know, steep slope into the future and feeling like the sky is the limit and then hitting the plateau and discovering
15:33
that the technology path that you picked actually flattens out way before the
15:40
performance that is required by your product. Now, you might still choose to be at
15:45
least for a while on that steep curve uh for a variety of practical reasons. You know, maybe you want to prototype
15:52
something or demo something or build something in service of learning. But be honest with yourself where you're
15:57
building for the purpose of a demo, for the purpose of learning or towards an actual product.
16:04
Uh so let's take uh an example from our domain autonomous vehicle and sensing.
Why Waymo Uses Cameras, LiDAR, and Radar
16:10
Uh there's been a long-standing debate about what kind of sensors do you actually need for autonomous driving.
16:16
Naturally, more sensors means higher performance, but also means higher complexity. So humans of course can
16:24
drive with just eyes. So there's that proof of existence. Now, and if the goal
16:29
were to just approximately match human performance or to build an assist product, that's a very reasonable way to
16:36
go. However, if you're targeting full autonomy and you're targeting superhuman
16:42
strongly superhuman performance, you find that weak sensing just leads to a safety curve that flattens out way too
16:48
early. So, at Whimo, we've taken an approach where we use multiple sensing modalities. We use cameras, lighters,
16:55
and radars, and they all complement each other. Cameras give you high resolution and color, uh, but they're passive, and
17:02
they degrade in darkness and glare. Lighter gives you a direct measurement
17:07
of the 3D structure of the world uh around you and radar is very good at
17:14
punching through environmental conditions and weather like fog or rain or snow and it directly can measure
17:19
velocity using doubler. Uh lighter and radar are active sensors. Uh so that
17:25
means they see just as well in pitch darkness or for example when driving
17:30
into a blinding sunset. And these different sensing modalities, of course, they're not backups to each other. Uh,
17:36
in our stack, each modality has an encoder and the information from all of
17:42
those sensors get fused into a single view of the world around us that is much more precise and um, generally vastly
17:50
superior to what you get with any one sensor. So, let me show you a few examples. Uh, here's a scene where a
17:57
Whimo is driving in a dust storm in Phoenix. So what you see here is what the scene
18:03
looks like to our fairly advanced high resolution and high dynamic range
18:09
camera. It's very close to what a c, you know, a human would see in the same conditions,
18:14
which is not much. And here on the right is what the lighter sees for the exact same frame. And you can much more
18:21
clearly see that there's a pedestrian standing on the side of the road. So if they were to step onto the road, that
18:28
early detection can make a really big difference in how the situation plays out and the safety of everyone involved.
18:36
Here's another example. At night driving along and there are a couple of pedestrians who are about to jump onto
18:42
the road over a concrete construction barrier. Again, at the bottom you see the camera, really can't see much. And
18:48
the lighter view at the top. Again, lighter versus camera. Here's another
18:54
example. A couple of dogs chasing a bull and a
19:01
couple of kids chasing the dogs. And big difference. Here's what it looks like to
19:07
the camera. Here's the lighter and the early detection of the uh the kids is off to the side and there are no
19:13
headlights. There are no lamps there. It's complete darkness. So, it makes a big difference. Uh or think about what
19:18
happens when something physically obstructs the view of your sensors.
19:24
uh you know if you don't have redundancy in sensing you can have you know a single leaf land on your sensors and
19:31
bring your robot to a full stop. Uh now
19:36
so you need redundancy. Redundancy of course does not necessarily mean multiple sensing modalities but if you
19:44
need redundancy anyway you might as well uh benefit from the complimentary
19:49
physics of the different sensing modalities in the nominal case. So, here's a a video of uh one of our
19:57
cars that picked up a leaf or actually I think a full uh branch of a tree uh that
20:02
our wipers were unable to shake and the car detected that and because we have sensing redundancy, it safely was able
20:09
to get back to the depot for proper cleaning. Uh so specifically when it comes to
20:17
hardware uh do not anchor to today's components
20:23
prices. Uh we are on the sixth generation of the Whimo driver, the Whimo hardware suite
20:31
today and with every generation the hardware not only delivered amazing capability but we're able to drastically
20:38
simplify and radically reduce the cost of the hardware as well. So betting your company, betting your approach on
20:44
today's hardware prices is just betting your company on a number that has a fairly short shelf life and is going to
20:51
expire. Uh so hardware will change. Uh many components will get commoditized
20:57
and drop in price. So design for that future and be ready to upgrade.
21:05
And that brings us to the next lesson. Lesson number three. Uh technology moves
Lesson 3: Ride Every Technology Wave
21:10
incredibly fast especially nowadays. So you need to be ready to ride those tech
21:16
waves and do that repeatedly. And when you do have to not only think about the
21:22
wins in performance and the wins in per capability, you have to be very mindful about uh unification and simplification.
21:32
Uh over the years we've seen a number of major breakthroughs in technology. a lot
21:37
of them around AI and with every wave of innovation, we pretty much rebuild the Whimo driver around that major wave of
21:43
AI breakthroughs and we often push the state-of-the-art in those areas forward ourselves. Uh we leveraged Connets
21:51
around 2013 for computer vision and perception. Then when transformers came about around 2017, we bet big on them
21:59
both for perception and for the task of behavior prediction and decision- making and planning. Turns out the task of
22:06
driving is not that dissimilar from the task of modeling language. Uh because of the social aspects of driving, you're
22:12
kind of having a conversation with other dynamic actors in the world, but you're doing that in the space kind of body
22:17
language of your agent, your car, as opposed to just the language of words.
22:23
Uh and you operate in sequences and local continuity matters. Uh but so does global context. uh and today we're
22:29
leveraging uh the latest in VLMs and Frontier world models.
22:35
Now using the latest tech for capability and
22:40
performance wins, I don't want to say it's easy, but it can be you know reasonably straightforward. Doing applied research in isolation or
22:47
starting a tiger team to you know prototype uh some new technology uh is not the most difficult part. There's
22:53
many companies, many teams that are excellent in this. The much harder muscle to build is to carry that
23:00
bleeding edge research into production and deploy it in a safety critical environment without regressions
23:08
and do it without breaking stride on the scaling of your product. And adding capability again is not the
23:16
hardest part, but adding capability while at the same time reducing fragmentation and reducing complexity
23:22
that is really important. And finally, the hard muscle to build as a company is to be able to do that repeatedly through
23:29
multiple waves of technical innovation and technical breakthroughs. So on this front, I have two bits of
23:34
advice. Uh the first one, when the technology, a new technology shows up, you know, it can be very exciting, very
23:41
tempting to kick off uh a new effort, a tiger team to pursue it. And that's great. You should absolutely do that.
23:48
However, when you do, it's very important that you consider what you would do after under a success scenario.
23:55
Let's say that effort succeeds, you should be very clear on what the path of that new innovation is for your company,
24:01
for your entire product, for your entire system. Uh, often times I've seen a failure mode where you know a project, a
24:07
very difficult technical project succeeds and then there's a dead end. So that can be very wasteful. That can be
24:14
completely you know deflating. Uh the second bit of advice I have here is uh
24:19
when pursuing new tech again don't just ask what does this new tech give me in
24:24
terms of capability and performance also ask has it simplified my stack and has it led to fragmentation or unification.
24:31
So set your launch bar to demand both breakthrough performance and at the same time radical simplification and
24:37
unification. And this exact philosophy and this muscle that we've built uh at Whimo over
Inside the Waymo Foundation Model
24:44
the years is what produced our latest core technology. Uh and this the heart
24:50
of it is the Whimo foundation model. Now the Whimo foundation model is a multimodal world action language model.
24:58
That's kind of a mouthful. So let me unpack the ingredients. It's a multimodal model because it is able to
25:05
process these multiodal sensor inputs, cameras, lighters, and radar. Uh it's a
25:10
world model because it inherently understands how the world works, the physics, the dynamics as well as the
25:16
social and semantic aspect of it. It's an action model because we are not just
25:21
passively observing how the world evolves. Uh we're an active participant. So the model needs to understand the
25:28
effects of our the actions of our agent on the world and be able to tell the
25:34
good ones from bad ones. And finally, it's aligned with language and that allows us to unlock general world
25:40
knowledge from visual language models and that's incredibly useful in the long tail of rare semantic uh situations.
25:50
So more specifically uh this is what the architecture looks like. It's kind of your typical encoder decoder
25:56
architecture. The encoder part takes in the multimodal sensing and compresses it
26:02
or encodes it into a efficient into an efficient representation uh that retains
26:08
all of the relevant data, all of the relevant information for the generative part or the decoder. It's an endto-end
26:16
model um which has a couple of nice properties. It allows us to effectively
26:21
back propagate the gradient from the task that we actually care about all the way to the early layers of the model and
26:28
it allows the encoder to reach you kind of learn the right rich representations
26:33
uh for what the generative part needs to solve the task. Uh it uses a system one
26:38
system two think fast think slow architecture and it leverages the general world knowledge of VLMs for
26:45
efficient learning of semantic tasks. So let's dive uh deeper. Uh first the think
26:51
fast path. Uh that part fuses the raw data from our cameras, our lighters, our radars and that allows for split-second
26:59
safety critical decisions. So you can think of it as kind of your driving instincts. Uh this is what allows the
27:04
car to break instantly if let's say a pedestrian runs into the road or a cyclist that's nearby swers into your
27:11
path. uh this is like the the if you will the lizard brain of your agent that
27:17
deals with a lot of geometric tasks and can react in milliseconds.
27:22
Uh second is the slow path. Uh that's the part that's responsible for the more complex uh semantic and scene level
27:30
understanding type tasks. And these sort of task these things don't typically change in milliseconds. So there you can
27:38
afford a bit more latency and you can trade that off for higher capability and
27:45
higher levels of uh of reasoning. So for example, if the whim driver encounters a
27:52
situation when there's, you know, a vehicle, let's say it's on fire on the side of the road, the fast path might
27:59
just see it as a generic uh generic obstacle and, you know, reason that the path ahead of us is clear. And this is
28:05
where the slow path comes in. And that path can use deep semantic reasoning to understand the semantics of that object,
28:12
the car being on fire and the broader scene context. And that allows our driver to decide to take a very, you
28:19
know, different action or a different route entirely even if geometrically the path ahead of us is very is clear.
28:27
Uh and finally there's the generate component. That's the decoder. That's the component that understands and can
28:33
produce behavior. Uh it understands how other actors behave uh and it allows us to make predictions and plan our own
28:40
driving decisions. And our Whimo foundation model powers
28:45
the Whimo driver that runs on different generations of hardware and runs on
28:51
different vehicle platforms. You have our fifth generation and sixth generation, the JLR IPA, the Ohigh and
28:57
the Hyundai Ionic. and in the future will power different products and different commercial applications like
29:03
trucking and personally owned vehicles. So by uh leveraging the strategy of
29:11
focusing on the high capacity foundation of uh ofboard model, we're able to move
29:17
a lot of complexity upstream to that large shared foundation and that allows us to make that specialization layer uh
29:25
that's running on the car uh uh pretty lightweight and that in turn allows us
29:30
to speed up the development process. So the most important muscle in this lesson uh is for your company to not just
29:39
leverage the tech of the day but have the ability and build that muscle to
29:44
repeatedly ride those tech waves and pull in the results of that innovation into production without regression
29:51
without breaking stride in deployment and scaling and without drowning in complexity.
29:57
So let's move to the next lesson. Uh there is a well-known lesson in the AI
30:04
community that general methods that leverage massive
Lesson 4: The Bitter Lesson Still Wins
30:10
compute and massive data will always beat methods that rely on handcrafted
30:18
engineered human knowledge. That's the so-called uh bitter lesson that Richard
30:23
Sutton uh published and formulated in 2019. And we have lived this and we have
30:29
seen this in every wave of technical breakthroughs. Each time the bitter lesson holds methods that scale best
30:36
with compute with data, they always win out. And by the way, this is uh you know
30:41
one of the reasons why we bet on the approach of building the foundation model. Um uh there is a well-known
30:48
property that if you bet on high-capacity model and you use your data and your compute on that you just
30:56
get better scaling laws and then you distill into smaller more efficient models that are running on your agent in
31:02
real time. You just get better scaling laws as opposed to just focusing on the smaller models directly.
31:08
Uh so one nuance area where uh this lesson shows up is the use of structure
31:15
in your models and depending on how you use your structure
31:21
you can end up on either side of the bitter lesson. Essentially structure
31:26
that fights scale will always lose and structure that channel scale always
31:31
wins. In particular this comes up around the discussion of end toend models. As I
31:37
mentioned an end toend model is, you know, uh has some very nice properties. You back properly gradient from the
31:43
final tasks all the way through the model and it allows the API between the
31:48
encoder and the decoder to learn to use rich learn representations and you know
31:54
those are the easiest models to build and train. um you know you can start uh the architectures are known you can
32:00
start with doing some imitation learning and a uh kind of a black box end toend model will give you very rapid progress
32:06
and you will ride that very you know initial steep part of the curve uh and for some products that's enough but if
32:12
you need to reach superhuman levels of performance in a fully autonomous agent in a safety critical environment uh just
32:19
doing kind of that basic vanilla end to end is not enough and this is where structure comes in and the key question
32:25
here is does the structure boost scale or does it fight it? Does it limit and
32:32
constrain your solution space or does it help you scale without loss of
32:37
generality? So, let me give you uh an example. Let me illustrate this point with kind of a
32:43
a simple thought exercise and a a toy problem. Imagine you're building a robot that will play
32:51
the game of goal and it wants you know you want it to play the game in the physical world right so you have a
32:57
camera that's observing the board and you have an actuator that will actually move the pieces around now one way you
33:03
can build such a robot is to you know have an end to-end system that goes directly from pixels to actuation and
33:09
maybe you train it by giving you some videos of you know how humans play the game uh and that could be a very
33:15
interesting research search exercise. However, if your goal was to build the world's best playing Go robot, that's
33:21
probably not the most efficient way to go. And the reason for that is that
33:26
there is a very simple intermediate representation that captures completely
33:33
the state of the game, the state of the the task that you're trying to solve. as you know 19 by19 board and that gives
33:41
you a fully observable and complete state of the world that you care about at least for the you know game plan
33:46
laying part. So leveraging that structure it doesn't limit your model it doesn't constrain your solution space
33:51
but it gives you a very helpful way to scale. Now that of course was a toy
33:56
example. Uh anything that's not trivial that you're trying to deploy in the physical world will not have that
34:02
property. And the fact that such a simple clean engineered representation doesn't exist in the physical world is
34:07
the whole reason why we need endto-end uh systems and learned representations
34:12
and learned embeddings. But in the physical world that does exist structure. You have laws of physics. You have rules
34:19
of the road. You have objects that behave in reasonably predictable ways. uh and you can use that structure in
34:25
addition to the learned representations to boost your performance, simplify validation and at the end of the day you
34:30
just get better scaling loss. Uh and this is the approach that we are pursuing at Whimo which we call
34:37
structure augmented end to end. So we go beyond the basic vanilla end to end by augmenting the learn embeddings with
34:44
materialized structure representations and that gives us a few very important advantages. So first is validation at
34:52
inference time. Now because the model isn't just a black box where sensors go in and you know uh actuation commands go
34:59
out, we can create a very powerful correctness and safety validation layer
35:05
that uh you can run in real time in uh uh when the agent is deployed on our
35:11
vehicles and this is really important for any agent that's operating in the physical world.
35:17
Uh secondly, we get great wins in efficiency when it comes to largecale
35:22
training and evaluation of the generative part of the model, the decoder. Now, if all you have is a
35:29
blackbox end to end system, you are forced to do all of your evaluation and all of your training in the end toend
35:36
setup all the way from sensors to decisions to actuation. Having that intermediate structured representation
35:42
allows you to kind of mix and match. You can do some training at larger scale uh and some evaluation in the space of
35:48
those compact structure representations and some in the full space of end to end from sensors to decisions. Uh and
35:56
finally we get strong verifiable feedback signals for both evaluation and
36:02
for training uh training recipes to support things like reinforcement learning. that additional materialized
36:07
structure just gives you uh much more powerful tools for evaluation for metrics as well as crafting your loss
36:15
function or you know reinforcement learning recipes. So the lesson here is to bet on a system that's maximally
36:22
learned and minimally constrained and leverage structure intentionally to boost performance and scaling laws both
36:29
in training and in evaluation. Now that raises the question of how do
36:35
you actually train and evaluate your physical AI agent? And that brings us to
36:40
the next lesson. To build and safely deploy an agent in the physical world,
Lesson 5: Why Every Physical AI Company Needs a Simulator
36:46
it is absolutely critical to have a good large scale realistic highfidelity
36:51
simulator. Now there's two ways you can do training and evaluation. You can do open loop and
36:58
you can do closed loop. uh in open loop kind of passively observing uh input to
37:04
output pairs uh and you can use that you know for evaluation for training imitation learning works like that
37:09
evaluation takes usually this shape of you know if you are find yourself in this situation what would you do and
37:14
then you you score that uh and that's in contrast with closed loop where in closed loop you take an action
37:21
uh you see the effect that that action has on the world then uh you update your
37:28
uh through your sensors the view of the world, you take another action and so forth and so on and you evaluate and you
37:33
train on those sequence of actions and sequence of world evolutions. Now the ability to take an action and evaluate
37:40
that counterfactual is absolutely vital for building and deploying safety critical agents in the
37:47
physical world. Uh so a real simulator is how you do
37:54
that. And a real simulator isn't just some lightweight tooling that sits next to your AI. Uh it is
38:03
an uh a big AI model in of itself. And the problem of building a good realistic
38:09
simulator is just as hard as building the agent itself. Uh so the AI behind
38:14
the simulator really needs to understand how the world works, the physics, the semantics, you know, the traffic, the
38:20
weather, and so on and so forth. And the quality of that simulator has to be high enough so that it doesn't only look
38:26
good, but it's sufficient to train and evaluate with high confidence an agent
38:32
that you're going to be putting in the world in a safety critical environment. So in other words, you have to build a
38:38
highly accurate generative world model. And at Whimo for years, we've been
38:44
building what we called uh behavioral world models. And you were doing that way before the term world models even
38:51
became popular. Uh and now in the era of endto-end models, you also need on top
38:58
of behavioral realism, you need sensing realism as well. And in fact, uh
39:03
building an end toend model has been fairly easy for quite a while now. But
39:09
evaluating it in closed loop that was the hard part of the problem. So we've
39:14
moved on to building sensing world models. And because we're using that structure augmented representation in
39:21
our models, uh we can also leverage that structure in our simulation.
39:26
Our behavior world model operates in the space of structured intermediate representations and the tightly coupled
39:34
sensor world model then producing produces realistic uh sensor simulations.
39:40
Our world model leverages uh the great work of Google deep minds on Gen3 and
39:47
that gives us the ability to produce controllable and highly realistic scenarios both in the behavioral as well
39:54
as uh sensing aspects. And that in turn allows us to not just
39:59
evaluate our agent uh and train uh new versions of our agent in situations that
40:06
we've previously encountered, but it allows us to train and evaluate in purely synthetic rare scenarios that
40:13
we've never seen in the real world. So what you're seeing here is not just a
40:19
generated video. It's a generative a full generous simulation of the Whimo driver uh in uh operating closed loop.
40:26
Uh so here we're simulating what would happen if it came across a car that was stopped in a lane on the freeway. Uh and
40:33
you can go further than that. Here's a plane that's landing on a freeway in front of us.
40:39
where you can simulate an elephant on the loose walking through the intersection,
40:45
snow on the Golden Gate Bridge or a dinosaur walking around. So the lesson here is that closed loop
40:52
simulation is absolutely required for evaluation and is extremely val valuable
40:58
for training of your physical AI agents. So you need highly realistic large scale
41:05
simulation to tri train and evaluate. And this brings us to lesson number uh
41:11
six. When you're dealing with a problem of that complexity, you
41:18
can't just build a model and call it a day. You have to build an entire
41:23
ecosystem. And then you also need a flywheel that powers it. Because to make this work at scale, you can't just build
41:31
the agent. You and one AI, you need to build three. You're building the agent
Lesson 6: Build an AI Flywheel
41:37
for us. That's the driver that drives the car. You also have the simulator,
41:42
uh, which is that virtual playground for the agent to learn in. And then you have the critic. And the critic is what
41:49
rigorously evaluates and judges the performance of the agent and tells it how to improve. And the good news is
41:56
that the fundamental reasoning and the generative capabilities of all three of
42:01
those are shared and that's why in our case they're based on the same foundation world model.
42:11
Now once you have these three pillars you can create an incredibly powerful
42:17
flywheel to accelerate your progress. So a deployment of your agent uh in the
42:23
real world generates data. That data then grounds the simulator and makes it
42:28
more realistic. The simulator generates harder age cases for the critic to score and for the
42:35
agent to learn from. So the agent gets smarter, gets deployed in the physical world, generate more data and that
42:40
powers the flywheel and accelerates progress. But a flywheel of course will you know
42:47
spin in any direction or in place. So in order to make it go in the direction you
42:54
want you need to guide it by metrics. And that brings us to the final lesson that your model is really table stakes
43:01
but eval and metrics that's your most important that's your strategic mode.
43:09
So build your eval before you build your technology. build your eval and your
43:14
metrics before you build your product. If you can't quantitatively define what
43:20
good enough means, you're not really building a product. You're just iterating on your demo. So nowadays,
Lesson 7: Evals Are Your Competitive Advantage
43:27
the best model architectures are fairly wellnown and new ideas tend to uh
43:33
proliferate fairly quickly. Data is incredibly important, but
43:40
without good metrics, you're just flying blind. you aren't leveraging the best data and you can't really evaluate the
43:46
ROI on making changes to it. So really eval and metrics that that's your
43:51
foundation and that what steers your whole tech stack.
43:57
Uh but for physical AI agents model level evaluation is not enough.
44:04
When you're putting an AI agent into the physical world, your eval and your validation needs to go much deeper and
44:11
much broader. You need to evaluate and validate every component of your system
44:17
from the physical layer to the behavioral layer uh that's running on board in the physical world as well as
44:23
the offboard components and uh all of the operational processes around it. So
44:28
for us we call that the safety and readiness framework and we spend years
44:34
building and refining it and uh that's what guides our development and our deployment and our scaling and I
44:40
consider that to be one of our most important uh assets
44:46
uh be and this again the reason it's important is because in the physical world trust is everything
44:54
and eval and metrics is how you go about earning that trust. You don't just win trust by talking
45:01
about, you know, the clever technical solution or the clever state-of-the-art architecture of your models or doing,
45:08
you know, flash a demo. You earn it gradually day by day by uh in the field
45:16
by relentlessly proving that your system is safe and that your system works. And of course, you can just prove that to
45:22
yourself behind closed doors. And this is exactly why we openly publish our safety data and our uh safety ongoing
45:30
safety research. So then that earned trust becomes your ultimate business
45:36
advantage, right? Your your models can be leaked, algorithms can be replicated,
45:42
but hundreds of millions of miles of fully autonomous operations in the real world backed by evidence-grade
45:49
evaluation and publicly audited proof that is much much more difficult to replicate.
45:55
So when you zoom out and look at this playbook as a whole, you realize that none of these lessons works alone. So
46:01
the nine set your bar and ensure that you pick the right technology and the right technical approach so that you
46:07
don't get stuck on the local minimum. Uh then intentional use of structure to boost scaling uh and the ability to ride
How Waymo Became 17x Safer Than Human Drivers
46:15
technical waves of innovation. I guess helps you get to the right level of nines uh and your AI ecosystem with the
46:22
agent, the simulator and the critic guided by ER eval and metrics. That's what allows you to build that powerful
46:27
flywheel and that's how all of these effects uh compound.
46:33
And it's this playbook that we've been refining uh over the years is what allows us to achieve the strongly
46:40
superhuman safety performance of the Whimo driver. Uh this is a snapshot of the latest safety data we've released is
46:46
based on over 220 million fully autonomous miles. And we're seeing there that in the areas where we operate, the
46:53
Whimo driver is about 17 times better than human drivers when it comes to
46:59
crashes uh that cause serious injury. And that really matters
47:06
uh because today somewhere in the world every 26 seconds someone loses their
47:13
lives on a road to a crash event. And on the current scale what that means is
47:18
that Whimo is preventing a serious injury every eight days. And this isn't just a metric on a dashboard. That means
47:24
that someone's loved one got to walk through the front of the door at the end of the day safe and unharmed.
47:32
So these are just the early safety uh benefits of AI in the physical world and
47:37
they will only grow from there. If you look at the broader landscape, the opportunity here is absolutely massive.
47:44
Uh physical AI right now is where digital AI was a few years ago and we have all of the right ingredients to go
47:50
after it. We have degenerative world models. We have the architectures. We have affordable compute and sensing. We
47:56
have proven scaling laws. And we have a real product operating at scale. And the last decade of AI happened in
The Next Decade of AI Will Be Physical
48:03
the digital world. I think the next decade will also happen in the physical world. And for those of you who decide
48:10
to build in the space, uh, good luck, have fun, and remember who you're
48:16
building for, your mission, and your customers. That's what matters. Uh otherwise tech is just a science project
48:22
and at the end of the day as exciting as exhilarating the tech is nothing really
48:28
beats the joy of making a difference in people's lives. [applause]
48:38
What are we doing? We're in our first ever Whimo. And what does it mean when we're in a Whimo? It means that there is nobody.
48:44
Nobody driving this thing. And uh this is a fully autonomous Whimo ride.
48:50
I cannot believe this. The car did a better job than the if somebody was driving.
48:57
The truck was over the yellow line. So the Whimo break and moved to the side.
49:06
It knew how to pronounce my name. Oh my god. Look at this. Oh, it's nice. [music] I love it. This
49:12
is not This is so cool.
49:18
I'll never forget this. Never. Sorry.
