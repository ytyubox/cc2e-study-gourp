# cc2e Checklists

| index | name | page|
| --| ------------ | --|
| 01| Requirements | 42|
| 02| Architecture | 54|
| 03| Upstream Prerequisites | 59|
| 04| Major Construction Practices | 69|
| 05| Design in Construction | 122|
| 06| Class Quality | 157|
| 07| High-Quality Routines | 185|
| 08| Defensive Programming | 211|
| 09| The Pseudocode Programming Process | 233|
| 10| General Considerations In Using Data | 257|
| 11| Naming Variables | 288|
| 12| Fundamental Data | 316|
| 13| Considerations in Using Unusual Data Types | 343|
| 14| Organizing Straight-Line Code | 353|
| 15| Using Conditionals | 365|
| 16| Loops | 388|
| 17| Unusual Control Structures | 410|
| 18| Table-Driven Methods | 429 |
| 19| Control-Structure Issues | 459|
| 20| A Quality-Assurance Plan | 476|
| 21| Effective Pair Programming | 484|
| 22| Effective Inspections | 491|
| 23| Test Cases | 532|
| 24| Debugging Reminders | 559|
| 25| Reasons to Refactor | 570|
| 26| Summary of Refactorings | 577|
| 27| Refactoring Safely | 584|
| 28| Code-Tuning Strategies | 607|
| 29| Code-Tuning Techniques | 642|
| 30| Configuration Management | 669|
| 31| Integration | 707|
| 32| Programming Tools | 724|
| 33| Layout | 773|
| 34| Self-Documenting Code | 780|
| 35| Good Commenting Technique | 816|

## Checklist: Architecture

Here’s a list of issues that a good architecture should address. The list isn’t intended to be a comprehensive guide to architecture but to be a pragmatic way of evaluating the nutritional content of what you get at the programmer’s end of the software food chain. Use this checklist as a starting point for your own checklist. As with the requirements checklist, if you’re working on an informal project, you’ll find some items that you don’t even need to think about. If you’re working on a larger project, most of the items will be useful.
Specific Architectural Topics

- [ ]  Is the overall organization of the program clear, including a good architec- tural overview and justification?
- [ ]  Are major building blocks well defined, including their areas of responsi- bility and their interfaces to other building blocks?
- [ ]  Are all the functions listed in the requirements covered sensibly, by neither too many nor too few building blocks?
- [ ]  Are the most critical classes described and justified?
- [ ]  Is the data design described and justified?
- [ ]  Is the database organization and content specified?
- [ ]  Are all key business rules identified and their impact on the system described?
- [ ]  Is a strategy for the user interface design described?
- [ ]  Is the user interface modularized so that changes in it won’t affect the rest
of the program?
- [ ]  Is a strategy for handling I/O described and justified?
- [ ]  Are resource-use estimates and a strategy for resource management described and justified for scarce resources like threads, database connec- tions, handles, network bandwidth, and so on?
- [ ]  Are the architecture’s security requirements described?
- [ ]  Does the architecture set space and speed budgets for each class, sub-
system, or functionality area?
- [ ]  Does the architecture describe how scalability will be achieved?
- [ ]  Does the architecture address interoperability?
- [ ]  Is a strategy for internationalization/localization described?
- [ ]  Is a coherent error-handling strategy provided?
- [ ]  Is the approach to fault tolerance defined (if any is needed)?
3.6 Amount of Time to Spend on Upstream Prerequisites 55
- [ ]  Has technical feasibility of all parts of the system been established?
- [ ]  Is an approach to overengineering specified?
- [ ]  Are necessary buy-vs.-build decisions included?
- [ ]  Does the architecture describe how reused code will be made to conform to other architectural objectives?
- [ ]  Is the architecture designed to accommodate likely changes? General Architectural Quality
- [ ]  Does the architecture account for all the requirements?
- [ ]  Is any part overarchitected or underarchitected? Are expectations in this
area set out explicitly?
- [ ]  Does the whole architecture hang together conceptually?
- [ ]  Is the top-level design independent of the machine and language that will be used to implement it?
- [ ]  Are the motivations for all major decisions provided?
- [ ]  Are you, as a programmer who will implement the system, comfortable with the architecture?

## Checklist: Major Construction Practices

Coding

- [ ]  Have you defined how much design will be done up front and how much will be done at the keyboard, while the code is being written?
- [ ]  Have you defined coding conventions for names, comments, and layout?
- [ ]  Have you defined specific coding practices that are implied by the architec- ture, such as how error conditions will be handled, how security will be addressed, what conventions will be used for class interfaces, what stan- dards will apply to reused code, how much to consider performance while coding, and so on?
- [ ]  Have you identified your location on the technology wave and adjusted your approach to match? If necessary, have you identified how you will program into the language rather than being limited by programming in it?
Teamwork
- [ ]  Have you defined an integration procedure—that is, have you defined the specific steps a programmer must go through before checking code into the master sources?
- [ ]  Will programmers program in pairs, or individually, or some combination of the two?
cc2e.com/0496
70 Chapter 4: Key Construction Decisions
Quality Assurance
- [ ]  Will programmers write test cases for their code before writing the code itself?
- [ ]  Will programmers write unit tests for their code regardless of whether they write them first or last?
- [ ]  Will programmers step through their code in the debugger before they check it in?
- [ ]  Will programmers integration-test their code before they check it in?
- [ ]  Will programmers review or inspect each other’s code?
Tools
- [ ]  Have you selected a revision control tool?
- [ ]  Have you selected a language and language version or compiler version?
- [ ]  Have you selected a framework such as J2EE or Microsoft .NET or explic- itly decided not to use a framework?
- [ ]  Have you decided whether to allow use of nonstandard language features?
- [ ]  Have you identified and acquired other tools you’ll be using—editor, refac- toring tool, debugger, test framework, syntax checker, and so on?

## CHECKLIST: Design in Construction

Design Practices

- [ ]  Have you iterated, selecting the best of several attempts rather than the first attempt?
- [ ]  Have you tried decomposing the system in several different ways to see which way will work best?
- [ ]  Have you approached the design problem both from the top down and from the bottom up?
- [ ]  Have you prototyped risky or unfamiliar parts of the system, creating the absolute minimum amount of throwaway code needed to answer specific questions?
- [ ]  Has your design been reviewed, formally or informally, by others?
- [ ]  Have you driven the design to the point that its implementation seems
obvious?
- [ ]  Have you captured your design work using an appropriate technique such as a Wiki, e-mail, flip charts, digital photography, UML, CRC cards, or comments in the code itself?
Design Goals
- [ ]  Does the design adequately address issues that were identified and deferred at the architectural level?
- [ ]  Is the design stratified into layers?
- [ ]  Are you satisfied with the way the program has been decomposed into
subsystems, packages, and classes?
- [ ]  Are you satisfied with the way the classes have been decomposed into routines?
- [ ]  Are classes designed for minimal interaction with each other?
cc2e.com/0527
Key Points
■ Software’s Primary Technical Imperative is managing complexity. This is greatly aided by a design focus on simplicity.
■ Simplicity is achieved in two general ways: minimizing the amount of essential complexity that anyone’s brain has to deal with at any one time, and keeping accidental complexity from proliferating needlessly.
■ Design is heuristic. Dogmatic adherence to any single methodology hurts cre- ativity and hurts your programs.
■ Good design is iterative; the more design possibilities you try, the better your final design will be.
■ Information hiding is a particularly valuable concept. Asking “What should I hide?” settles many difficult design issues.
■ Lots of useful, interesting information on design is available outside this book. The perspectives presented here are just the tip of the iceberg.
Key Points 123
- [ ]  Are classes and subsystems designed so that you can use them in other systems?
- [ ]  Will the program be easy to maintain?
- [ ]  Is the design lean? Are all of its parts strictly necessary?
- [ ]  Does the design use standard techniques and avoid exotic, hard-to-under- stand elements?
- [ ]  Overall, does the design help minimize both accidental and essential complexity?

## CHECKLIST: Class Quality

Abstract Data Types

- [ ]  Have you thought of the classes in your program as abstract data types and evaluated their interfaces from that point of view?
Abstraction
- [ ]  Does the class have a central purpose?
- [ ]  Is the class well named, and does its name describe its central purpose?
- [ ]  Does the class’s interface present a consistent abstraction?
- [ ]  Does the class’s interface make obvious how you should use the class?
- [ ]  Is the class’s interface abstract enough that you don’t have to think about how its services are implemented? Can you treat the class as a black box?
- [ ]  Are the class’s services complete enough that other classes don’t have to meddle with its internal data?
- [ ]  Has unrelated information been moved out of the class?
- [ ]  Have you thought about subdividing the class into component classes,
and have you subdivided it as much as you can?
- [ ]  Are you preserving the integrity of the class’s interface as you modify the class?
cc2e.com/0672
Cross-Reference This is a checklist of considerations about the quality of the class. For a list of the steps used to build a class, see the checklist “The Pseudocode Programming Process” in Chapter 9, page 233.
158 Chapter 6: Working Classes
Encapsulation
- [ ]  Does the class minimize accessibility to its members?
- [ ]  Does the class avoid exposing member data?
- [ ]  Does the class hide its implementation details from other classes as much as the programming language permits?
- [ ]  Does the class avoid making assumptions about its users, including its derived classes?
- [ ]  Is the class independent of other classes? Is it loosely coupled?
Inheritance
- [ ]  Is inheritance used only to model “is a” relationships—that is, do derived classes adhere to the Liskov Substitution Principle?
- [ ]  Does the class documentation describe the inheritance strategy?
- [ ]  Do derived classes avoid “overriding” non-overridable routines?
- [ ]  Are common interfaces, data, and behavior as high as possible in the inheritance tree?
- [ ]  Are inheritance trees fairly shallow?
- [ ]  Are all data members in the base class private rather than protected?
Other Implementation Issues
- [ ]  Does the class contain about seven data members or fewer?
- [ ]  Does the class minimize direct and indirect routine calls to other classes?
- [ ]  Does the class collaborate with other classes only to the extent absolutely necessary?
- [ ]  Is all member data initialized in the constructor?
- [ ]  Is the class designed to be used as deep copies rather than shallow copies
unless there’s a measured reason to create shallow copies?
Language-Specific Issues
- [ ]  Have you investigated the language-specific issues for classes in your spe- cific programming language?

## CHECKLIST: High-Quality Routines

Big-Picture Issues

- [ ]  Is the reason for creating the routine sufficient?
- [ ]  Have all parts of the routine that would benefit from being put into rou-
tines of their own been put into routines of their own?
- [ ]  Is the routine’s name a strong, clear verb-plus-object name for a procedure or a description of the return value for a function?
- [ ]  Does the routine’s name describe everything the routine does?
- [ ]  Have you established naming conventions for common operations?
- [ ]  Does the routine have strong, functional cohesion—doing one and only one thing and doing it well?
- [ ]  Do the routines have loose coupling—are the routine’s connections to other routines small, intimate, visible, and flexible?
- [ ]  Is the length of the routine determined naturally by its function and logic, rather than by an artificial coding standard?
Parameter-Passing Issues
- [ ]  Does the routine’s parameter list, taken as a whole, present a consistent interface abstraction?
- [ ]  Are the routine’s parameters in a sensible order, including matching the order of parameters in similar routines?
- [ ]  Are interface assumptions documented?
- [ ]  Does the routine have seven or fewer parameters?
- [ ]  Is each input parameter used?
- [ ]  Is each output parameter used?
- [ ]  Does the routine avoid using input parameters as working variables?
- [ ]  If the routine is a function, does it return a valid value under all possible circumstances?

## CHECKLIST: Defensive Programming

General

- [ ]  Does the routine protect itself from bad input data?
- [ ]  Have you used assertions to document assumptions, including precondi-
tions and postconditions?
- [ ]  Have assertions been used only to document conditions that should never occur?
- [ ]  Does the architecture or high-level design specify a specific set of error- handling techniques?
- [ ]  Does the architecture or high-level design specify whether error handling should favor robustness or correctness?
- [ ]  Have barricades been created to contain the damaging effect of errors and reduce the amount of code that has to be concerned about error process- ing?
- [ ]  Have debugging aids been used in the code?
- [ ]  Have debugging aids been installed in such a way that they can be acti-
vated or deactivated without a great deal of fuss?
- [ ]  Is the amount of defensive programming code appropriate—neither too much nor too little?
- [ ]  Have you used offensive-programming techniques to make errors difficult to overlook during development?
Exceptions
- [ ]  Has your project defined a standardized approach to exception handling?
- [ ]  Have you considered alternatives to using an exception?
- [ ]  Is the error handled locally rather than throwing a nonlocal exception, if possible?
- [ ]  Does the code avoid throwing exceptions in constructors and destructors?
- [ ]  Are all exceptions at the appropriate levels of abstraction for the routines
that throw them?
- [ ]  Does each exception include all relevant exception background informa- tion?
- [ ]  Is the code free of empty catch blocks? (Or if an empty catch block truly is appropriate, is it documented?)
cc2e.com/0868
212 Chapter 8: Defensive Programming
Security Issues
- [ ]  Does the code that checks for bad input data check for attempted buffer overflows, SQL injection, HTML injection, integer overflows, and other malicious inputs?
- [ ]  Are all error-return codes checked?
- [ ]  Are all exceptions caught?
- [ ]  Do error messages avoid providing information that would help an attacker break into the system?

## CHECKLIST: The Pseudocode Programming Process

- [ ]  Have you checked that the prerequisites have been satisfied?
- [ ]  Have you defined the problem that the class will solve?
- [ ]  Is the high-level design clear enough to give the class and each of its rou- tines a good name?
- [ ]  Have you thought about how to test the class and each of its routines?
- [ ]  Have you thought about efficiency mainly in terms of stable interfaces and readable implementations or mainly in terms of meeting resource and speed budgets?
- [ ]  Have you checked the standard libraries and other code libraries for appli- cable routines or components?
- [ ]  Have you checked reference books for helpful algorithms?
cc2e.com/0943
Cross-Reference The point of this list is to check whether you followed a good set of steps to create a routine. For a checklist that focuses on the quality of the routine itself, see the “High- Quality Routines” checklist in Chapter 7, page 185.
234 Chapter 9: The Pseudocode Programming Process
- [ ]  Have you designed each routine by using detailed pseudocode?
- [ ]  Have you mentally checked the pseudocode? Is it easy to understand?
- [ ]  Have you paid attention to warnings that would send you back to design (use of global data, operations that seem better suited to another class or another routine, and so on)?
- [ ]  Did you translate the pseudocode to code accurately?
- [ ]  Did you apply the PPP recursively, breaking routines into smaller routines
when needed?
- [ ]  Did you document assumptions as you made them?
- [ ]  Did you remove comments that turned out to be redundant?
- [ ]  Have you chosen the best of several iterations, rather than merely stop- ping after your first iteration?
- [ ]  Do you thoroughly understand your code? Is it easy to understand?

## CHECKLIST: General Considerations In Using Data

Initializing Variables

- [ ]  Does each routine check input parameters for validity?
- [ ]  Does the code declare variables close to where they’re first used?
- [ ]  Does the code initialize variables as they’re declared, if possible?
- [ ]  Does the code initialize variables close to where they’re first used, if it isn’t possible to declare and initialize them at the same time?
- [ ]  Are counters and accumulators initialized properly and, if necessary, rein- itialized each time they are used?
- [ ]  Are variables reinitialized properly in code that’s executed repeatedly?
- [ ]  Does the code compile with no warnings from the compiler? (And have
you turned on all the available warnings?)
- [ ]  If your language uses implicit declarations, have you compensated for the problems they cause?
Other General Issues in Using Data
- [ ]  Do all variables have the smallest scope possible?
- [ ]  Are references to variables as close together as possible, both from each
reference to a variable to the next reference and in total live time?
- [ ]  Do control structures correspond to the data types?

- [ ]  Are all the declared variables being used?
- [ ]  Are all variables bound at appropriate times—that is, are you striking a con- scious balance between the flexibility of late binding and the increased complexity associated with late binding?
- [ ]  Does each variable have one and only one purpose?
- [ ]  Is each variable’s meaning explicit, with no hidden meanings?

## cc2e.com/1191

CHECKLIST: Naming Variables
General Naming Considerations

- [ ]  Does the name fully and accurately describe what the variable represents?
- [ ]  Does the name refer to the real-world problem rather than to the program-
ming-language solution?
- [ ]  Is the name long enough that you don’t have to puzzle it out?
- [ ]  Are computed-value qualifiers, if any, at the end of the name?
- [ ]  Does the name use Count or Index instead of Num?
Naming Specific Kinds of Data
- [ ]  Are loop index names meaningful (something other than i, j, or k if the loop is more than one or two lines long or is nested)?
- [ ]  Have all “temporary” variables been renamed to something more mean- ingful?
- [ ]  Are boolean variables named so that their meanings when they’re true are clear?
- [ ]  Do enumerated-type names include a prefix or suffix that indicates the cat- egory—for example, Color_for Color_Red, Color_Green, Color_Blue, and so on?
- [ ]  Are named constants named for the abstract entities they represent rather than the numbers they refer to?
Naming Conventions
- [ ]  Does the convention distinguish among local, class, and global data?
- [ ]  Does the convention distinguish among type names, named constants,
enumerated types, and variables?
- [ ]  Does the convention identify input-only parameters to routines in lan- guages that don’t enforce them?
- [ ]  Is the convention as compatible as possible with standard conventions for the language?
- [ ]  Are names formatted for readability? Short Names
- [ ]  Does the code use long names (unless it’s necessary to use short ones)?
- [ ]  Does the code avoid abbreviations that save only one character?
- [ ]  Are all words abbreviated consistently?
Key Points
■ Good variable names are a key element of program readability. Specific kinds of variables such as loop indexes and status variables require specific considerations.
■ Names should be as specific as possible. Names that are vague enough or gen- eral enough to be used for more than one purpose are usually bad names.
■ Naming conventions distinguish among local, class, and global data. They dis- tinguish among type names, named constants, enumerated types, and variables.
■ Regardless of the kind of project you’re working on, you should adopt a variable naming convention. The kind of convention you adopt depends on the size of your program and the number of people working on it.
■ Abbreviations are rarely needed with modern programming languages. If you do use abbreviations, keep track of abbreviations in a project dictionary or use the standardized prefixes approach.
■ Code is read far more times than it is written. Be sure that the names you choose favor read-time convenience over write-time convenience.
Key Points 289
- [ ]  Are the names pronounceable?
- [ ]  Are names that could be misread or mispronounced avoided?
- [ ]  Are short names documented in translation tables?
Common Naming Problems: Have You Avoided...
- [ ]  ...names that are misleading?
- [ ]  ...names with similar meanings?
- [ ]  ...names that are different by only one or two characters?
- [ ]  ...names that sound similar?
- [ ]  ...names that use numerals?
- [ ]  ...names intentionally misspelled to make them shorter?
- [ ]  ...names that are commonly misspelled in English?
- [ ]  ...names that conflict with standard library routine names or with pre- defined variable names?
- [ ]  ...totally arbitrary names?
- [ ]  ...hard-to-read characters?

## CHECKLIST: Fundamental Data

Numbers in General

- [ ]  Does the code avoid magic numbers?
- [ ]  Does the code anticipate divide-by-zero errors?
- [ ]  Are type conversions obvious?
- [ ]  If variables with two different types are used in the same expression, will the expression be evaluated as you intend it to be?
- [ ]  Does the code avoid mixed-type comparisons?
- [ ]  Does the program compile with no warnings?
Integers
- [ ]  Do expressions that use integer division work the way they’re meant to?
- [ ]  Do integer expressions avoid integer-overflow problems?
Floating-Point Numbers
- [ ]  Does the code avoid additions and subtractions on numbers with greatly different magnitudes?
- [ ]  Does the code systematically prevent rounding errors?
- [ ]  Does the code avoid comparing floating-point numbers for equality?
Characters and Strings
- [ ]  Does the code avoid magic characters and strings?
- [ ]  Are references to strings free of off-by-one errors?
cc2e.com/1206
Cross-Reference For a checklist that applies to general data issues rather than to issues with specific types of data, see the check- list on page 257 in Chapter 10, “General Issues in Using Variables.” For a checklist of considerations in naming varieties, see the checklist on page 288 in Chapter 11, “The Power of Variable Names.”
12.9 Creating Your Own Types (Type Aliasing) 317
- [ ]  Does C code treat string pointers and character arrays differently?
- [ ]  Does C code follow the convention of declaring strings to be length CON-
STANT+1?
- [ ]  Does C code use arrays of characters rather than pointers, when appropriate?
- [ ]  Does C code initialize strings to NULLs to avoid endless strings?
- [ ]  Does C code use strncpy() rather than strcpy()? And strncat() and strncmp()?
Boolean Variables
- [ ]  Does the program use additional boolean variables to document condi- tional tests?
- [ ]  Does the program use additional boolean variables to simplify conditional tests?
Enumerated Types
- [ ]  Does the program use enumerated types instead of named constants for their improved readability, reliability, and modifiability?
- [ ]  Does the program use enumerated types instead of boolean variables when a variable’s use cannot be completely captured with true and false?
- [ ]  Do tests using enumerated types test for invalid values?
- [ ]  Is the first entry in an enumerated type reserved for “invalid”?
Named Constants
- [ ]  Does the program use named constants for data declarations and loop limits rather than magic numbers?
- [ ]  Have named constants been used consistently—not used as named con- stants in some places and as literals in others?
Arrays
- [ ]  Are all array indexes within the bounds of the array?
- [ ]  Are array references free of off-by-one errors?
- [ ]  Are all subscripts on multidimensional arrays in the correct order?
- [ ]  In nested loops, is the correct variable used as the array subscript, avoid- ing loop-index cross-talk?

318 Chapter 12: Fundamental Data Types
Creating Types

- [ ]  Does the program use a different type for each kind of data that might change?
- [ ]  Are type names oriented toward the real-world entities the types represent rather than toward programming-language types?
- [ ]  Are the type names descriptive enough to help document data declarations?
- [ ]  Have you avoided redefining predefined types?
- [ ]  Have you considered creating a new class rather than simply redefining a type?

## CHECKLIST: Considerations in Using Unusual Data Types

Structures

- [ ]  Have you used structures instead of naked variables to organize and manipulate groups of related data?
- [ ]  Have you considered creating a class as an alternative to using a structure?
Global Data
- [ ]  Are all variables local or of class scope unless they absolutely need to be global?
- [ ]  Do variable naming conventions differentiate among local, class, and glo- bal data?
- [ ]  Are all global variables documented?
cc2e.com/1392
344 Chapter 13: Unusual Data Types
- [ ]  Is the code free of pseudoglobal data—mammoth objects containing a mishmash of data that’s passed to every routine?
- [ ]  Are access routines used instead of global data?
- [ ]  Are access routines and data organized into classes?
- [ ]  Do access routines provide a level of abstraction beyond the underlying data type implementations?
- [ ]  Are all related access routines at the same level of abstraction? Pointers
- [ ]  Are pointer operations isolated in routines?
- [ ]  Are pointer references valid, or could the pointer be dangling?
- [ ]  Does the code check pointers for validity before using them?
- [ ]  Is the variable that the pointer references checked for validity before it’s used?
- [ ]  Are pointers set to null after they’re freed?
- [ ]  Does the code use all the pointer variables needed for the sake of readabil-
ity?
- [ ]  Are pointers in linked lists freed in the right order?
- [ ]  Does the program allocate a reserve parachute of memory so that it can shut down gracefully if it runs out of memory?
- [ ]  Are pointers used only as a last resort, when no other method is available?

## cc2e.com/1472

Key Points
Figure 14-2 If the code is organized poorly, boxes drawn around related sections overlap.
Once you’ve grouped related statements, you might find that they’re strongly related and have no meaningful relationship to the statements that precede or follow them. In such a case, you might want to refactor the strongly related statements into their own routine.
Key Points 353

Checklist: Organizing Straight-Line Code

- [ ]  Does the code make dependencies among statements obvious?
- [ ]  Do the names of routines make dependencies obvious?
- [ ]  Do parameters to routines make dependencies obvious?
- [ ]  Do comments describe any dependencies that would otherwise be unclear?
- [ ]  Have housekeeping variables been used to check for sequential dependen- cies in critical sections of code?
- [ ]  Does the code read from top to bottom?
- [ ]  Are related statements grouped together?
- [ ]  Have relatively independent groups of statements been moved into their own routines?

## CHECKLIST: Using Conditionals cc2e.com/1545

if-then Statements

- [ ]  Is the nominal path through the code clear?
- [ ]  Do if-then tests branch correctly on equality?
- [ ]  Is the else clause present and documented?
- [ ]  Is the else clause correct?
- [ ]  Are the if and else clauses used correctly—not reversed?
- [ ]  Does the normal case follow the if rather than the else?
if-then-else-if Chains
- [ ]  Are complicated tests encapsulated in boolean function calls?
- [ ]  Are the most common cases tested first?
- [ ]  Are all cases covered?
- [ ]  Is the if-then-else-if chain the best implementation—better than a case statement?
case Statements
- [ ]  Are cases ordered meaningfully?
- [ ]  Are the actions for each case simple—calling other routines if necessary?
- [ ]  Does the case statement test a real variable, not a phony one that’s made
up solely to use and abuse the case statement?
- [ ]  Is the use of the default clause legitimate?
- [ ]  Is the default clause used to detect and report unexpected cases?
- [ ]  In C, C++, or Java, does the end of each case have a break?

## CHECKLIST: Loops

Loop Selection and Creation

- [ ]  Is a while loop used instead of a for loop, if appropriate?
- [ ]  Was the loop created from the inside out?
Entering the Loop
- [ ]  Is the loop entered from the top?
- [ ]  Is initialization code directly before the loop?
- [ ]  If the loop is an infinite loop or an event loop, is it constructed cleanly rather than using a kludge such as for i = 1 to 9999?
- [ ]  If the loop is a C++, C, or Java for loop, is the loop header reserved for loop- control code?
Inside the Loop
- [ ]  Does the loop use { and } or their equivalent to enclose the loop body and prevent problems arising from improper modifications?
- [ ]  Does the loop body have something in it? Is it nonempty?
- [ ]  Are housekeeping chores grouped, at either the beginning or the end of
the loop?
- [ ]  Does the loop perform one and only one function, as a well-defined rou- tine does?
- [ ]  Is the loop short enough to view all at once?
- [ ]  Is the loop nested to three levels or less?
- [ ]  Have long loop contents been moved into their own routine?
- [ ]  If the loop is long, is it especially clear?
cc2e.com/1616
Key Points
■ Loops are complicated. Keeping them simple helps readers of your code.
■ Techniques for keeping loops simple include avoiding exotic kinds of loops, minimizing nesting, making entries and exits clear, and keeping housekeeping code in one place.
■ Loop indexes are subjected to a great deal of abuse. Name them clearly, and use them for only one purpose.
■ Think through the loop carefully to verify that it operates normally under each case and terminates under all possible conditions.
Key Points 389
Loop Indexes
- [ ]  If the loop is a for loop, does the code inside it avoid monkeying with the loop index?
- [ ]  Is a variable used to save important loop-index values rather than using the loop index outside the loop?
- [ ]  Is the loop index an ordinal type or an enumerated type—not floating- point?
- [ ]  Does the loop index have a meaningful name?
- [ ]  Does the loop avoid index cross-talk?
Exiting the Loop
- [ ]  Does the loop end under all possible conditions?
- [ ]  Does the loop use safety counters—if you’ve instituted a safety-counter
standard?
- [ ]  Is the loop’s termination condition obvious?
- [ ]  If break or continue are used, are they correct?

## CHECKLIST: Table-Driven Methods

- [ ]  Have you considered table-driven methods as an alternative to compli- cated logic?
- [ ]  Have you considered table-driven methods as an alternative to compli- cated inheritance structures?
- [ ]  Have you considered storing the table’s data externally and reading it at run time so that the data can be modified without changing code?
- [ ]  If the table cannot be accessed directly via a straightforward array index (as in the age example), have you put the access-key calculation into a rou- tine rather than duplicating the index calculation in the code?
cc2e.com/1872
430 Chapter 18: Table-Driven Methods Key Points
■ Tables provide an alternative to complicated logic and inheritance structures. If you find that you’re confused by a program’s logic or inheritance tree, ask your- self whether you could simplify by using a lookup table.
■ One key consideration in using a table is deciding how to access the table. You can access tables by using direct access, indexed access, or stair-step access.
■ Another key consideration in using a table is deciding what exactly to put into the table.

## cc2e.com/1985

The McCabe measure of complexity isn’t the only sound measure, but it’s the measure most discussed in computing literature and it’s especially helpful when you’re think- ing about control flow. Other measures include the amount of data used, the number of nesting levels in control constructs, the number of lines of code, the number of lines between successive references to variables (“span”), the number of lines that a variable is in use (“live time”), and the amount of input and output. Some researchers have developed composite metrics based on combinations of these simpler ones.
19.6 Control Structures and Complexity 459
CHECKLIST: Control-Structure Issues

- [ ]  Do expressions use true and false rather than 1 and 0?
- [ ]  Are boolean values compared to true and false implicitly?
- [ ]  Are numeric values compared to their test values explicitly?
- [ ]  Have expressions been simplified by the addition of new boolean vari- ables and the use of boolean functions and decision tables?
- [ ]  Are boolean expressions stated positively?
- [ ]  Do pairs of braces balance?
- [ ]  Are braces used everywhere they’re needed for clarity?
- [ ]  Are logical expressions fully parenthesized?
- [ ]  Have tests been written in number-line order?
- [ ]  Do Java tests uses a.equals(b) style instead of a == b when appropriate?
- [ ]  Are null statements obvious?
- [ ]  Have nested statements been simplified by retesting part of the condi- tional, converting to if-then-else or case statements, moving nested code into its own routine, converting to a more object-oriented design, or have they been improved in some other way?
- [ ]  If a routine has a decision count of more than 10, is there a good reason for not redesigning it?
460 Chapter 19: General Control Issues Key Points
■ Making boolean expressions simple and readable contributes substantially to the quality of your code.
■ Deep nesting makes a routine hard to understand. Fortunately, you can avoid it relatively easily.
■ Structured programming is a simple idea that is still relevant: you can build any program out of a combination of sequences, selections, and iterations.
■ Minimizing complexity is a key to writing high-quality code.

## Chapter 20: The Software-Quality Landscape cc2e.com/2043

CHECKLIST: A Quality-Assurance Plan

- [ ]  Have you identified specific quality characteristics that are important to your project?
- [ ]  Have you made others aware of the project’s quality objectives?
- [ ]  Have you differentiated between external and internal quality characteristics?
- [ ]  Have you thought about the ways in which some characteristics might compete with or complement others?
- [ ]  Does your project call for the use of several different error-detection tech- niques suited to finding several different kinds of errors?
- [ ]  Does your project include a plan to take steps to assure software quality during each stage of software development?
- [ ]  Is the quality measured in some way so that you can tell whether it’s improving or degrading?
- [ ]  Does management understand that quality assurance incurs additional costs up front in order to save costs later?

## cc2e.com/2192 CHECKLIST: Effective Pair Programming

- [ ]  Do you have a coding standard so that pair programmers stay focused on programming rather than on philosophical coding-style discussions?
- [ ]  Are both partners participating actively?
- [ ]  Are you avoiding pair programming everything and, instead, selecting the
assignments that will really benefit from pair programming?
- [ ]  Are you rotating pair assignments and work assignments regularly?
- [ ]  Are the pairs well matched in terms of pace and personality?
- [ ]  Is there a team leader to act as the focal point for management and other people outside the project?

## cc2e.com/2199 CHECKLIST: Effective Inspections

- [ ]  Do you have checklists that focus reviewer attention on areas that have been problems in the past?
- [ ]  Have you focused the inspection on defect detection rather than correc- tion?
- [ ]  Have you considered assigning perspectives or scenarios to help reviewers focus their preparation work?
- [ ]  Are reviewersrs given enough time to prepare before the inspection meet- ing, and is each one prepared?
- [ ]  Does each participant have a distinct role to play—moderator, reviewer, scribe, and so on?
- [ ]  Does the meeting move at a productive rate?
- [ ]  Is the meeting limited to two hours?
- [ ]  Have all inspection participants received specific training in conducting inspections, and has the moderator received special training in moderation skills?
- [ ]  Is data about error types collected at each inspection so that you can tailor future checklists to your organization?
492 Chapter 21: Collaborative Construction
- [ ]  Is data about preparation and inspection rates collected so that you can optimize future preparation and inspections?
- [ ]  Are the action items assigned at each inspection followed up, either per- sonally by the moderator or with a reinspection?
- [ ]  Does management understand that it should not attend inspection meetings?
- [ ]  Is there a follow-up plan to assure that fixes are made correctly?

## cc2e.com/2210 CHECKLIST: Test Cases

- [ ]  Does each requirement that applies to the class or routine have its own test case?
- [ ]  Does each element from the design that applies to the class or routine have its own test case?
- [ ]  Has each line of code been tested with at least one test case? Has this been verified by computing the minimum number of tests necessary to exercise each line of code?
- [ ]  Have all defined-used data-flow paths been tested with at least one test case?
- [ ]  Has the code been checked for data-flow patterns that are unlikely to be correct, such as defined-defined, defined-exited, and defined-killed?
- [ ]  Has a list of common errors been used to write test cases to detect errors that have occurred frequently in the past?
- [ ]  Have all simple boundaries been tested: maximum, minimum, and off-by- one boundaries?
- [ ]  Have compound boundaries been tested—that is, combinations of input data that might result in a computed variable that’s too small or too large?
- [ ]  Do test cases check for the wrong kind of data—for example, a negative number of employees in a payroll program?
- [ ]  Are representative, middle-of-the-road values tested?
- [ ]  Is the minimum normal configuration tested?
- [ ]  Is the maximum normal configuration tested?
- [ ]  Is compatibility with old data tested? And are old hardware, old versions of the operating system, and interfaces with old versions of other software tested?
- [ ]  Do the test cases make hand-checks easy?

## cc2e.com/2368 CHECKLISTS: Debugging Reminders

Techniques for Finding Defects

- [ ]  Use all the data available to make your hypothesis.
- [ ]  Refine the test cases that produce the error.
- [ ]  Exercise the code in your unit test suite.
- [ ]  Use available tools.
- [ ]  Reproduce the error several different ways.
- [ ]  Generate more data to generate more hypotheses.
- [ ]  Use the results of negative tests.
- [ ]  Brainstorm for possible hypotheses.
- [ ]  Keep a notepad by your desk, and make a list of things to try.
- [ ]  Narrow the suspicious region of the code.
- [ ]  Be suspicious of classes and routines that have had defects before.
- [ ]  Check code that’s changed recently.
- [ ]  Expand the suspicious region of the code.
- [ ]  Integrate incrementally.
- [ ]  Check for common defects.
- [ ]  Talk to someone else about the problem.
- [ ]  Take a break from the problem.
- [ ]  Set a maximum time for quick and dirty debugging.
- [ ]  Make a list of brute-force techniques, and use them.
Techniques for Syntax Errors
- [ ]  Don’t trust line numbers in compiler messages.
- [ ]  Don’t trust compiler messages.
- [ ]  Don’t trust the compiler’s second message.
- [ ]  Divide and conquer.
- [ ]  Use a syntax-directed editor to find misplaced comments and quotation marks.
Techniques for Fixing Defects
- [ ]  Understand the problem before you fix it.
- [ ]  Understand the program, not just the problem.
- [ ]  Confirm the defect diagnosis.
- [ ]  Relax.
- [ ]  Save the original source code.
- [ ]  Fix the problem, not the symptom.
- [ ]  Change the code only for good reason.
- [ ]  Make one change at a time.
- [ ]  Check your fix.
- [ ]  Add a unit test that exposes the defect.
- [ ]  Look for similar defects.
General Approach to Debugging
- [ ]  Do you use debugging as an opportunity to learn more about your pro- gram, mistakes, code quality, and problem-solving approach?
- [ ]  Do you avoid the trial-and-error, superstitious approach to debugging?
- [ ]  Do you assume that errors are your fault?
- [ ]  Do you use the scientific method to stabilize intermittent errors?
- [ ]  Do you use the scientific method to find defects?
- [ ]  Rather than using the same approach every time, do you use several differ- ent techniques to find defects?
- [ ]  Do you verify that the fix is correct?
- [ ]  Do you use compiler warning messages, execution profiling, a test frame- work, scaffolding, and interactive debugging?

## cc2e.com/2443 CHECKLIST: Reasons to Refactor

- [ ]  Code is duplicated.
- [ ]  A routine is too long.
- [ ]  A loop is too long or too deeply nested.
- [ ]  A class has poor cohesion.
- [ ]  A class interface does not provide a consistent level of abstraction.
- [ ]  A parameter list has too many parameters.
- [ ]  Changes within a class tend to be compartmentalized.
- [ ]  Changes require parallel modifications to multiple classes.
- [ ]  Inheritance hierarchies have to be modified in parallel.
- [ ]  case statements have to be modified in parallel.
- [ ]  Related data items that are used together are not organized into classes.
- [ ]  A routine uses more features of another class than of its own class.
- [ ]  A primitive data type is overloaded.
- [ ]  A class doesn’t do very much.
- [ ]  A chain of routines passes tramp data.
- [ ]  A middleman object isn’t doing anything.
- [ ]  One class is overly intimate with another.
- [ ]  A routine has a poor name.
- [ ]  Data members are public.
- [ ]  A subclass uses only a small percentage of its parents’ routines.
- [ ]  Comments are used to explain difficult code.
- [ ]  Global variables are used.
- [ ]  A routine uses setup code before a routine call or takedown code after a routine call.
- [ ]  A program contains code that seems like it might be needed someday.

## CHECKLIST: Summary of Refactorings

Data-Level Refactorings

- [ ]  Replace a magic number with a named constant.
- [ ]  Rename a variable with a clearer or more informative name.
- [ ]  Move an expression inline.
- [ ]  Replace an expression with a routine.
- [ ]  Introduce an intermediate variable.
- [ ]  Convert a multiuse variable to a multiple single-use variables.
- [ ]  Use a local variable for local purposes rather than a parameter.
- [ ]  Convert a data primitive to a class.
- [ ]  Convert a set of type codes to a class or an enumeration.
- [ ]  Convert a set of type codes to a class with subclasses.
- [ ]  Change an array to an object.
- [ ]  Encapsulate a collection.
- [ ]  Replace a traditional record with a data class.
Statement-Level Refactorings
- [ ]  Decompose a boolean expression.
- [ ]  Move a complex boolean expression into a well-named boolean function.
cc2e.com/2450
578 Chapter 24: Refactoring
- [ ]  Consolidate fragments that are duplicated within different parts of a conditional.
- [ ]  Use break or return instead of a loop control variable.
- [ ]  Return as soon as you know the answer instead of assigning a return value
within nested if-then-else statements.
- [ ]  Replace conditionals (especially repeated case statements) with polymor-
phism.
- [ ]  Create and use null objects instead of testing for null values.
Routine-Level Refactorings
- [ ]  Extract a routine.
- [ ]  Move a routine’s code inline.
- [ ]  Convert a long routine to a class.
- [ ]  Substitute a simple algorithm for a complex algorithm.
- [ ]  Add a parameter.
- [ ]  Remove a parameter.
- [ ]  Separate query operations from modification operations.
- [ ]  Combine similar routines by parameterizing them.
- [ ]  Separate routines whose behavior depends on parameters passed in.
- [ ]  Pass a whole object rather than specific fields.
- [ ]  Pass specific fields rather than a whole object.
- [ ]  Encapsulate downcasting.
Class Implementation Refactorings
- [ ]  Change value objects to reference objects.
- [ ]  Change reference objects to value objects.
- [ ]  Replace virtual routines with data initialization.
- [ ]  Change member routine or data placement.
- [ ]  Extract specialized code into a subclass.
- [ ]  Combine similar code into a superclass.

24.4 Refactoring Safely
Opening up a working sys- tem is more like opening up a human brain and replacing a nerve than opening up a sink and replacing a washer. Would maintenance be eas- ier if it was called “Software Brain Surgery?”
—Gerald Weinberg
Refactoring is a powerful technique for improving code quality. Like all powerful tools, refactoring can cause more harm than good if misused. A few simple guidelines can prevent refactoring missteps.
Save the code you start with Before you begin refactoring, make sure you can get back to the code you started with. Save a version in your revision control system, or copy the correct files to a backup directory.
24.4 Refactoring Safely 579
Class Interface Refactorings

- [ ]  Move a routine to another class.
- [ ]  Convert one class to two.
- [ ]  Eliminate a class.
- [ ]  Hide a delegate.
- [ ]  Remove a middleman.
- [ ]  Replace inheritance with delegation.
- [ ]  Replace delegation with inheritance.
- [ ]  Introduce a foreign routine.
- [ ]  Introduce an extension class.
- [ ]  Encapsulate an exposed member variable.
- [ ]  Remove Set() routines for fields that cannot be changed.
- [ ]  Hide routines that are not intended to be used outside the class.
- [ ]  Encapsulate unused routines.
- [ ]  Collapse a superclass and subclass if their implementations are very similar.
System-Level Refactorings
- [ ]  Create a definitive reference source for data you can’t control.
- [ ]  Change unidirectional class association to bidirectional class association.
- [ ]  Change bidirectional class association to unidirectional class association.
- [ ]  Provide a factory routine rather than a simple constructor.
- [ ]  Replace error codes with exceptions or vice versa.

## cc2e.com/2457 CHECKLIST: Refactoring Safely

- [ ]  Is each change part of a systematic change strategy?
- [ ]  Did you save the code you started with before beginning refactoring?
- [ ]  Are you keeping each refactoring small?
- [ ]  Are you doing refactorings one at a time?
- [ ]  Have you made a list of steps you intend to take during your refactoring?
- [ ]  Do you have a parking lot so that you can remember ideas that occur to you mid-refactoring?
- [ ]  Have you retested after each refactoring?
- [ ]  Have changes been reviewed if they are complicated or if they affect mis-
sion-critical code?
- [ ]  Have you considered the riskiness of the specific refactoring and adjusted your approach accordingly?
- [ ]  Does the change enhance the program’s internal quality rather than degrade it?
- [ ]  Have you avoided using refactoring as a cover for code and fix or as an excuse for not rewriting bad code?

## CHECKLIST: Code-Tuning Strategies

Overall Program Performance

- [ ]  Have you considered improving performance by changing the program requirements?
- [ ]  Have you considered improving performance by modifying the program’s design?
- [ ]  Have you considered improving performance by modifying the class design?
cc2e.com/2506
608 Chapter 25: Code-Tuning Strategies
- [ ]  Have you considered improving performance by avoiding operating sys- tem interactions?
- [ ]  Have you considered improving performance by avoiding I/O?
- [ ]  Have you considered improving performance by using a compiled
language instead of an interpreted language?
- [ ]  Have you considered improving performance by using compiler optimizations?
- [ ]  Have you considered improving performance by switching to different hardware?
- [ ]  Have you considered code tuning only as a last resort? Code-Tuning Approach
- [ ]  Is your program fully correct before you begin code tuning?
- [ ]  Have you measured performance bottlenecks before beginning code tuning?
- [ ]  Have you measured the effect of each code-tuning change?
- [ ]  Have you backed out the code-tuning changes that didn’t produce the intended improvement?
- [ ]  Have you tried more than one change to improve performance of each bot- tleneck—that is, iterated?

## CHECKLIST: Code-Tuning Techniques

Improve Both Speed and Size

- [ ]  Substitute table lookups for complicated logic.
- [ ]  Jam loops.
- [ ]  Use integer instead of floating-point variables.
- [ ]  Initialize data at compile time.
- [ ]  Use constants of the correct type.
- [ ]  Precompute results.
- [ ]  Eliminate common subexpressions.
- [ ]  Translate key routines to a low-level language.
cc2e.com/2672
26.7 The More Things Change, the More They Stay the Same 643
Improve Speed Only
- [ ]  Stop testing when you know the answer.
- [ ]  Order tests in case statements and if-then-else chains by frequency.
- [ ]  Compare performance of similar logic structures.
- [ ]  Use lazy evaluation.
- [ ]  Unswitch loops that contain if tests.
- [ ]  Unroll loops.
- [ ]  Minimize work performed inside loops.
- [ ]  Use sentinels in search loops.
- [ ]  Put the busiest loop on the inside of nested loops.
- [ ]  Reduce the strength of operations performed inside loops.
- [ ]  Change multiple-dimension arrays to a single dimension.
- [ ]  Minimize array references.
- [ ]  Augment data types with indexes.
- [ ]  Cache frequently used values.
- [ ]  Exploit algebraic identities.
- [ ]  Reduce strength in logical and mathematical expressions.
- [ ]  Be wary of system routines.
- [ ]  Rewrite routines inline.

## CHECKLIST: Configuration Management

General

- [ ]  Is your software configuration management plan designed to help pro- grammers and minimize overhead?
- [ ]  Does your SCM approach avoid overcontrolling the project?
- [ ]  Do you group change requests, either through informal means (such as a list of pending changes) or through a more systematic approach (such as a change-control board)?
- [ ]  Do you systematically estimate the cost, schedule, and quality impact of each proposed change?
- [ ]  Do you view major changes as a warning that requirements development isn’t yet complete?
cc2e.com/2843
670 Chapter 28: Managing Construction
Tools
- [ ]  Do you use version-control software to facilitate configuration management?
- [ ]  Do you use version-control software to reduce coordination problems of
working in teams?
Backup
- [ ]  Do you back up all project materials periodically?
- [ ]  Are project backups transferred to off-site storage periodically?
- [ ]  Are all materials backed up, including source code, documents, graphics, and important notes?
- [ ]  Have you tested the backup-recovery procedure?

## cc2e.com/2992

Additional Resources
cc2e.com/2999
Following are additional resources related to this chapter’s subjects:
Integration
Lakos, John. Large-Scale C++ Software Design. Boston, MA: Addison-Wesley, 1996. Lakos argues that a system’s “physical design”—its hierarchy of files, directories, and libraries—significantly affects a development team’s ability to build software. If you don’t pay attention to the physical design, build times will become long enough to undermine frequent integration. Lakos’s discussion focuses on C++, but the insights related to “physical design” apply just as much to projects in other languages.
Additional Resources 707
CHECKLIST: Integration
Integration Strategy

- [ ]  Does the strategy identify the optimal order in which subsystems, classes, and routines should be integrated?
- [ ]  Is the integration order coordinated with the construction order so that classes will be ready for integration at the right time?
- [ ]  Does the strategy lead to easy diagnosis of defects?
- [ ]  Does the strategy keep scaffolding to a minimum?
- [ ]  Is the strategy better than other approaches?
- [ ]  Have the interfaces between components been specified well? (Specifying interfaces isn’t an integration task, but verifying that they have been spec- ified well is.)
Daily Build and Smoke Test
- [ ]  Is the project building frequently—ideally, daily—to support incremental integration?
- [ ]  Is a smoke test run with each build so that you know whether the build works?
- [ ]  Have you automated the build and the smoke test?
- [ ]  Do developers check in their code frequently—going no more than a day or
two between check-ins?
- [ ]  Is the smoke test kept up to date with the code, expanding as the code expands?
- [ ]  Is a broken build a rare occurrence?
- [ ]  Do you build and smoke test the software even when you’re under pres- sure?

## Checklist: Programming Tools

- [ ]  Do you have an effective IDE?
- [ ]  Does your IDE support integration with source-code control; build, test,
and debugging tools; and other useful functions?
- [ ]  Do you have tools that automate common refactorings?
- [ ]  Are you using version control to manage source code, content, require- ments, designs, project plans, and other project artifacts?
- [ ]  If you’re working on a very large project, are you using a data dictionary or some other central repository that contains authoritative descriptions of each class used in the system?
- [ ]  Have you considered code libraries as alternatives to writing custom code, where available?
cc2e.com/3019
Key Points
■ Programmers sometimes overlook some of the most powerful tools for years before discovering them.
■ Good tools can make your life a lot easier.
■ Tools are readily available for editing, analyzing code quality, refactoring, ver-
sion control, debugging, testing, and code tuning.
■ You can make many of the special-purpose tools you need.
■ Good tools can reduce the more tedious aspects of software development, but they can’t eliminate the need for programming, although they will continue to reshape what we mean by “programming.”
Key Points 725
- [ ]  Are you making use of an interactive debugger?
- [ ]  Do you use make or other dependency-control software to build programs
efficiently and reliably?
- [ ]  Does your test environment include an automated test framework, auto- mated test generators, coverage monitors, system perturbers, diff tools, and defect-tracking software?
- [ ]  Have you created any custom tools that would help support your specific project’s needs, especially tools that automate repetitive tasks?
- [ ]  Overall, does your environment benefit from adequate tool support?

## CHECKLIST: Layout

General

- [ ]  Is formatting done primarily to illuminate the logical structure of the code?
- [ ]  Can the formatting scheme be used consistently?
- [ ]  Does the formatting scheme result in code that’s easy to maintain?
- [ ]  Does the formatting scheme improve code readability?
Control Structures
- [ ]  Does the code avoid doubly indented begin-end or {} pairs?
- [ ]  Are sequential blocks separated from each other with blank lines?
- [ ]  Are complicated expressions formatted for readability?
- [ ]  Are single-statement blocks formatted consistently?
- [ ]  Are case statements formatted in a way that’s consistent with the format- ting of other control structures?
- [ ]  Have gotos been formatted in a way that makes their use obvious?
cc2e.com/3194
774 Chapter 31: Layout and Style
Individual Statements
- [ ]  Is white space used to make logical expressions, array references, and rou- tine arguments readable?
- [ ]  Do incomplete statements end the line in a way that’s obviously incorrect?
- [ ]  Are continuation lines indented the standard indentation amount?
- [ ]  Does each line contain at most one statement?
- [ ]  Is each statement written without side effects?
- [ ]  Is there at most one data declaration per line?
Comments
- [ ]  Are the comments indented the same number of spaces as the code they comment?
- [ ]  Is the commenting style easy to maintain?
Routines
- [ ]  Are the arguments to each routine formatted so that each argument is easy to read, modify, and comment?
- [ ]  Are blank lines used to separate parts of a routine?
Classes, Files and Programs
- [ ]  Is there a one-to-one relationship between classes and files for most classes and files?
- [ ]  If a file does contain multiple classes, are all the routines in each class grouped together and is each class clearly identified?
- [ ]  Are routines within a file clearly separated with blank lines?
- [ ]  In lieu of a stronger organizing principle, are all routines in alphabetical sequence?

## cc2e.com/3252

CHECKLIST: Self-Documenting Code
Classes

- [ ]  Does the class’s interface present a consistent abstraction?
- [ ]  Is the class well named, and does its name describe its central purpose?
- [ ]  Does the class’s interface make obvious how you should use the class?
- [ ]  Is the class’s interface abstract enough that you don’t have to think about how its services are implemented? Can you treat the class as a black box?
Routines
- [ ]  Does each routine’s name describe exactly what the routine does?
- [ ]  Does each routine perform one well-defined task?
- [ ]  Have all parts of each routine that would benefit from being put into their own routines been put into their own routines?
- [ ]  Is each routine’s interface obvious and clear? Data Names
- [ ]  Are type names descriptive enough to help document data declarations?
- [ ]  Are variables named well?
- [ ]  Are variables used only for the purpose for which they’re named?
- [ ]  Are loop counters given more informative names than i, j, and k?
- [ ]  Are well-named enumerated types used instead of makeshift flags or bool- ean variables?
- [ ]  Are named constants used instead of magic numbers or magic strings?
- [ ]  Do naming conventions distinguish among type names, enumerated types,
named constants, local variables, class variables, and global variables?
Data Organization
- [ ]  Are extra variables used for clarity when needed?
- [ ]  Are references to variables close together?
- [ ]  Are data types simple so that they minimize complexity?
- [ ]  Is complicated data accessed through abstract access routines (abstract data types)?
Control
- [ ]  Is the nominal path through the code clear?
- [ ]  Are related statements grouped together?
32.3 To Comment or Not to Comment
Comments are easier to write poorly than well, and commenting can be more damag- ing than helpful. The heated discussions over the virtues of commenting often sound like philosophical debates over moral virtues, which makes me think that if Socrates had been a computer programmer, he and his students might have had the following discussion.
The Commento
Characters:
THRASYMACHUS A green, theoretical purist who believes everything he reads
CALLICLES A battle-hardened veteran from the old school—a “real” programmer
GLAUCON A young, confident, hot-shot computer jock
ISMENE A senior programmer tired of big promises, just looking for a few practices that work
32.3 To Comment or Not to Comment 781
- [ ]  Have relatively independent groups of statements been packaged into their own routines?
- [ ]  Does the normal case follow the if rather than the else?
- [ ]  Are control structures simple so that they minimize complexity?
- [ ]  Does each loop perform one and only one function, as a well-defined rou- tine would?
- [ ]  Is nesting minimized?
- [ ]  Have boolean expressions been simplified by using additional boolean
variables, boolean functions, and decision tables?
Layout
- [ ]  Does the program’s layout show its logical structure? Design
- [ ]  Is the code straightforward, and does it avoid cleverness?
- [ ]  Are implementation details hidden as much as possible?
- [ ]  Is the program written in terms of the problem domain as much as possi- ble rather than in terms of computer-science or programming-language structures?

## cc2e.com/3243

CHECKLIST: Good Commenting Technique
General

- [ ]  Can someone pick up the code and immediately start to understand it?
- [ ]  Do comments explain the code’s intent or summarize what the code does,
rather than just repeating the code?
- [ ]  Is the Pseudocode Programming Process used to reduce commenting time?
- [ ]  Has tricky code been rewritten rather than commented?
- [ ]  Are comments up to date?
- [ ]  Are comments clear and correct?
- [ ]  Does the commenting style allow comments to be easily modified?
Statements and Paragraphs
- [ ]  Does the code avoid endline comments?
- [ ]  Do comments focus on why rather than how?
- [ ]  Do comments prepare the reader for the code to follow?
- [ ]  Does every comment count? Have redundant, extraneous, and self-indul- gent comments been removed or improved?
- [ ]  Are surprises documented?
- [ ]  Have abbreviations been avoided?
- [ ]  Is the distinction between major and minor comments clear?
- [ ]  Is code that works around an error or undocumented feature commented?
Data Declarations
- [ ]  Are units on data declarations commented?
- [ ]  Are the ranges of values on numeric data commented?
- [ ]  Are coded meanings commented?
- [ ]  Are limitations on input data commented?
- [ ]  Are flags documented to the bit level?
- [ ]  Has each global variable been commented where it is declared?
- [ ]  Has each global variable been identified as such at each usage, by a naming convention, a comment, or both?
- [ ]  Are magic numbers replaced with named constants or variables rather than just documented?
Control Structures
- [ ]  Is each control statement commented?
- [ ]  Are the ends of long or complex control structures commented or, when
possible, simplified so that they don’t need comments?
Routines
- [ ]  Is the purpose of each routine commented?
- [ ]  Are other facts about each routine given in comments, when relevant, including input and output data, interface assumptions, limitations, error corrections, global effects, and sources of algorithms?
Files, Classes, and Programs
- [ ]  Does the program have a short document, such as that described in the Book Paradigm, that gives an overall view of how the program is orga- nized?
- [ ]  Is the purpose of each file described?
- [ ]  Are the author’s name, e-mail address, and phone number in the listing?
