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
- [ ] Is obvious behavior implemented?
- [ ] Does the code behave correctly at the boundaries?
- [ ] Is the code at the correct level of abstraction?
- [ ] Are base classes independent of their derivatives?
- [ ] Is the code free from artificial coupling?
- [ ] Is the code free from envy of another object's scope and abilities?
- [ ] Is the code as expressive as possible?
- [ ] Does the code adhere to the Single Responsibility Principle?

### Comments
- [ ] Is the code free from comments that contain inappropriate information?
- [ ] Is the code free from obsolete comments?
- [ ] Is the code free from comments that will quickly become obsolete?
- [ ] Is the code free from redundant comments?
- [ ] Are all of the comments written well?
- [ ] Is the code free from commented out code?

### Naming
#### Have You Avoided...
- [ ] ...names that are misleading?
- [ ] ...names with similar meanings?
- [ ] ...names that are different by only one or two characters?
- [ ] ...names that sound similar?
- [ ] ...names that use numerals?
- [ ] ...names intentionally misspelled to make them shorter?
- [ ] ...names that are commonly misspelled in English?
- [ ] ...names that conflict with standard library-routine or with pre-defined variable names?
- [ ] ...totally arbitrary names?
- [ ] ...hard to read characters?

### Variables
- [ ] Are variables defined closed to where they are used?
- [ ] Does the code initialize variables as they're declared, if possible?
- [ ] Does the variable have the smallest scope possible?
- [ ] Are variables reinitialized properly in code that's executed repeatedly?
- [ ] Are you using explanatory variables? Are the names descriptive?
- [ ] Does the variable name reflect the appropriate level of abstraction?
- [ ] Is the variable name unambiguous?
- [ ] Does the variable name avoid including type and scope information?
- [ ] Does each variable have one and only one purpose?

### Conditionals
- [ ] Are conditionals encapsulated in a function or variable?
- [ ] Are conditionals expressed as positives?
- [ ] Are boundary conditions encapsulated in a function?

### Functions
- [ ] Are the functions defined closed to where they are used?
- [ ] Does the function name says what it does?
- [ ] Does the function do only one thing?
- [ ] Does the function descend only one level of abstraction?
- [ ] Does the function name reflect the appropriate level of abstraction?
- [ ] Is the function name unambiguous?
- [ ] Does the function name avoid including type and scope information?

### Classes

#### Abstraction
- [ ] Does the class have a central purpose?
- [ ] Is the class well-named, and does the name describe its' central purpose?
- [ ] Does the class's interface present a consistent abstraction?
- [ ] Does the class's interface make obvious how the class should get used?
- [ ] Is the class's interface abstract enough that you don't have to think about how its services are implemented?
- [ ] Are the class's services complete enough that other classes don't have to meddle with its internal data?
- [ ] Has unrelated information been moved out of the class?
- [ ] Are you unable to split the class into subclasses?
- [ ] Has the integrity of the class's interface been preserved?

#### Encapsulation
- [ ] Does the class minimize accessibility to its members?
- [ ] Does the class avoid exposing member data?
- [ ] Does the class hide its implementation details from other classes as much as possible?
- [ ] Does the class avoid making assumptions about its users, including its derived classes?
- [ ] Is the class independent of other classes? Is it loosely coupled?

#### Inheritance
- [ ] Is inheritance used only to model "is a" relationships?
- [ ] Do child classes adhere to the Liskov Substitution Principle?
- [ ] Do child classes avoid overriding non-overridable routines?
- [ ] Are common interfaces, data, and behavior as high as possible in the inheritance tree?
- [ ] Are inheritance trees fairly shallow?
- [ ] Are all data members in the base class private rather than protected?

#### Misc.
- [ ] Does the class contain about seven data members or fewer?
- [ ] Does the class minimize direct and indirect routing calls to other classes?
- [ ] Does the class collaborate with other classes only to the extent absolutely necessary?
- [ ] Is all member data initialized in the constructor?
- [ ] Is the class designed to be used as deep copies rather than shallow copies unless there's a measured reason to create shallow copies?

### Organization
- [ ] Does the code read well from top to bottom?
- [ ] Is the code free from dead or unused code?
- [ ] Is the code consistent with existing style and formatting?
- [ ] Is the code free from clutter?
- [ ] Are dependent modules of code physically close together?
- [ ] Is the code free from magic numbers and magic strings?
- [ ] Are configuration options as high a level as possible in the abstraction?
- [ ] Does the code adhere to DRY (Don't Repeat Yourself)? Is the code free from duplicate code?

### Tests
- [ ] Are there sufficient tests for functionality?
- [ ] Are there trivial tests?
- [ ] Are all boundary conditions being tested for?
- [ ] Is test execution fast?

