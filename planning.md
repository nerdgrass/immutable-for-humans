# Immutable for Humans Planning

## Project Goal
The goal of this project will be to create a reference for Immutable.js that functions both as layman's documentation as well as resources for self-education in the how and why of using immutable collections in Javascript.

## Approach
The approach to this project is one of inclusivity - as a self-taught front-end developer, approaching immutable data structures with out prior knowledge of their historical implementations. IE, grab a friend who already knows functional programming and immutable data, because its freaking **rough** trying to dive in by yourself.

Thankfully, I had some very friendly and patient coworkers who put up with an art school dropout trying to jump from a cursory understanding of [MVC] (http://stackoverflow.com/questions/2626803/mvc-model-view-controller-can-it-be-explained-in-simple-terms) to understanding [the sorcery of LISP] (WWW.EXAMPLE.GOES/HERE). 

Not everybody has awesome coworkers willing to teach them the dark arts of mixing FP and JS. So, I'm going to attempt to inscribe my learnings and organize them in such a way that anybody that writes Javascript finds Immutable.js and its associated concepts approachable. I'll probably screw this up, so I'm making this open source. If all goes well, maybe somebody somewhere will find this useful.

## Structure
- **Human Docs**
  * Code Documentation
    * An exact copy of the Immutable.js docs, but with explanations in layman's terms.
    * Code is written in ES5, ES6, and ES7. Switch between (IE: react-dnd docs)
  * Concept Documentation
    * Concepts (like recursion, iterables, or types) are documented and cited when used, just like code.
- **Tutorials**
    * Blog-length essays going over how to do things. Like:
      * Comparing immutable objects vs comparing POJOs
      * Benefits of Immutable in performance
      * Benefits of Immutable re: state tracking
      * Benefits of Immutable in development (or lack thereof)
      * How it dovetails into Flux
    * Tutorial: How to build Immutable.js for humans
      * Blog-sized tutorials that show how to build a digital book that people can edit, hosted on github, eventually w/ pdf converter api integration
      * GH used for hosting because its cheap and effective
      * Creates a cool tool for people to self publish
- **Code**
  * All examples from Tutorials in various forms. Should have examples in ES5, ES6, & ES7. 
  * Should have React + Flux, Reflux, Redux, etc examples. 
  * Should have Immutable for Humans book & editor source code
