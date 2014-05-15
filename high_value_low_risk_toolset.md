Title:  A High Value Low Risk Tool Set  
Author: Olle Törnström  
Date:   2014-05-15

# A High Value Low Risk Tool Set

I think it's fair to say that application development for the web is truly a minefield of change and uncertainty. The cause being technical progress and evolution of both software and hardware. Part of this evolution is of course good, but we must understand that **change will remain constant over time**.

The decisions we make today, and the tools, languages or platforms we use will all be subjected to this concept of change.

In this document I'm going to explain my view on how to manage this situation, and what I believe to be a sound approach to application development in the web eco-system, at this point in time.

## Core values

Before I go into any technical issues I'm going to establish a few basic rules or guiding ethics for development in general, and explain why I find them important.

### 1. End user value over technical agenda

It is fortunately so that most developers already understand and belive in this. More and more the focus is to build _what's best for the user_ and not what's most fitting for the language, tool or platform.

Still I think this is something that's important enough to say again and again. We build _applications_ for people, and _systems_ for machines.

### 2. Agility is responsible resource use

I think _change_ also equally applies to business requirements or opportunities. My view is that we can only react to this, not plan for it. There will always be options but there are [rules for options][CV1] that we can use:

> 1. Options have value.
> 2. Options expire.
> 3. Never commit early unless you know why.

In doing this I believe we can reduce waste and save time, resources and money, even if we are required to iterate and re-evaluate solutions or decisions.

   [CV1]: http://www.infoq.com/articles/real-options-enhance-agility

### 3. Observed usefulness as the main metric of quality

I'm convinced that only end user feedback can give a true indication on whether the application provides the value that is required or not. Establishing channels and methods to gain that feedback is vital.

Technical quality should never be sacrificed but the true metric of quality software is, in my opinion, end user happiness. Our technology must never prevent us from enhancing this metric.

## Leaky abstractions

Another important piece of information, as a background to the technical argumentation in this document, is the issue of [leaky abstractions][LA1], coined as  "The law of leaky abstractions", by Joel Spoolsky in his [blogpost from 2002][LA2]:

> All non-trivial abstractions, to some degree, are leaky.

What it basically says is that a layer of abstraction, almost never fully abstracts away its underlying layer. We have to know or learn the _implementation_ of the abstraction to fully understand the cause and effect of using it. We're never fully  protected or relieved from the technical difficulty it tries to remove.

The reason I'm bringing this up is that, in my experience, this is very much true. Regardless of what library, framework or tool you're using, you are required to know or learn about the underlying technology. You cannot fully remove the requirement of deeper domain knowledge.

To this extent, let's recognize our primary target platform and knowledge domain: HTML, CSS and JavaScript. A deep knowledge of theese technologies will always be required (and to some extent their underlying layers too).

   [LA1]: http://google.com?q=leaky+abstractions
   [LA2]: http://www.joelonsoftware.com/articles/LeakyAbstractions.html

## Progressively enhanced content

Now that I've established some core values and laid out the harsh truth about leaky abstractions, let me introduce the idea of progressive enhancement as a suitable methodology, or rather a general mind set, to manage all this.

Now, it is argued that [progressive enhancement is dead][PE1], but [other][PE2] [people][PE3] [disagree][PE4] - I too disagree. I think the technical implication is still good and that the _idea_ is even greater.

My point is that progressive enhancement allows us to reson about end user value in a very agile way, which suites our core values perfectly. We can always try to deliver **content** as a minimal viable product, and then try to progressively enhance in order to optimize the end user happiness.

_As a side note, please don't confuse content and data. Data is in my opinion not always content. Content is made with the intention of being for humans, suitable to the context in which it is presented._

With regards to our target platform, we should therefore be able to at least create content in a suitable format - HTML.

   [PE1]: http://tomdale.net/2013/09/progressive-enhancement-is-dead/
   [PE2]: http://thatemil.com/blog/2013/07/02/progressive-enhancement-still-not-dead/
   [PE3]: http://jakearchibald.com/2013/progressive-enhancement-still-important/
   [PE4]: http://christianheilmann.com/2012/02/16/stumbling-on-the-escalator/

## Templating

So now we're actually entering into the concrete technical domain. Given the statements above, and our target platform, I think we can agree that our technical value chain or tool set, must at least be able to produce HTML content.

Let's leave out the business logic or controller code for a while and assume we have data that we want to use to produce content. Templating tools and libraries today all fit into a range of either supporting more or less _logic_. By _logic_ we mean, the degree of which we can program or do actual language API calls in the templates themselves.

In my opinion are templating libraries with less logic the better choice.

Once again, this is a dear and [heavily][TP1] [debated][TP2] [issue][TP3]. I think the real smell of too much logic code in the templates is that your're more or less programming across a context and language boundary.

A, perhaps contrived, but obvious example would be JSP/JSTL code that invokes Java methods.

The other side of the spectrum is component-based template solutions, which means there is **no** logic in the templates, at all.

Let's not forget about the separation in the work process. Content design and template authoring may have less to do with core business logic, so the right template solution might allow for value enhancement without changes to the layers _below_.

   [TP1]: http://www.workingsoftware.com.au/page/Your_templating_engine_sucks_and_everything_you_have_ever_written_is_spaghetti_code_yes_you
   [TP2]: http://www.ebaytechblog.com/2012/10/01/the-case-against-logic-less-templates
   [TP3]: http://stackoverflow.com/questions/3896730/whats-the-advantage-of-logic-less-template-such-as-mustache

## Styling content

We have content, now let's make it more enjoyable and valuable to the end user. 

[TODO: Write about CSS: plain vs modern, responsive and modular & bootstrap]

## Enhanced content

[TODO: Describe end user/business value of static duration 50% vs dynamic gauge w. ajax/jquery]

[TODO: Write about JavaScript: responsible development, jquery, widgets, testing, requirejs, promises & libraries vs frameworks]

## Rounding up

[TODO: Write about plain Static-HTML, Sprint MVC, Wicket, JSON-API]

