---
layout: post
title: "A modern web frontend vision"
category: posts
---

We are living exciting times when it comes to web technology we are really close to having for instance:

* Functional programming for the frontend.
* Close to native performance for webapps.

Let's check each bullet closer.

Functional programming for the frontend
=======================================

Functional programming is becoming a hot topic, and we can see how a myriad of languages that have been living for longer than the languages we use are becoming now important. 

Scala, Clojure, and Haskell are good evidence, but even better are classic imperative languages getting functional features. 
Ruby, Groovy, Javascript's lodash and underscore. And finally... Java 8 is getting "lambda blocks" or functions as first class citizens.

Why is this happening?
----------------------

Multicore architectures are the hardware's guys bet, even my 200 dollar phone has two cores in it.
Software guys need tools to use those multicore architectures. Functional seems to be a good bet, it makes concurrency easier, sometimes even automatic (Clojure's map function is always multicore wheter you like it or not).

Ok, but why is this relevant for the frontend?
----------------------------------------------

Node.js had a vision, what if instead of writing wrappers between language constructs we could communicate transparently the frontend and the backend? And not only that, but having the same programming paradigms, syntax and semantics available wherever you are?

Javascript for the backend was the answer, we could use Google's fine V8. It seems to be working... LinkedIn, Microsoft, Yahoo among other companies have found a good place for Node.js.

But couldn't it be the other way around? Isn't it possible to use a backend, nicely engineered language for the backend? (Not to say that javascript is a bad language, I actually love it, but let's face it.. there are a ton of ways of using it's bad parts).

Well, there is. There have been some efforts, like Google's DART, Coffeescript, Clojurescript. 
Let's talk about clojurescript, a Lisp for the frontend.


Really, a Lisp? In the 21st century?
------------------------------------

Yep, and it is really nice, imagine the power of lisp's simplicity for the frontend, even better imagine you can jump seemlessly between frontend and backend code which is clojure. Nice, huh?

Well, that's Clojurescript, and it's working. Relevance, a software development firm is using a complete Clojure stack for it's development, and it has some pretty big customers, IBM, BestBuy, BBC, livingsocial. Granted, they also use rails, but there's a lot of clojure going in there. They are pretty commited, having some Clojure's core commiters, they have their own clojure web framework among other things...

So, how does Clojurescript work? It has to be javascript in the end, so the clojurescript guys decided to use Google's Closure compiler. 

But... things are not perfect, there are claims that the ui starts to slow down when you add things like angularjs to the combo. And it is completely normal, stuff like this happens when you have a zillion layers.

But... worry not... there's some hope.

Close to native performance for webapps
=======================================

Performance is still a big problem when it comes to webapps, even though the javascript interpreters are making a huge effort to improve things.
Week after week we se how Firefox and Chrome get faster and faster, and there's some new kids around.

asm.js
------

Have heard about asm.js? It's a VERY cool idea, and it involves compiling javascript into native code.

How do you get that? The idea was to make javascript simpler, by defining a highly optimizable subset of it. Once you have a ver simple subset of javascript you can invest a lot of work into compiling it into native code.

Seems too wild to be true? OdinMonkey will be released in a few weeks with Firefox 22, it already supports asm.js.

Google seems to be interested in giving support to asm.js in it's V8. They already made some optimizations without compiling to native the got a 2x performance boost in asm.js compatible code.

What does all of that mean for me?
----------------------------------

Just have a look:

<iframe width="560" height="315" src="http://www.youtube.com/embed/XsyogXtyU9o" frameborder="0" allowfullscreen></iframe>


The integrated vision
=====================

Let's tie the knots, just imagine this:

* You write your webapp in clojure entirely, the frontend is Clojurescript, the backend is JVM Clojure.
* The frontend is compiled into asm.js compatible code. 
* Google's closure compiler further improves your code, generating asm.js compatible code too.
* You get an extremely fast application, the backend runs in a modern JVM, the performance is close to native, you need not worry about concurrency, clojure handles it automatically. You frontend is asm.js compatible code, the app feels like it is a native app.

What is needed to make this possible?

* asm.js needs to mature a bit, the specification is still a draft, maybe Mozilla's move with Firefox will make developers and companies interested.
* We need more support for asm.js, it developers start using it apps will be much faster in Firefox than in Chrome, if Chrome embraces this, maybe Microsoft might make something to support it.
* The clojure guys might change their compiler in order to generate only asm.js compatible code.
* Google guys might tune the Closure compiler, to get even better asm.js code.

We aren't that far, and this is only a vision, the name of the technologies, and who implements them might be different. In the end, I imagine a world where you can use whatever device you want, a tablet, a phone, a computer. Any OS: Linux, MacOS, Windows, and you get an amazing user experience NO MATTER WHAT CHOICE YOU MAKE!

Freedom is the important thing here, let's work for that!


