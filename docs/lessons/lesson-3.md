---
title: Lesson 3
parent: Lessons
nav_order: 3
---

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