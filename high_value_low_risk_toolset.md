Title:  A High Value Low Risk Toolset  
Author: Olle Törnström  
Date:   2014-05-15

# A High Value Low Risk Toolset

I think it's fair to say that application development for the web is truly a minefield of change and uncertainty. The cause being technical progress and evolution of both software and hardware. Part of this evolution is of course good, but we must understand that **change will stay constant over time**.

The decisions we make today, and the tools, languages or platforms we use will all be subjected to this concept of change.

In this document want to explain my view on how to manage this situation, and what I believe to be a sound technical approach for application development in the web eco-system, **at this point in time**.

## Core values

Before I go into any technical issues I'm going to establish a few basic rules or guiding ethics for development in general, and explain why I find them important.

### 1. End user value over technical agenda

It is fortunately so that most developers already understand and belive in this. More and more the focus is to build _what's best for the user_ and not what's most fitting for the language, tool or platform.

Still I think this is something that's important enough to say again and again. We build _applications_ for people, and _systems_ for machines.

### 2. Agility is responsible resource use

I think _change_ also equally applies to business requirements or opportunities. My view is that we can only react to this, not plan for it. There will always be options but there are [rules for options][21] that we can use:

> 1. Options have value.
> 2. Options expire.
> 3. Never commit early unless you know why.

In doing this I believe we can reduce waste and save time, resources and money, even if we are required to iterate and re-evaluate solutions or decisions.

   [21]: http://www.infoq.com/articles/real-options-enhance-agility

### 3. Observed usefulness as the main metric of quality

I'm convinced that only end user feedback can give a true indication on whether the application provides the value that is required or not. Establishing channels and methods to gain that feedback is vital.

Technical quality should never be sacrificed but the true metric of quality software is, in my opinion, end user happiness. Our technology must never prevent us from enhancing this metric.

## Leaky abstractions

Another important piece of information, as a background to the technical argumentation in this document, is the issue of [leaky abstractions][31], coined as  "The law of leaky abstractions", by Joel Spoolsky in his [blogpost from 2002][32]:

> All non-trivial abstractions, to some degree, are leaky.

What is basically says is that a layer of abstraction, almost never fully abstracts away its underlying layer. We have to know or learn the _implementation_ of the abstraction to fully understand the cause and effect of using it. We're never fully  protected or relieved from the technical difficulty it tries to remove.

   [31]: http://google.com?q=leaky+abstractions
   [32]: http://www.joelonsoftware.com/articles/LeakyAbstractions.html

