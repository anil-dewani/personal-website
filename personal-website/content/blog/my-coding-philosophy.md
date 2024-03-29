---
title: "My Code Development Philosophy"
summary: "There is always a right way to code and wrong way to code, after having dwelled into various projects and scenarios - I've collected various sets of laws/philosophies to abide, for making my code resilient and more aligned towards the industry standards"
cover_photo: "https://i.imgur.com/9XHe1Wa.jpeg"
read_time: "6 min"
---


I'd like to share my journey and the insights I've gathered while navigating the vibrant and challenging landscape of Information Technology...

Coding is a structured form of creativity, distinct from the abstract freedom of painting where your mind wanders intuitively. Though coding involves subjective choices, making it somewhat artistic, it fundamentally remains a process of creation. It's about constructing things, bringing them into existence with your skills, and ensuring they are resilient, clean, and functional.

As I delved into Information Technology, the abundance of new tools, methodologies, and the frequent occurrence of security breaches due to poor programming practices were overwhelming. Every day brought something new to learn and apply. The excitement was palpable and utterly consuming.

Even after a decade, I continue to discover new ideas and possibilities born from the relentless creativity of those who can't stop creating.

The DIY (Do-It-Yourself) nature of this field quickly made it clear that there are effective and ineffective approaches to problem-solving. Merely learning a new programming language from the internet wasn't sufficient. Here are some philosophical insights I've adopted to refine my creative process and enhance its resilience.

## Technical Debt
![Technical Debt](https://i.imgur.com/ZQpPImG.png)

We all must’ve heard about term like financial debt, but what about technical debt? To keep it simple, technical debt is about being conscious of the consequences which can get accumulated when we take shortcuts while developing our code.

For example, you can build your code faster if you avoid creating its documentation along with it. You can keep releasing new versions without solving bugs in the older versions. These examples will be considered a scenario that creates technical debt. 

Inherently, technical debt is not good or bad. It depends upon how it is leveraged. Its like any other loan, if you manage to yield more profits then the extra interest you pay for the loan, its well worth it. The only viable necessity is to be aware of the consequences which can come by taking shortcuts. You can estimate the technical debt by considering various factors such as: bugs and exploits, code quality and resource consumption, to name a few.


## Estimations Matter

![Estimations Matter](https://i.imgur.com/u3RFWG5.png)

Ever been in a scenario when you estimated to complete a code in one week and it all made complete sense in your mind, but when you actually execute it - it took away your whole month? It’s happened to a lot of us. The typical answer to this issue is to learn to make better estimations.

Since coding is very diverse and there are a lot of ways things can go wrong, it’s almost a skill to learn to form efficient estimates about your development workflows. Most of the time we fall in this trap of under-estimating the time and resources needed. This is why we see most of the business person in software development industry giving over-estimations to their clients. 

Personally for me, the core aspect to gaining correct estimates breaks down to: breaking down the project into mini functionality modules and estimating resources for deploying each functionality individually. Calculate it and add 50% extra for testing, debugging and bug fixes. Of-course it is very subjective process and depends on various quality and quantity metrics involved in the process.


## Valuing Simplicity

![Value of Simplicity](https://i.imgur.com/DDHpBFh.png)

Often times, major bugs, errors and issue happen because of the high entropy nature of the code. The higher the complexity, the higher probability of errors and exploits to surface up.

Hence, keeping things simplistic is considered as a top notch skill. A programmer with a very diverse set of knowledge can easily lose its way and end up choosing the complex ways to solve simple things. 

True art is to develop your skill-set and take it to new heights but at the same time practice grounding. Learn to stay a minimalist. Minimalist approach teaches you to be cultivate enough clarity and resourceful needed to keep things simplistic.

Keeping things simple is actually not as easy as it seems in this realm, for sure. Very skilled programmers fall for this trap easily. The solution to this problem is to have a habit of minimalism and develop habit of pre-cognition before you start coding your implementations. Be clear within first, and then you will be able to be simplistic in your manifestations too. Take a few deep breaths, if it helps.


## Avoiding Assumptions

![Avoiding Assumptions](https://i.imgur.com/b8bdjEF.png)

A lot of coding is about speculation. Speculating the ways in which a problem can be solved. Speculating about various tools required to develop the infrastructural needs of the software. Speculating about the set of features required by the consumers of the software and many more!

The more you speculate, the more is the chance of assumptions. Assumptions are vital in this creative process of speculation, however a wrong assumption can quickly create accidental complexities. Your assumptions should be rooted in current trends and industry truths, not fantasy. It’s very easy to get lost in wild speculation and unworthy assumptions.

For example, it’s easy to speculate that you will use a certain set of software packages but you unconsciously assume that software package to be as secure as it used to be. It’s easy to speculate that your consumers want a feature you are building, but in reality your assumption is not rooted in their actual needs.

Trick here is to double-check all your assumptions and put them into right perspective as soon as you discover them. Try to be in touch with the industry standards, consumer necessities and relevant best practices.


## Avoiding Premature Optimizations

![Avoiding Premature Optimizations](https://i.imgur.com/r4uyd4h.png)

Once you are flowing in that mental flow state of coding for hours while rocking your favourite lo-fi music in the background, it becomes very easy to get caught up into optimisation a certain functionality or feature-set much beyond the actual needs.

This way, you end up building features and functionalities into your software which were actually never needed. You just build it because you were enjoying your flow state. This eventually ends up in creating un-necessary features and avoids the need to keep things simplistic for security concerns.

The solution is to always have the next steps of task ready in your to-do list or project kan-ban for your sprints. Aim should be to stay on the sprint plan and be in that mental flow state for as long as you can without falling into the trap of optimising your code beyond actual necessities. Plan before you enter into the flow state and that will help a lot.


## Embracing Modularity

![Embracing Modularity](https://i.imgur.com/O9LU9vn.png)

 It’s been a well-known pattern in the software industry to keep your code modular and structured into smaller inter-connected segments than one big complex script doing multiple things at a time.

As long as you have a feature which is big enough to be divided into smaller modular units of functionalities. It should be divided into sub-modules. This also avoids coding the same sub-sections needed for different feature-sets as the modular approach lets you develop plug-and-play kind of a modular structure to your code.

Documenting becomes much simplistic and easier as well because of this modular approach.

Putting these modules into a packaged hierarchy using the object oriented approach is a vital step towards making your code modular, clean and easy to debug.


## Maintaining Resilient Integrity

![Maintaining Resilient Integrity](https://i.imgur.com/0EPtEpz.png)

Developing a highly structured software goes through various software life cycles. If the task is to develop a highly complex software - the major emphasis should be given to follow standard protocols of releasing the software. Usually any new project should be considered pre-alpha and eventually should progress towards alpha, beta, delta and finally release for marketing and production. 


It’s vital to setup git workflows, tag each new release with appropriate software versioning. Bugs and issues should be tagged to a specific version of the software. 

Having different branches for each feature-set along with a separate development and release branches helps a lot with maintaining the code and gives a bird-eye view towards the whole setup.

Aim should always be to pre-plan the complete work-flow for development and management of the code. Sticking to industry standardised workflows saves you from a lot of problems which you might not have anticipated when you began.


## Choosing Tools Wisely

![Choosing Tools Wisely](https://i.imgur.com/JUgictY.png)

 Since a lot of programmers love to follow the DRY Principle which states that there is really no need to re-invent the wheel and if there is a software package available on the internet for free, it should be utilised.


However, this approach comes with few caveats, specially if you are building critical software which has a lot of compliance necessities. 

Not all software packages you utilise for free on the internet provide LTS Support aka there is no long terms support and many of such software packages aren’t even maintained and updated anymore.

It’s vital to maintain a complete list of all the tools and packages used by your software which are not actually maintained by you. This list helps with all the security related compliances and quality checks. 

A lot of the time, it is better to code your own version of a package if there is no LTS support available. It’s best to avoid packages where you cannot find active managers of those packages, it’s vital to also look into active issues which are open on that package to make the right decision.

Since we as coders love to utilise frameworks and cookie-cutters, this should not become a lazy habit. There is a responsibility to stay up-to-date regarding all the tools in our tool-set. Get rid of the ones which can cause trouble in your workflow, and keep finding newer ones which are highly maintained and polished.


## Automating Processes

![Automating process](https://i.imgur.com/w50VtJl.png)

Isn’t it the most fascinating thing to just witness your computers do all the hard-work for you while you sip on that chilled coffee? Sure, it is. Thats what computers are for, we can command them a lot of things as long as we learn to command and configure them in the most optimal ways.

Modern software development is incomplete without utilising automation frameworks into your work flow. These automation frameworks can be configured to do automatic builds for each new release candidate you push to your release branches, it can auto-deploy your code to development and production servers. A lot of unit testing frameworks utilise automation to do black-box and white-box testing on your code base to automatically discover new bugs, errors and misconfigurations. Eventually, with advancements in machine learning frameworks, the day is not far that software would eventually fix the bugs automatically as well.  

One more vital part of automation setup is to setup security audits for your all your front-facing business critical aspects of your software - these softwares try to maintain a up-to-date list of exploits and try to check if the exploits can be used to break into your software and alert you in real-time.

Setting up these automation frameworks helps in reducing down your software development cycles, gives you better snapshot into your setup and saves you a lot of valuable time.


## Conclusion
These insights have shaped my approach to software development, emphasizing continuous learning and the application of effective methodologies. I hope they offer valuable perspectives for others in this field.

I welcome the sharing of experiences and strategies that have benefited your work. Your contributions can enrich our collective understanding and practices.

Let's continue to embrace the creative flow that drives our work in Information Technology.
