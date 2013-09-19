---
layout: post
title: "GTK + Chromium + Clojure + ClojureScript"
category: posts
---

It's been a while since I wrote a desktop app. I have an idea involving something called "FIEL" (you personal digital signature in México), and I've read some really good things about C++11, so I decided it was a good idea to try and build something with those two.

There are a few GUI frameworks available, but to be honest I don't really grok GTK, QT 5 looks nice but there's all those IDEs and and XMLs and I'm not really an IDE person.

After a little research I found the [Chromium Embedded Framework](https://code.google.com/p/chromiumembedded/)
sounds pretty good, there are some good points:

* **Ubiqutous frontend technologies** You can just use what you've probably been using the most for frontend: CSS, JS and HTML
* **JavaScript interoperability** You can write you JS functions with native C++ and export them, using Chrome's V8 API and call JS from C++. So you can open files, connect to databases, download things or do whatever you want with the host OS.
* **Supports some neat things** Like WebRTC! 

Tha bad side:

I'm complecting things together, but that's OK. I really want to do this.

But behold! There's more complecting waiting for us.

For this app I have a strange use case, I need to be able to call some custom Java classes to sign and encrypt, yeah I could use openssl, but eventually someone is going to ask me to add those JAR files.

So, I [embedded a JVM!](https://github.com/iamedu/firmavio/blob/master/frontend/java.cc)

Ok so let's take a step back, and check where we are:

* We have JS for the frontend
* We have Java for the backend (Not really, I don't mean to use Java for anything else than SSL, well.. maybe the scripting API would be a nice fit for something)
* We have C++ as duct tape

I know what you are thinking... everyone's favorite platform runs on top of the first two... Yes, I'm talking about clojure!

So... it doesn't hurt if I write clojurescript instead of Javascript and Clojure instead of Java, right?

At least it sounds interesting, I'm half way through it but it seems that it's going to work.

Let me show you:

![Firmavio starting](../../images/firmavio1.png)

It does nothing, but I think it is a good starting point for every desktop app that I write from now on.

BTW you can check the code [here](https://github.com/iamedu/firmavio)
