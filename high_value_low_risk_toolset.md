Title:   A High Value Low Risk Tool Set  
Author:  Olle Törnström toernstroem[at]synyx.de  
Date:    2014-05-15 -- 2014-08-29  
Version: 0.8

A High Value Low Risk Tool Set
==============================

**TL;DR: Progressive enhancement, yes. Content is still king. Must have deep domain knowledge of HTML/CSS/JavaScript. Libraries instead of frameworks. Design and architecture for your client side apps too.**

I think it's fair to say that application development for the web is truly a minefield of change and uncertainty. The cause being technical progress and evolution of both software and hardware. This process of change is of course good, and I think we must accept that **change will remain constant over time**.

In this document I'm going to explain my view on how to manage this situation, and describe what I believe is a sound technical approach to application development in the web eco-system, **at this point in time**.

Core values
-----------

Before I go into specific technical details I'm going to establish a few basic rules or guiding ethics for development in general, and explain why I find them important, and how they apply to my analysis.

### 1. End user value over technical agenda

Luckily most developers already understand this. More and more the focus is to build _what's best for the user_ and not what's most fitting for the language, library, tool or platform. We build _applications_ for people, and rather _systems_ for machines. The distinction is that we shouldn't put technical elegance before the value our application provides to the person using it.

### 2. Agility is responsible resource use

Change, in my opinion, as mentioned in the introduction, applies equally to business opportunities, requirements and constraints. We can't plan for these events, we can only react to them. The actions we take are based on some current options, but there are [rules for options][1] that we can apply to our process:

   [1]: http://www.infoq.com/articles/real-options-enhance-agility

> 1. Options have value.
> 2. Options expire.
> 3. Never commit early unless you know why.

In doing this, we strive to reduce waste and create the best possible value from the options we have, based on the information we have at that point in time. This is how we can save resources, time and money. But we must be ready to iterate and re-evaluate a solution again at a later time. That's enhancing value, in an iterative manner.

### 3. Observed usefulness as the metric of quality

I'm convinced that only end user feedback can give a true indication on whether an application provides the value that is required or not. Establishing channels and methods to gain that feedback is vital. Technical quality should never be sacrificed, but the true metric of quality software is simply end user happiness and productivity. Being able to understand how the end users feel is a part of understanding this quality metric. Improvements that lead to happier end users should have priority.

### 4. Technical craftsmanship

Observing best practices and using idiomatic and _modern_ development methodologies will act as a protection against failure to deliver quality. Solutions should be implemented at the correct complexity level, never too simple or too complex. Optimization for _readability_ first allows for lower maintenance cost. Code review, pair-programming or open source development are key triggers for transparency and a sound technical approach.

Leaky abstractions
------------------

I'm convinced that we can't make any qualified argument about technology without taking the issue of [leaky abstractions][2], coined as _"The law of leaky abstractions"_ by Joel Spoolsky in his [blogpost from 2002][3], into account. It states:

   [2]: http://google.com?q=leaky+abstractions
   [3]: http://www.joelonsoftware.com/articles/LeakyAbstractions.html

> All non-trivial abstractions, to some degree, are leaky.

What it means is that any layer of abstraction, never fully abstracts away its underlying layer. We have to know or learn the _implementation_ of the abstraction to understand the cause and effect of using it. You basically can't remove the requirement of deeper domain knowledge.

So for us this means, that regardless of what framework, tool or library we use for web application development, we have to have a deep knowledge and understanding about HTML, CSS and JavaScript (among other things).

The ubiquitous platform
-----------------------

I'm convinced that we must view the target platform technologies, HTML, CSS and JavaScript, as true knowledge requirements. Based on what we've mentioned earlier, those are the abstractions and implementations that we have to be able to understand and explain, regardless of what tool set we wish to use.

For example, an ever recurring issue when using JavaScript widgets is the fallacy in thinking that using them does not require one to understand how they work. This often leads to higher technical debt to pay off - bugs that suddenly remove more end user value than the widget provided to begin with.

The target for our efforts are to build applications that will run in web browsers. We just can't get away from that fact. We must learn and understand the limits of the domain, and use the abilities of the platform.

Progressively enhanced content
------------------------------

Progressive enhancement guides us to build features that adapt their richness based on the context where they're used. Now, it is argued that [progressive enhancement is dead][4], but [other][5] [people][6] [disagree][7]. I would also disagree. Progressive enhancement is great way for us to reason about end user value in an iterative and agile way. It matches our core values perfectly.

   [4]: http://tomdale.net/2013/09/progressive-enhancement-is-dead/
   [5]: http://thatemil.com/blog/2013/07/02/progressive-enhancement-still-not-dead/
   [6]: http://jakearchibald.com/2013/progressive-enhancement-still-important/
   [7]: http://christianheilmann.com/2012/02/16/stumbling-on-the-escalator/

For example say that we can provide something valuable to the end user by simply creating content - a simple HTML-based page of information. That content could then later be enhanced, if and only if it's required in order to make the application more efficient or enjoyable to the end user. We can choose to execute our options at the last possible time and are not required to commit.

_Remember that content and data are not necessarily the same thing. Content is made with the intention of being for humans, and therefore having a higher value to the end user._

What's important to us is to understand and take into account how suitable some technology or tool is to the concept of progressive enhancement, if we wan't to benefit from it.

### The fear of "mobile first"

I find it sad that, in the context of progressive enhancement, there's currently a great fear, and in my opinion, misunderstanding about "mobile first". I think it's not an option and not a matter of cost-control - it is the most sound way to define end user value as being usable in the wide variety of devices of today.

Done the right way, "mobile first" merely becomes the better initial version of end user content, before enhancing for the more advanced (desktop) platform. It is a first step that is done anyway, and not an option and not necessarily an opt-in cost consideration. Just do it.

Vertical cuts
-------------

It comes with a _buzz word warning_ to mention "vertical features or services", but sadly it's a bit of an overlooked possibility. Committing to vertically cut features, in the context of web application development, can give us many more options to adapt the technology to the solution we're building, and not the other way around.

There are many ways that we can support this separation in deployment packaging: separate VM's, processes or more web application contexts running inside an application server. This is not something new, it's just not used that way very often.

If one part of a web application simply is posting and viewing data, and the other part is a highly dynamic client side application, the sensible thing to do, would be to make the cut with regards to the technical demands. One of the two apps does not require anything but plain old server pages, but the other one require massive green threads, web sockets and the hottest JavaScript library out there.

Separate them. Make the cut. It's risk management. If we take this route, the issue of finding a technical stack becomes less of a single decision, and more a collection of recommendations, where the application will dictate the choice of the best possible stack for it's requirements.

Templating
----------

Using a template engine for content creation is very much a work process management decision. It can provide the team with an option to separate the art direction, layout and design implementation from the technical view, view model or domain modelling. For some this is the only way to ensure high velocity iterations, where web developers won't have to wait for full server reloads or code that needs to compile.

We should understand that the right templating solution is empowering. The question is how much power do we want to give this technical layer?

Templates languages all have a property of being more or less expressive, allowing the user to actually _program_ with it. On one side of the spectrum there are template solutions that cross over their context boundary, and actually program in the programming language of their "host" e.g. JSP/JSTL or PHP. Moving towards the other end of the spectrum we have less logic, less conditionals, only structuring and output. Or the most extreme, component based templates, where there's no logic at all.

This is a dear and [heavily][8] [debated][9] [issue][10]. I think we can agree that a template language that allows too much freedom often leads to code that blurs the border between business and presentation logic. Languages with less logic will often require pre-massaging of the data before it can be rendered into the view, which basically puts view-code directly next to the business code (but not mixing).

   [8]: http://www.workingsoftware.com.au/page/Your_templating_engine_sucks_and_everything_you_have_ever_written_is_spaghetti_code_yes_you
   [9]: http://www.ebaytechblog.com/2012/10/01/the-case-against-logic-less-templates
   [10]: http://stackoverflow.com/questions/3896730/whats-the-advantage-of-logic-less-template-such-as-mustache

I think less logic templating is the better choice. My view is that template languages without good constraints will basically self-deteriorate into a mess through the use of ugly hacks, all with the best of intentions.

Another thing to consider regarding templating is what benefits there are from choosing a technology that can be used both on the server side as well as on the client side. I don't have any deeper experience here, but my guess is that this means making a compromise. There are some [interesting][11] [articles][12] on the matter, and I would suggest digging deeper into that matter.

   [11]: http://engineering.linkedin.com/frontend/leaving-jsps-dust-moving-linkedin-dustjs-client-side-templates
   [12]: http://engineering.linkedin.com/frontend/client-side-templating-throwdown-mustache-handlebars-dustjs-and-more

Styling
-------

With the risk of sounding like a broken record - again, my previous statements about core values, leaky abstractions and progressive enhancement apply to styling or CSS too. Added to that, I think we have to recognize that CSS authoring (or development) is very much a practiced craft. There are of course specs, but boy let me tell you, did the browsers get them wrong. At least they choose to interpret them differently.

First, please understand that there is a [great][13] [body][14] of [work][15] on the [matter][16], and that CSS also requires [design and structure][17], just as any other part of your application.

   [13]: http://smacss.com/book/
   [14]: http://www.stubbornella.org/content/2010/07/01/top-5-mistakes-of-massive-css/
   [15]: http://viget.com/inspire/css-squareoff
   [16]: http://www.hagenburger.net/BLOG/Modular-CSS-Class-Names.html
   [17]: http://www.sitepoint.com/css-architectures-scalable-and-modular-approaches/

I like the modular approach, and I've seen (and created) enough CSS-mess to believe in the need for a better way. Understanding how loose coupling can reduce the volume of CSS code is real eye-opener. There is basically no real _need_ for tools in styling, just well crafted and well though out CSS.

### CSS pre-processors

So at this point it's good to direct the attention to pre-processors. If we **first** apply modular styling and loose coupling of HTML and CSS, then it's ok to add pre-processing, as icing on the cake.

The power that variables, mix-ins and functions bring to CSS authoring is all good. It makes it easy for us to create re-usable themes and removes some issues with plain CSS. Colors, typography and grid-dimensions can for example be declared as common constraints for all stylings.

Which pre-processor to use is just another religious matter, in my opinion. But I think it's more important to evaluate how the tool fits the build process. Is it easy to use? Will it require runtime resources in production? And so on.

### CSS-frameworks

So there's a big promise typically made by [styling][18] [frameworks][19] out there - they will solve the problem of styling for you... in one great, free to use, very much hyped, and cool, oh did I mention it's open source? ...magically.

   [18]: http://getbootstrap.com
   [19]: http://foundation.zurb.com

Here are some people with [opinions][20] [against][21], [using][22] one of the popular frameworks. I think you should read up on their views, and other discussions you might find on the issue.

   [20]: http://blog.idyllic-software.com/why-we-dont-use-twitter-bootstrap/
   [21]: http://halanstevens.com/blog/bootstrap-youre-doing-it-wrong/
   [22]: http://fourkitchens.com/blog/2013/10/09/you-dont-need-bootstrap

My point of view is that we should not buy in to the framework until we can se the benefit. We want to commit only when we understand why. Any given feature in one of the frameworks will most certainly be available as a small, separate, widget or library that does only that thing - perhaps even better.

Frameworks provide a high benefit in the re-use they offer, with the risk that an early buy-in brings. Once skinned or themed, they can allow very fast development cycles and orthogonal iterations for pure style improvements, and business application development. The thing to understand is of course that it applies a constraint - only the use of commonly styled components are _allowed_. Such a constraint can of course in some situations be a pure win, if one wants to prevent heterogenous project results.

I'm saying, be careful, but also value the option to develop a commonly themed set of enforcing visual components.

### Responsive design

To me responsive design is all about content. Great content and a responsive layout, adapting to the end user device - that's pure value - and this is probably the greatest return of investment that any stakeholder can get. That is also the sweet-spot for responsive design, where the design is not forced to be responsive but rather manifests the _design_ by simply being it. An example here is a grid-based layouts, where the content is mainly text, like an online-magazine.

It's a bit more tricky in applications where the design serves a special purpose - single page apps with panels, widgets, or custom buttons and form fields. The responsiveness in these cases may be just a way to _gracefully degrade_ the user experience and this is of course a compromise. I believe that a lot of applications of that kind, try to hard to be responsive and simply end up supporting a couple of _modes_ or _sizes_. That's hardly responsive in my opinion.

I think is clear, from the two aspects of responsive design, that it's certainly not a one-size-fits-all tool. It needs be considered quite early in the development and design process, and choosing a tool that provides _grid-based responsiveness_ might mean very little if the application design just can't benefit from it.

Also, one must not forget the [problems][23] of responsiveness, bloated pages and unnecessary resource loading. The implication could be an even less useful experience for those devices it was supposed to serve in the first place (mobile). This is still an area full of [suggestions][24], engineering and [cool ideas][25], so it can most certainly pay off to not commit too early.

   [23]: http://www.guypo.com/mobile/performance-implications-of-responsive-design-book-contribution/
   [24]: http://html5doctor.com/responsive-images-end-of-year-report/
   [25]: http://responsiveicons.co.uk

Enhanced content
----------------

It should be clear from the title that I'm talking about continuing on the line of progressively enhancing any delivered content, into a higher end user value, by making it dynamic. Static content can be turned into a stream of information. Events can be sent as notifications. Page updates can be replaced by contextual reload of just some information.

### JavaScript

I'm not going to say too much about [JavaScript performance][26], but it's absolutely no longer a limiting factor. For our purposes, it's more than able to support _any_ feature we might come to think of.

   [26]: http://www.sitepoint.com/javascript-doom/

But extending value, with client-side engineering and rich applications that live on their own in the browser, requires a commitment on some tools and best practices in my opinion. For starters, some rock solid [coding][26] [standards][27] for JavaScript. Most of this conventional wisdom will hint at [some][28] [important][29] [patterns][30] that are there to preserve sanity and clarity.

   [26]: http://neil.rashbrook.org/Js.htm
   [27]: http://javascript.crockford.com/code.html
   [28]: http://www.google.com/search?q=javascript+module+pattern
   [29]: http://wiki.commonjs.org/wiki/Modules/AsynchronousDefinition
   [30]: http://www.html5rocks.com/en/tutorials/es6/promises/

There's nothing wrong with programming in JavaScript - there I've said it. Still I would recommend using [jQuery][31] as a minimal library requirement for any client side engineering. Now the zealots of [nativejs-ism][32] do have a point in their argumentation against it - less page weight. But that could be viewed as a matter of performance optimization, which can be dealt with separately.

   [31]: http://jquery.com
   [32]: http://youmightnotneedjquery.com

_It's at this point that I need to make clear, that when I say "jQuery", I mean the DOM abstraction layer library. Absolutely, in no way, do I mean the widget library "jQuery UI"._

In sort of a _handwaving_ manner I'm going to state that the [observer pattern][33] is your friend. It's of course part the nature of the DOM API, and unlocking and understanding the power of it, is a true eye opener - and the basis for some [really cool stuff][34] too. This is [not new stuff][35], but well worth digesting again. The important thing is to understand the relationship with progressive enhancement, and how orthogonal dynamic enhancements can actually be implemented. Learn it. Love it. Live it.

   [33]: http://en.wikipedia.org/wiki/Observer_pattern
   [34]: https://muut.com/blog/technology/riotjs-the-1kb-mvp-framework.html
   [35]: http://yehudakatz.com/2009/04/20/evented-programming-with-jquery/

### Quick run-through of things on my list

_This section is a quick draft of issues I didn't have time to write about, but are very much part of my view:_

- JavaScript-frameworks; most often they're full out all-in poker buy-ins, with little compromise, so use very carefully. Unless we're talking about libraries, or [polyfills][36], in which case they're cool. Libraries and selective tools are almost always the better alternative, in my opinion, and they're often composable or supported in the development-chain (RequireJS).

   [36]: http://www.polymer-project.org

- Data-binding, declarative, in JavaScript; it's all the hype, sort of like an ORM for client-side application code. Can be useful but often comes with a full framework in order to use - in that case, beware.

- Test-driven JavaScript development; do it.

- Architecture and design; Any web application that's more than just a value-enhanced content-application (using plug-ins) should have a proper architecture and design. Tiered architecture or MVC or some form of OOA/OOD is the correct way to go about building a client side application in JavaScript. At least talk about it or write a README-file.

- From Ajax to WebSockets; There's a lot to be said here but in short, I believe that a lot of use-cases can be covered by polling or long-poll. No need to whip out WebSockets just yet. There are of course [libraries][37] that handles degrading - in which case they're super. But don't forget that one can probably move very quickly with a simple abstraction and a poll-implementation.

   [37]: http://socket.io

- A future with mesh; Currently there's the possibility, based on Web RTC and some other technologies, that we could see a more distributed or P2P-based direct use for client side web applications. This is real _future tech_ in web development in my opinion, but we should be aware that the cost and time put in proper JavaScript-development and deeper domain knowledge, will be a great win for those future possibilities.
