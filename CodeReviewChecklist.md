# Code Review Checklist

## Before We Get Started
### What I'm trying to do
Firstly, I've often found that the rules and best practices that I try to reference during code review are scattered all over the place. I've created this checklist so that I can link to different best practices and code smells when reviewing code. During code reviews, I don't want to say that a line of code needs to get changed without having resources behind the change request.

Secondly, while I really love the checklists listed out in Code Complete and Clean Code, the information and checks aren't always current, as the most recent editions of the books have been printed in 2004 and 2008 respectively. I wanted to synthesize these checklists together for a cleaner and more current list.

Finally, I wanted to create a checklist for myself so that I could print out the checklist or reference the checklist on a second monitor during code reviews.

### What I'm not doing
#### Using this checklist to critique language specific syntax
#### Using this checklist as a replacement to a linter or style guid.
Computers are very good at checking to see if brackets line up. Computers are very good at checking dangling whitespace. Computers aren't very good at telling you if a comment is appropriate or if your variable names are week. While the checklists below do contain some generic style checks, this checklist will not cover items such as 'end of file must be denoted by an empty space'. Those checks should by handled by linters such as [ESLint](https://eslint.org), [PMD](https://pmd.github.io/), or [checkstyle](https://checkstyle.sourceforge.io/).

### Resources
Below are the resources that I've used when building out these checklists
- [Code Complete](https://www.amazon.com/Code-Complete-Practical-Handbook-Construction/dp/0735619670/ref=sr_1_3?keywords=code+complete&qid=1563384307&s=gateway&sr=8-3)
- [Clean Code](https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882/ref=sr_1_4?keywords=code+complete&qid=1563384345&s=gateway&sr=8-4)
- [The Clean Coder](https://www.amazon.com/gp/product/0137081073/ref=dbs_a_def_rwt_bibl_vppi_i2)

## Checklists
The checks and the questions that this list present are expressed as positives. This is so that a checklist full of checks can represent that the code passes review.
### General Code Health
- [ ] Is obvious behavior implemented? (G2)
- [ ] Does the code behave correctly at the boundaries? (G3)
- [ ] Does the code adhere to DRY (Don't Repeat Yourself)? Is the code free from duplicate code? (G5)
- [ ] Is the code at the correct level of abstraction? (G6)
- [ ] Are base classes independent of their derivatives? (G7)
- [ ] Is there an appropriate level of information? (G8)
- [ ] Is the code free from dead or unused code? (G9)
- [ ] Is the code consistent with existing style and formatting? (G11)
- [ ] Is the code free from clutter? (G12)
- [ ] Is the code free from artificial coupling? (G13)
- [ ] Is the code free from envy of another object's scope and abilities? (G14)
- [ ] Is the code as expressive as possible? (G16)
- [ ] Does the code adhere to the Single Responsibility Principle (G17)
- [ ] Are dependent modules of code physically close together? (G22)
- [ ] Is the code free from magic numbers and magic strings? (G25)
- [ ] Are configuration options as high a level as possible in the abstraction? (G35)
### Comments
- [ ] Is the code free from comments that contain inappropriate information? (C1)
- [ ] Is the code free from obsolete comments? (C2)
- [ ] Is the code free from comments that will quickly become obsolete? (C3)
- [ ] Is the code free from redundant comments? (C3)
- [ ] Are all of the comments written well? (C4)
- [ ] Is the code free from commented out code? (C5)
### Variables
- [ ] Are variables defined closed to where they are used? (G10)
- [ ] Are you using explanatory variables? Are the names descriptive? (G19, N1)
- [ ] Does the variable name reflect the appropriate level of abstraction? (N2)
- [ ] Is the variable name unambiguous? (N4)
- [ ] Does the variable name avoid including type and scope information? (N6)
### Functions
- [ ] Are the functions defined closed to where they are used? (G10)
- [ ] Does the function name says what it does? (G20)
- [ ] Does the function do only one thing? (G30)
- [ ] Does the function descend only one level of abstraction? (G34)
- [ ] Does the function name reflect the appropriate level of abstraction? (N2)
- [ ] Is the function name unambiguous? (N4)
- [ ] Does the function name avoid including type and scope information? (N6)
### Conditionals
- [ ] Are conditionals encapsulated in a function or variable? (G28)
- [ ] Are conditionals expressed as positives? (G29)
- [ ] Are boundary conditions encapsulated in a function? (G33)
### Tests
- [ ] Are there sufficient tests for functionality? (T1)
- [ ] Are there trivial tests? (T3)
- [ ] Are all boundary conditions being tested for? (T5)
- [ ] Is test execution fast? (T9)

