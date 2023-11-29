---
layout: essay
type: essay
title: "Software Development User Manual: Design Patterns in Software Engineering"
# All dates must be YYYY-MM-DD format!
date: 2023-11-29
published: true
labels:
  - Design Patterns
  - Container/Presentational Pattern
---

<img width="330px" class="rounded pe-4" src="../img/ai3.png">

## Design Patterns
Design patterns play an essential role in software development. They consider frequent problems in developing software and provide general solutions. Just as it sounds, design patterns identify common patterns in software and acknowledge them in a structured form. This organization of frequent issues and occurrences in code allows developers to better understand their work while more easily overcoming potential problems. For instance take the Singleton Pattern, this pattern addresses managing the global state of an application through ensuring that a class can only be instantiated once and accessed globally. An observer pattern allows subscription between certain objects. This pattern consists of an observable and the observers such that when there is an event, the observable notifies the observers. This pattern is useful because it prevents objects from being tightly coupled through establishing that the observable is responsible for event monitoring while observers are responsible for handling received data. Notably there are limitations to these design patterns. With the Singleton pattern, as web development tools continue to adapt this pattern is not as common since in React, there are other state management tools that are used. Considerably, these tools are very similar to Singletons but there are differences. For example, React Context and Redux have a read-only state while Singletons have a mutable state. With the Observer pattern a limitation is the complexity of the observer, if too complex there can be performance issues. Though while there are limitations, generally speaking design patterns can be a powerful tool to enhance the software development process. 

## Design Patterns as User Manuals
Considering the capabilities and uses of design patterns it is evident how they can be seen as a user manual for software development. Design patterns can serve as a guide that can be referenced in a multitude of situations and issues. They provide details, benefits, and limitations for the given situation. Design patterns are like a formalized collection of lessons learned, what works best, and how to best approach various problems in software development. There are even specific patterns to specific frameworks. For instance the patterns addressed before (Singleton and Observer) are javascript patterns. There are also React patterns and Vue patterns to name a few. What this means is that instead of just one general user manual for all web development there are more focused manuals tailored to a project's tools and suites being used. Much like you would not want to use a Toyota user manual for information about a BMW, you want to use the proper patterns that are relevant to the tools being used. With the proper user manual of design patterns, developers can more easily understand and troubleshoot software development. 

In my own experience I have found an essential use of the Container/Presentational Pattern. This pattern is all about enforcing the separation of tasks through separating the view and logic. How this is done is that there will be a presentation component regarding how data is viewed by the user, and then there is the container component which concerns what data is being viewed. For instance, in the implementation of a project where a user will see a list of vendors, their information, and what they sell, I implemented a vendors page and a vendor component. The vendor component outlines what information is shown for a vendor while the vendors page indicates how all of this is viewed. Through adhering to this design pattern I was able to confidently implement an effective version of the desired functionality. 
