---
title: Home
layout: home
nav_order: 1
---

# Technical Contributor Program
### Introduction

The Technical Contributor Program is an initiative by the TEI Technical Council to provide mentoring on how to edit and maintain the TEI P5 Guidelines and Stylesheets repositories to interested members of the TEI community. 

Upon completing the program, Technical Contributors will:

* Have a deeper understanding of the TEI Guidelines and Stylesheets source code.

* Know how to use GitHub, Git, Docker, and the command line (bash).

* Be able to edit the Guidelines and Stylesheets.

* Be able to build and test the TEI Guidelines and schemas.

* Know how to address GitHub issues. 

* Be able to create and merge Pull Requests.

### Procedures
The steps for the various procedures outlined in the lessons are documented in the TEI Technical Contributor Program Guide.

### Practicalities
* What does it entail to be a Technical Contributor and how do I become one?

    * Open to anyone in TEI community that is interested in learning about and contributing to the TEI Guidelines
    * Attend some Technical Council meetings
    * Participate in mentoring sessions with Technical Council members

### Outline
#### Lesson 1: Introduction to the TEI Guidelines
Introduction to how the TEI Guidelines are organised:
* Introduction to what modules, attribute classes, element classes, macros, and datatypes are:
 
    * [Elements](https://tei-c.org/release/doc/tei-p5-doc/en/html/REF-ELEMENTS.html)
    * [Attributes](https://tei-c.org/release/doc/tei-p5-doc/en/html/REF-ATTS.html)
    * [Attribute Classes](https://tei-c.org/release/doc/tei-p5-doc/en/html/REF-CLASSES-ATTS.html)
    * [Model Classes](https://tei-c.org/release/doc/tei-p5-doc/en/html/REF-CLASSES-MODEL.html)
    * [Datatypes and Other Macros](https://tei-c.org/release/doc/tei-p5-doc/en/html/REF-MACROS.html)

#### Lesson 2: Introduction to the TEI Technical Council and the TEI Repositories
* Introduction to the TEIC repositories:
  
    * [TEI](https://github.com/TEIC/TEI)
    * [Stylesheets](https://github.com/TEIC/Stylesheets)
    * [Documentation](https://github.com/TEIC/Documentation)
    * [Website](https://github.com/TEIC/website)
* Exercise: Finding the source files for the [TEI Guidelines](https://tei-c.org/release/doc/tei-p5-doc/en/html/index.html) in the [TEI](https://github.com/TEIC/TEI) repository

#### Lesson 3: Overview of the TEI Guidelines repository
* Introduction to the TEI Guidelines Prose and Specs files in [Source](https://github.com/TEIC/TEI/tree/dev/P5/Source).
   * The Guidelines folder. See the **Organisation of the Guideline Chapters** section in [TCW20](https://tei-c.org/documentation/tcw20/).
       * Overview of the Guidelines folder
       * Overview of the naming convention for Guidelines chapters. See the **Naming conventions section** in [TCW20](https://tei-c.org/documentation/tcw20/)).
    * The Specifications folder. See the **Organisation of the Specifications** section in [TCW20](https://tei-c.org/documentation/tcw20/).
       * Overview of the specification folder
       * Overview of the layout of specification files i.e. gloss, description, remarks etc.
            * Explain when a `<gloss>` should be provided.
            * Every `<gloss>`,  `<desc>`, and `<remarks>` should have both `@xml:lang` and `@versionDate` to facilitate translation.
            * If there are any `<gloss>`, `<desc>`, or `<remarks>` elements, there should be one with `@xml:lang="en"`, and it should be first; furthermore no two should have the same value of `@xml:lang`.
    * TEI [issues](https://github.com/TEIC/TEI/issues)
    * TEI [pull requests](https://github.com/TEIC/TEI/pulls)
 
#### Lesson 4: Introduction to the Stylesheets repository
* Why does the TEI repository have a utilities folder and XSLT?
* Overview of why there is a [Stylesheets](https://github.com/TEIC/Stylesheets) repository.
* Stylesheet [issues](https://github.com/TEIC/Stylesheets/issues) 
* Stylesheet [pull requests](https://github.com/TEIC/Stylesheets/pulls)
 
#### Lesson 5: Introduction to the Website repository
* Overview of the [website](https://github.com/TEIC/website) repository
* Introduction to Markdown
* TEI [website issues](https://github.com/TEIC/website/issues)
* TEI [website pull requests](https://github.com/TEIC/website/pulls)
 
#### Lesson 6: Introduction to Git and GitHub Authentication
* [Introduction to Shell and Git](https://slides.com/elisabeshero-bondar/shell-git-nav/) by Elisa Beshero-Bondar
* Cloning the [TEI](https://github.com/TEIC/TEI), [Stylesheets](https://github.com/TEIC/Stylesheets), and [website](https://github.com/TEIC/website) repositories 
    * Using password-protected SSH keys (see [TCW32](https://tei-c.org/documentation/tcw32/))
* GitHub Authentication
    * Generating and adding SSH keys or tokens for GitHub

#### Lesson 7: Using the Command Line, Git, and the TEIC GitHub repositories
* Working on the command line 
    * [Tutorial](https://swcarpentry.github.io/shell-novice/) on working on the command line
    * The Programming Historian on working with [Bash](https://programminghistorian.org/en/lessons/intro-to-bash)
    * See tutorials from [TCW32](https://tei-c.org/documentation/tcw32/)
        * [Command Line Tutorial](https://www.learnenough.com/command-line-tutorial)
        * [How to install and use Git Bash on Windows 10](https://www.howtogeek.com/249966/how-to-install-and-use-the-linux-bash-shell-on-windows-10/)
* Navigating to the TEIC repositories using the command line
* Introduction to common git commands:
    * David Birnbaum’s [Introduction to working with Git](http://dh.obdurodon.org/git/)
    * [Git CLI cheatsheet](https://gist.github.com/hofmannsven/6814451)  
* Exercises:
    * Updating your local instance of the TEIC repos 
    * Checking the status of your local instance of the TEIC repos
    * Checking the history of changes via your local instance of the TEIC repos

#### Lesson 8: Introduction to using Docker for the TEIC repositories 
See [TCW32: Building and Testing the Guidelines and Stylesheets](https://tei-c.org/documentation/tcw32/).
* Introduction to Docker
* Installing Docker
* Starting your Docker instance from the command line
    * See the Docker Commands Quick Reference Guide for TCW32.
* Building and testing the Guidelines using Docker
* Updating your Docker instance

#### Lesson 9: Editing the Guidelines
See the **Making a Change to the Guidelines** section in [TCW20](https://tei-c.org/documentation/tcw20/)
* Editing the Guidelines using your chosen editor.
* Create a new branch using git
* Commit changes using git
* Push changes to the TEIC repository

#### Lesson 10: Creating and updating a Pull Request
* Creating a pull request
* Updating the PR on GitHub
* Pushing commits to a PR
* Removing commits from a PR
* Merging dev into a PR 
* Resolving conflicts


#### Lesson 11: Merging local uncommitted changes to a new branch
What to do if you forget to create a branch before you start making changes.


#### Lesson 12: Adding a fork from a remote repository
Explanation of why it might be necessary to fetch remote repositories

#### Lesson 13: Introduction to XPath and XSLT
* What is XPath and XSLT? 
    * [XPath and XSLT-workshop at TEI 2026](https://teic.github.io/XSLT-workshop/) (Elisa, Martina, Trish, and Lauren)
    * [Processing XML-workshop at DSHI 2025](https://ebeshero.github.io/UpTransformation/index.html) (Elisa and David Birnbaum)
    * [Introduction to XSLT for Digital Humanists](https://www.wwp.neu.edu/outreach/seminars/uvic_xslt_2017/index.html) (Syd & Martin)
* Using XPath/XSLT with the TEI

#### Lesson 14: Customisation
* How to create a customisation file. 
* How writing a customisation is essential for testing effectively.
* See the [TBE](https://www.teibyexample.org/exist/examples/TBED08v00.htm) section on customization. 

#### Lesson 15: Testing
See [TCW32](https://tei-c.org/documentation/tcw32/)
* Overview of the Test suite 
* How to use the Test suite
* How to resolve diff errors using the command line or the Oxygen diff Files app 

<!--#### Lesson 16: Updating the content model of TEI elements 
How to update the content models of TEI elements.

#### Lesson 17: Deprecating TEI elements
How to deprecate TEI elements.-->

#### Resources



  


