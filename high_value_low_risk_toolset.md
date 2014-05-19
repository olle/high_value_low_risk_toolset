Title:  A High Value Low Risk Tool Set  
Author: Olle Törnström  
Date:   2014-05-15

A High Value Low Risk Tool Set
==============================

I think it's fair to say that application development for the web is truly a minefield of change and uncertainty. The cause being technical progress and evolution of both software and hardware. This process of change is of course good, but I think we must realize, and use as a base for our resoning, that **change will remain constant over time**.

In this document will try to explain my view on how to manage this situation, and describe what I believe to be a sound technicalapproach to application development in the web eco-system, **at this point in time**.

_Please note: anything stated in this document, except when referred to (linked) as an external reference, is my very personal subjective view, even if I'm not starting every sentence with "I think..." or "I believe...". You have been warned._

Core values
-----------

Before I go into any technical issues I'm going to establish a few basic rules or guiding ethics for development in general, and explain why I find them important, and why I think they apply to our analysis.

### 1. End user value over technical agenda

Lucklily most developers already understand this. More and more the focus is to build _what's best for the user_ and not what's most fitting for the language, tool or platform. We build applications for people, and systems for machines. The distinction here is that we must not put the technical elegance _before_ the value our application provides to the actual person using it.

### 2. Agility is responsible resource use

The same principle of constant change, as mentioned in the introduction, applies to opportunities, bussiness requirements and constraints. We can't plan for theese unexpected events, we can only react to them. The actions we take are based on options, but there are [rules for options][1] that we can apply to our process:

   [1]: http://www.infoq.com/articles/real-options-enhance-agility

> 1. Options have value.
> 2. Options expire.
> 3. Never commit early unless you know why.

In doing this, we strive to reduce waste and create the best possible value from the options we have, based on the information we have at that point in time. This is how we save resource, time and money. But we must be ready to iterate and re-evaluate a solution again at a later time.

### 3. Observed usefulness as the main metric of quality

I'm convinced that only end user feedback can give a true indication on whether an application provides the value that is required or not. Establishing channels and methods to gain that feedback is vital. Technical quality should never be sacrificed but the true metric of quality software is simply end user happiness. Being able to hear and understand how the end users feel is a part of understing this quality metric. Improvements that lead to happier end users must be have priority.

### 4. Technical craftsmanship

Observing best practicies and using idiomatic and _modern_ development methodoligies will act as a protection against declining quality. Solutions should be implemented at the correct, but commonly understandable, complexity level.

Leaky abstractions
------------------

We can't make any qualified arguments for or against any given tool set without taking the issue of [leaky abstractions][2], coined as "The law of leaky abstractions" by Joel Spoolsky in his [blogpost from 2002][3], into account. It states the following:

   [2]: http://google.com?q=leaky+abstractions
   [3]: http://www.joelonsoftware.com/articles/LeakyAbstractions.html

> All non-trivial abstractions, to some degree, are leaky.

What it says is that any layer of abstraction, never fully abstracts away its underlying layer. We have to know or learn the _implementation_ of the abstraction to understand the cause and effect of using it. You basically can't remove the requirement of deeper domain knowledge.

Regardless of what framework, tool or library we use for web application devlopment, we have to have deep knowledge about HTML, CSS and JavaScript (among other things).

The ubiquitous platform
-----------------------

I'm convinced that we must view the target platform technologies, HTML, CSS and JavaScript, as true knowledge requirements. Based on what we've mentioned earlier, those are the abstractions and implementations that we have to be able to understand and explain, regardless of what tool set we whish to use.

For example, an ever recurring issue when using JavaScript widgets is the fallacy in thinking that using them does not require one to understand how they work.

Progressively enhanced content
------------------------------

Progressive enhancement guides us to build features that adapt their richness based on the context where they're used. Now, it is argued that [progressive enhancement is dead][4], but [other][5] [people][6] [disagree][7]. I think it's the best possible match for our core values as it allows us to reson about end user value in a very iterative and agile way.

   [4]: http://tomdale.net/2013/09/progressive-enhancement-is-dead/
   [5]: http://thatemil.com/blog/2013/07/02/progressive-enhancement-still-not-dead/
   [6]: http://jakearchibald.com/2013/progressive-enhancement-still-important/
   [7]: http://christianheilmann.com/2012/02/16/stumbling-on-the-escalator/

For example say that we can provide someting valuable to the end user by simply creating content - a simple HTML-page. That content could then later be enhanced, if and only if it's required in order to make the application more efficient or enjoyable to the end user.

_Remember that content and data are not necessarily the same thing. Content is made with the intention of being for humans, and therefore having a higher value to the end user._

The if and how progressive enhancement is supported by some specific tool or technology in the tool set is a very important issue.

Vertical cuts
-------------

[TODO]
- Applications should be cut where it makes sense
- Different technologies for different problems
- Enhancement can be kept narrow
- Re-use services and evolve an eco-system - `sites` are dead

Templating
----------

Two important issues with templating are how they support the work process and secondly whether they technically allow more or less _logic_ or freedom of expression.

On the first issue, we should recognize that template technologies supporting a decoupled content development process, allowing art direction, layout, design and implementation to be done separately from the business logic, provides different options than those that require a more coupled process.

To be fair, it's always possible to separate pure HTML layout development, but we know by experience that some frameworks or libraries are better than other in allowing faster integration of HTML and business logics. For example based on which resources are required or how long it takes to start-up or reload pages during layout work.

The second issue is the implications of a template librarys ability to support more or less _logic_. By _logic_ we mean, the degree of which we can program or do actual language API calls in the templates themselves. This is a dear and [heavily][8] [debated][9] [issue][10]. I think we can agree that a template language that allows too much freedom often leads to code that blurs the border between business and presentation logic - which is bad.

Less logic in templates is better.

[TODO]

- Client vs server-side templating

   [8]: http://www.workingsoftware.com.au/page/Your_templating_engine_sucks_and_everything_you_have_ever_written_is_spaghetti_code_yes_you
   [9]: http://www.ebaytechblog.com/2012/10/01/the-case-against-logic-less-templates
   [10]: http://stackoverflow.com/questions/3896730/whats-the-advantage-of-logic-less-template-such-as-mustache

Styling
-------

Apart from the prevous statements about core values, leaky abstractions and progressive enhancement, which absolutely apply to styling or CSS, we should also be aware of the following.

[TODO]

- Core values apply
- Frameworks and libraries might create lock-ins, but are big wins for reuse
- Pre-processors, what they bring but what they don't take away
- Modular is reusable without the library buy-in
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
