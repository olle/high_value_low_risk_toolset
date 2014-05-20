Title:  A High Value Low Risk Tool Set  
Author: Olle Törnström  
Date:   2014-05-15

A High Value Low Risk Tool Set
==============================

I think it's fair to say that application development for the web is truly a minefield of change and uncertainty. The cause being technical progress and evolution of both software and hardware. This process of change is of course good, and I think we must accept that **change will remain constant over time**.

In this document I'm going to explain my view on how to manage this situation, and describe what I believe is a sound technical approach to application development in the web eco-system, **at this point in time**.

_Please note: anything stated in this document, except when referred to (linked) as an external reference, is my very personal subjective view, even if I'm not starting every sentence with "I think..." or "I believe..."._

Core values
-----------

Before I go into any technical details I'm going to establish a few basic rules or guiding ethics for development in general, and explain why I find them important, and how they apply to my analysis.

### 1. End user value over technical agenda

Luckily most developers already understand this. More and more the focus is to build _what's best for the user_ and not what's most fitting for the language, library, tool or platform. We build applications for people, and systems for machines. The distinction is that we can't put technical elegance _before_ the value our application provides to the person using it.

### 2. Agility is responsible resource use

Change, in my opinion, as mentioned in the introduction, applies equally to business opportunities, requirements and constraints. We can't plan for theese events, we can only react to them. The actions we take are based on some current options, but there are [rules for options][1] that we can apply to our process:

   [1]: http://www.infoq.com/articles/real-options-enhance-agility

> 1. Options have value.
> 2. Options expire.
> 3. Never commit early unless you know why.

In doing this, we strive to reduce waste and create the best possible value from the options we have, based on the information we have at that point in time. This is how we can save resources, time and money. But we must be ready to iterate and re-evaluate a solution again at a later time. That's enhancing value, in an iterative manner.

### 3. Observed usefulness as the metric of quality

I'm convinced that only end user feedback can give a true indication on whether an application provides the value that is required or not. Establishing channels and methods to gain that feedback is vital. Technical quality should never be sacrificed, but the true metric of quality software is simply end user happiness. Being able to understand how the end users feels is a part of understing this quality metric. Improvements that lead to happier end users must have priority.

### 4. Technical craftsmanship

Observing best practicies and using idiomatic and _modern_ development methodoligies will act as a protection against failure to deliver quality. Solutions should be implemented at the correct complexity level, never too simple or too complex.

Leaky abstractions
------------------

I'm convinced that we can't make any qualified argument about technology without taking the issue of [leaky abstractions][2], coined as _"The law of leaky abstractions"_ by Joel Spoolsky in his [blogpost from 2002][3], into account. It states:

   [2]: http://google.com?q=leaky+abstractions
   [3]: http://www.joelonsoftware.com/articles/LeakyAbstractions.html

> All non-trivial abstractions, to some degree, are leaky.

What it means is that any layer of abstraction, never fully abstracts away its underlying layer. We have to know or learn the _implementation_ of the abstraction to understand the cause and effect of using it. You basically can't remove the requirement of deeper domain knowledge.

So for us this means, that regardless of what framework, tool or library we use for web application devlopment, we have to have a deep knowledge and understanding about HTML, CSS and JavaScript (among other things).

The ubiquitous platform
-----------------------

I'm convinced that we must view the target platform technologies, HTML, CSS and JavaScript, as true knowledge requirements. Based on what we've mentioned earlier, those are the abstractions and implementations that we have to be able to understand and explain, regardless of what tool set we whish to use.

For example, an ever recurring issue when using JavaScript widgets is the fallacy in thinking that using them does not require one to understand how they work. This often leads to higher technical debt to pay off - bugs that suddenly remove _more_ end user value than the widget actually provided to begin with.

Progressively enhanced content
------------------------------

Progressive enhancement guides us to build features that adapt their richness based on the context where they're used. Now, it is argued that [progressive enhancement is dead][4], but [other][5] [people][6] [disagree][7]. I would also disagree. Progressive enhancement is great way for us to reson about end user value in an iterative and agile way. It matches our core values perfectly.

   [4]: http://tomdale.net/2013/09/progressive-enhancement-is-dead/
   [5]: http://thatemil.com/blog/2013/07/02/progressive-enhancement-still-not-dead/
   [6]: http://jakearchibald.com/2013/progressive-enhancement-still-important/
   [7]: http://christianheilmann.com/2012/02/16/stumbling-on-the-escalator/

For example say that we can provide someting valuable to the end user by simply creating content - a simple HTML-page. That content could then later be enhanced, if and only if it's required in order to make the application more efficient or enjoyable to the end user. We can choose to execute our options at the last possible time and are not required to commit.

_Remember that content and data are not necessarily the same thing. Content is made with the intention of being for humans, and therefore having a higher value to the end user._

What's important to us is to understand and take into account how suitable some technology or tool is to the concept of progressive enhancement.

Vertical cuts
-------------

It comes with a _buzz word warning_ to mention "vertical features or services", but sadly it's a bit of an overlooked possibility. Committing to vertically cut features, in the context of web application development, can give us many more options to adapt the technology to the solution we're building, and not the other way around.

There are many way that we can support this separation in the deployment packaging: separate VM's, processes or contexts running inside an application server. This is not something new, it's just not used that way very often.

If one part of a web application simply is posting and viewing data, and the other part is a highly dynamic client side application, the sensible thing to do, would be to make the cut with regards to the technical stack. One of these two apps does not require anything but plain old server pages, but the other one require massive green threads, web sockets and the hottest JavaScript library out there.

Separate them. Make the cut. It's risk management if you ask me. If we take this route, the issue of finding a technical stack becomes less of a single decision, and more a collection of recommendationa, where the application will dictate the choice of the best possible stack for it's requirements.

Templating
----------

Using a template engine for content creation is very much a work process management decision. It can provide the team with an option to separate the art direction, layout and design implementation from core business technology or domain modeling. For some this is the only way to ensure high velocity iterations, where web developers won't have to wait for full server reloads or code that needs to compile. So we can understand that the right templating solution is empowering. The question is how much power do we want to give this technical layer?

Templates languages all have a property of being more or less expressive, allowing the user to actually _program_ with it. On one side of the spectrum there are template solutions that cross over their context boundary, and actually program in the programming language of their "host" e.g. JSP/JSTL or PHP. Moving towards the other end of the spectrum we have less logic, less conditionals, only structuring and output. Or the most extreme, component based templates, where there's no logic at all.

This is a dear and [heavily][8] [debated][9] [issue][10]. I think we can agree that a template language that allows too much freedom often leads to code that blurs the border between business and presentation logic. Languages with less logic will often require pre-massaging of the data before it can be rendered into the view, which basically puts view-code directly next to the business code (but not mixing).

   [8]: http://www.workingsoftware.com.au/page/Your_templating_engine_sucks_and_everything_you_have_ever_written_is_spaghetti_code_yes_you
   [9]: http://www.ebaytechblog.com/2012/10/01/the-case-against-logic-less-templates
   [10]: http://stackoverflow.com/questions/3896730/whats-the-advantage-of-logic-less-template-such-as-mustache

I think less logic templating is the better choice. My view is that template languages without good constraints will basically self-deteriorate into a mess through the use of ugly hacks, all with the best of intentions.

Another thing to consider regarding templating is what benefits there are from choosing a technology that can be used both on the server side as well as on the client side. I don't have any deeper experience here, but my guess is that this means making a compromise. There are some [interesting][11] [articles][12] on the matter, and I would suggest digging deeper into the matter.

   [11]: http://engineering.linkedin.com/frontend/leaving-jsps-dust-moving-linkedin-dustjs-client-side-templates
   [12]: http://engineering.linkedin.com/frontend/client-side-templating-throwdown-mustache-handlebars-dustjs-and-more

Styling
-------

With the risk of sounding like a broken record - again, my previous statements about core values, leaky abstractions and progressive enhancement apply to styling or CSS too. Added to that, I think it we have to recognized that CSS authoring (or development) is very much a practiced craft. There are of course specs, but boy let me tell you, did the browsers get them wrong. At least they choose to interpret them differently.

First, please understand that there is a [great][13] [body][14] of [work][15] on the [matter][16], and that CSS also requires [design and structure][17], just as any other part of your application.

   [13]: http://smacss.com/book/
   [14]: http://www.stubbornella.org/content/2010/07/01/top-5-mistakes-of-massive-css/
   [15]: http://viget.com/inspire/css-squareoff
   [16]: http://www.hagenburger.net/BLOG/Modular-CSS-Class-Names.html
   [17]: http://www.sitepoint.com/css-architectures-scalable-and-modular-approaches/

I like the modular approach, and I've seen (and created) enough CSS-mess to believe in the need for some better methods. Understanding how loose coupling can reduce the volume of CSS code is real eye-opener. There is basically no real _need_ for tools in styling, just well crafted and well though out CSS.

### CSS pre-processors

So at this point it's good to direct the attention to pre-processors. If we **first** apply modular styling and loose coupling of HTML and CSS, then it's ok to add pre-processing, as icing on the cake.

The power that variables, mixins and functions bring to CSS authoring is all good. It makes it easy for us to create re-usable themes and removes some issues with plain CSS. Colors, typography and grid-dimentions can for example be declared as common constraints for all stylings.

Which pre-processor to use is just another religous matter, in my opinion. But I think it's more important to evaluate how the tool fits the build process. Is it easy to use? Will it require runtime resources in production? And so on.

### CSS-frameworks

So there's a big promise typically made by [styling][18] [frameworks][19] out there - they will solve the problem of styling for you... in one great, free to use, very much hyped, and cool, oh did I mention it's open source? ...all in buy-in.

   [18]: http://getbootstrap.com
   [19]: http://foundation.zurb.com
   
Here are some people with [opinions][20] [against][21], [using][22] one of the popular frameworks. I think you should read up on their views, and other discussions you might find on the issue.

   [20]: http://blog.idyllic-software.com/why-we-dont-use-twitter-bootstrap/
   [21]: http://halanstevens.com/blog/bootstrap-youre-doing-it-wrong/
   [22]: http://fourkitchens.com/blog/2013/10/09/you-dont-need-bootstrap
   
My point of view is that we should not buy in to the framework until we can se the benefit. We want to commit only when we understand why. Any given feature in one of the frameworks will most certainly be available as a small, separate, widget or library that does only that thing - perhaps even better.

Frameworks provide a high benefit in the re-use they offer, with the risk that an early buy-in brings.

### Responsive design

[TODO]
- Responsive is progressive enhancement, but it comes at a cost - weight
- Adaptive graphics, SVG, embedded and generated Sprite-Maps, no bitmaps

Enhanced content
----------------

[TODO]

- Enhancing static to dynamic
- Entry-level widgets/plug-ins jQuery, with standards
- Frameworks are full buy-ins, libraries are more composable
- Responsible development: modular, test-driven, require, promises, open to optimize
- From Ajax to WebSockets, client-server vs. mesh

## References

[TODO]

- Static HTML creation, key features
- Going from data -> information -> content, semantic HTMLs
- Dynamic pages with Java+Templating, thymeleaf, freemarker, velocity etc
- Spring MVC, the feature of different frontends
- Component vs req/resp based frameworks
- Wicket
- Resources and APIs vs server-web-stack
- RESTful and APIs only is not the answer, it's not progressive
