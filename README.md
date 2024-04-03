## Practical notes - about this collection

A collection of practical notes on software engineering, broken down into habits, lessons learned, or plain old notes worth looking at, from various resources such as those listed in the [charlax/professional-programming](https://github.com/charlax/professional-programming) repo.

## Principles

The goal of this page is to collect and centralize the best habits, lessons and notes from the various resources. This page is not meant to be comprehensive, but rather my personal guide that I can revisit over time. I try to keep it light and avoid excessive detail.

The selection of resources is opinionated. The structure of this repo is based on the order within the amazing repo by charlax.

## Topics

### Code reviews

- 

### Coding & code quality

Practice coding
- **Code regurlarly**
- Code often, learn a language in-depth, and keep solving real-world problems
- Biggest contributor to your progress is how much you practice
- You must apply your knowledge by writing a lot of code
- Coding daily is a great habit to pick up
- Aim to work on meaningful tasks and problems every day which you solve with code
- If you're not coding daily, for whatever reason, try to find ways to — pick up extra projects at work, move to a team which does a lot of coding, work on a side project that sharpens your programming skillset
- You need to code daily to keep growing into a competent software engineer
- **Ask for code reviews**
- Code should work, be read and understood by others, and follow common conventions
- After you write code, get feedback on it, so you can improve it
- Aim to get feedback on all the code you write, even if code reviews aren't required
- Ask more epxerienced people for extra feedback to help you grow faster
- If getting additional code reviews is hard, ask a colleague to pair woth you, so you can walk them through the code and ask which areas of improvement they see
- If there's nobody to work with, try finding someone from outside your team who's experienced with the technology or domain, and can give meaningful feedback
- (Learn from code reviews) Make notes on the feedback you get and if you see repeated comments, consider addressing them
- (Deal with harsh code reviews) Assume the comment is directed at the code, not you (Do not take it personally)
- **Read as much code as you write**
- Get involved early in code reviews across the team or the codebase (even when you're not an expert in the language, or very familiar with the code base)
- Make it a habit to go through each change colleagues make, understand what it does, and make notes on the approaches taken
- When something is unclear, ask the author
- Even better, read code written outsde of your team or company
- If you can access other projects in your workplace, start following code changes and code reviews by teams whose codebases you depend on
- Teams and companies often follow conventions specific to their environment
- Read open-source code to see other people's code and get a sense of what's going on beyond your company
- Try to find an actively developed open-source project which works with a similar language as you use
- Check out a project on GitHub, familiarize yourself with how it works, and then start following the changes
- Try to make sense of that's happening, which type of code is being written, and the feedback which code reviewers give
- **Code some more**
- Build a small side project that solves a minor problem for you, your friends, or your family
- Write code that works and try picking up new approaches or technology stacks
- Complete a tutorial or training with coding exercises
- Do coding challenges like those on LeetCode, Project Euler, or others, and practice a language which you use, and improve your algorithmic problem-solving skills
- Do regular code katas as they help to familiarize with a language and improve your problem-solving and algorithmic skills
- Search for daily code kata challenges and aim to do them daily, for a few weeks, until the katas stop being challenging

Readable code
- Unreadable code is a major contributor to technical debt; tech debt is a major contributor to teams slowing down
- If code is not readable, engineers spend a lot of time on figuring out what id does and how it works, and might even misunderstand the code and its behavior
- Readable, well-tested code makes refactoring, extending, and modifying a codebase as eas as possible
- Readable, well-tested code is the foundation of a solid codebase that gives engineers confidence to make changes
- "Readable code" begins with code you find easy to read
- When finishing coding, take a break and clear your mind, then re-read the code assuming no knowledge of it – can you follow the code? Do the names of variables and methids help you understand what they do? Are the comments in places where the code isn't enough? Is the style of the code consistent across the changes?
- Think about how you could make the code more readable
- Test of readable code: _can others understand it?_
- Get feedback via code reviews and ask how clear the code is
- Readable code will attract few to no clarifying questions – each question and misunderstanding is a hint that the code could be more readable
- If you're happy with how clear the code is and other developers find it readable, you're on the right track
- **Things to pay attention to**
- Always write code with two main goals in mind: (1) The code should be correct, meaning it produces the expected results when executed and (2) Other developers find it easy to read and understand
- A few things to pay attention to :point_down:
- Naming - Use self-explanatory, concise names. Stick to consistent naming approaches in line with the naming used on the codebase.
- Well-structured - The codebase is easy to navigate as functions, classes, and modules follow a logical structure. Formatting is consistent across classes and the codebase.
- Keep the code simple (KISS) - The simpler code is, the easier it is to read and understand. With this in mind, aim for small functions and classes that don't grow too big. Avoid introducing complex coding solutions for the sake of it, when you could get things done simpler.
- Single responsibility - Aim for functions to do just one thing, and for classes to have a main responsibility. A single focus makes it easer to test for correctness, and also for tests to be reusable.
- Don't repeat yourself (DRY) - Avoid copy-pasting code. Instead, if you find the need to reuse, consider refactoring the code so it follows the single responsibility principle.
- Comments - Explain the "why" on the code, not the "how" in your comments.
- Continuously refactor to maintain readability - Readable codebases stay readable as they grow thanks to continuous refactoring.

Writing quality code
- **Use the right amount of abstractions**
- Write code that (is readable and) uses the right amount of abstractions and works reliably enough, accounting for potential error cases
- E.g. classes abstract away implementation details from other parts of the code
- Information hiding reduces complexity in two ways, (1) it simplifies the interface to a module (or class) and hides away the details which reduces the cognitive load on developers who use it, (2) information hiding makes it easier to evolve the system as there are no dependencies on that information outside of the module containing the information
- You don't want to break a system into too many small pieces as that adds unnecessary cognitive load
- **Handle errors, and handle them well**
- Have a consistent error-handling strategy – What do you do when you come across a condition which could be an error? DO you throw an error, log the error, do both, or something else?
- You should be able to explain how you handle errors (ideally consistently with how everyone on the team does)
- You should aim to have a strategy for error logging
- When in doubt use defensive programming – assume inputs from other parts of the code are unreliable and potentially malicious
- A few approaches for defensive programming :point_down:
- Validate inputs (especially from users) – Assume malicious intent or accidentally incorrect information; validate a parameter and throw an error if it's not
- Expect invalid responses – When invoking a function, don't assume it will always return a valid value; expect empty responses or odd values
- Expect malicious input – Expect an attacker to deliberately send input that breaks the system
- Expect exceptions and errors – When invoking functions, be prepared that they might throw an error
- There will be times when you don't need to use defensive programming, e.g. when working with a class where all inputs have been validated by design
- **Be wary of "unknown" states**
- What to do with unknown states, e.g. in the mapping of API responses to success or failure codes
- Two common approaches: Allowlists and Blocklists
- Allowlists – Create a list of successful responses and assume everything else is a failure
- Blocklists – Create a list of responses considered failures and assume everything else is a success
- Handling an "unknown" state can cause unexpected problems; best approach for handling unknown responses and codes is having a third state that is "unknown" and raising an error, alert, or else, to get an engineer to look at it

### Debugging

- 

### Getting Things Done

- 

### Software Development

Become proficient in a language
- Learn a language really well
- Knowing a language inside out :left_right_arrow: Knowing how to use the language :arrow_right: Understanding constructs, operations, etc., the what and why of best practices, memory management, garbage collection, compiling, performance engineering
- **Learn the fundamentals of a language** – built-in data types, variables, data structures, operators, control statements, classes, objects, standard ways of error handling
- Try out some more advanced parts of the language – generics, parallel execution/threading, complex data types, additional features the language supports
- Have reference material you can return to – Read the documentation of the language, find a good language reference, look at code examples, or study a book of the language's fundamentals
- **Go a level deeper** – What really happens when you declare a variable, a function, or a class? How will the code be compiled to machine code, and which optimizations might occur? What is the memory footprint of the program? How can you observe the memory used? How is memory freed up? Assuming the language uses garbage collection, how does it work? If the language supports generics, are both covariance and contravariance supported? How is generic code interpreted, and how is it optimized under the hood?
- Seek out books, videos, courses, and other resources on the advanced parts of a language
- When trying to answer questions like the above, don't forget these are complex and cover areas you might not know, or be able to tackle yourself
- Learn to use tooling to peek under the hood and get more information on how things work (e.g. memory and CPU profilers, dev tools, diagnostic tools)
- **Learn the "main" framework you use with a language** – follow the same approach in learning a framework as when learning a language; learn the fundamentals, then peek under the hood and go deeper
- Invest time in digging deeper; the knowledge you gain should be an advantage when debugging tricky bugs, making architecture decisions, or migrating to new versions of the framework
- **Learn a second language** – Look for opportunities once you're familiar enough with your first language
- It's easier to compare strengths and weaknesses – between your first and your second language (assuming you learned the first in-depth)
- Go deeper into your first language – learning a second language tends to help ypu become more expert in your first language; happens when you tru to do something in your "main" language which the second language supports
- You shake the habit of only using your "main" language – a single programming language is rarely the best fit for all projects and situations; get into the habit of being unafraid to learn new languages by learning new languages
- It's easier to learn more languages – the more languages you learn, the more you appreciate their different features and capabilities
- **Go deep in at least one area, early in your career** – study in-depth resources, pair with someone who's an expert in an area to learn from them while asking for self-learning resources and completing them
- Go deep by studying the seemingly "boring" but necessary things you come across, day to day (blub studies); learning the principles behind something makes it easer to learn similar things; blub studies are broadly applicable because even if you're learning about details of one blubby system, that system's design will contain a juicy, non-blubby core of extractible general principles
- Blub studies, _finding out how the things you use day to day actually work_, helps to go deep and broad
- As long as you spend time learning things outside of your comfort zone, your depth and breadth of knowledge and skill will grow

Debugging
- Engineers who can debug quickly and efficiently, fix errors quicker, and iterate faster
- Inspecting code while it is executing is one of the best ways to see what incorrect assumptions you made, and how the code actually behaves
- **Know your debugging tools** – start by discovering the debugging tools which come with the IDE you use
  - Set breakpoints and inspect the local variables
  - Step in/out/over functions and inspect the call stack
  - Look up documentation and tutorials on how to use the more advanced features
- Some debuggers may support some of the following helpful features:
  - Modifying variables on the fly
  - Evaluating expressions during debugging
  - Conditional breakpoints and exception breakpoints
  - Watchpoints (a breakpoint set on a variable, fired when it is changing)
  - Dropping to a frame (restarting debugging from another part of the call stack)
  - Skip between threads
  - Modify source code while the debugger is running
  - Modify environment variables
  - Simulate sensory inputs (for hardware-based environments like mobile)
- **Observe how experienced developers debug** – ask if you can shadow them or pair with them as they debug a tricky bug; mention that you're interestd to learn how they approach finding the root causes of bugs
- **Learn to debug without tools** – such approaches include:
  - Log to the console – start dumping messages when a function is called; print the values of variables and anything else that could be helpful
  - Paper debugging – Using pen and paper, or a whiteboard, write up key variables you care about and start to execute the code in your head, writing down how those variables change each time; if you have access to a debugger, do paper debugging first, then run the debugger to check if you ran the program correctly in your head
  - Write (unit) tests – similar to test-driven development (TDD) and especially useful when debugging functions; write tests that specify the expected input and the expected outputs; check which succeed and which don't; modify the code and quickly rerun the tests

Refactoring
- To be good at refactoring, you must do it – a lot
- **Practice refactoring as often as possible**
- Start by refactoring your own code after it's written
  - When you complete a task and your code works, read through all the changes with a critical eye
  - What could be done better, or more expressively?
  - How could the code read more nicely?
  - When you see something you can improve, make the change
- Get ideas for refactoring via code reviews and act on them
  - Check for comments which point out what could be improved at the codebase level
  - Comments like this often highlight opportunities for refactoring other parts of the code
  - If you see a comment which could be an opportunity for a code change, take it up and volunteer to do a refactor
  - Pair with someone who can confirm it's a good idea and review your refactor later
  - Do this refactor as a separate task or pull request to make it easy to review
- Read through the code
  - Make notes of inconsistencies and hard to understand parts while reading code
  - Reading code and trying to understand what it does is a more focused way of getting ideas for refactor opportunities than via code reviews
  - Put the notes into a private document or use an extension for your IDE and record your own comments; with these comments stored in a local file and not committed or seen by anyone else
  - Write up a list of things you'd like to refactor, then get feedback from others
  - Don't just jump into fixing everything you've spotted, instead, get a second opinion and talk through your observations with someone experienced in the codebase; in rare cases they might have decided to trade off less readable code for other reasons such as performance or maintainability 
  - With the feedback, decide which refactorings make sense, then estimate the effort each one would take and put them together in a sequence of how to proceed; it's a good idea to put simpler refactorings first
  - **Know your IDE's refactor functionality and use it** – learn the refactoring it supports, like renaming variables, changing function signatures, extracting logic into its own function, and more
  - Start with simple refactors and slowly move to more complex one
  - The smaller the scope of a refactor, the easier it is to get it right and test that nothing broke
  - An under-appreciated refactor opportunity is refactoring unit tests; start with just one test, make it more readable, and then get feedback via code reviews
  - Next, extract common functionality of the classes or functions involved in the test into their own methods, simplifying tests and making them more readable
  - Be very careful when refactoring poorly tested production code; it's key to have a safety net when refactoring frequently and this safety net is unit tests
  - **Make refactoring an everyday habit** – exercise frequently, make mistakes, and learn from them; soon you'll refactor without fear and little effort

Testing
- **Test your code before requesting a code review or committing it** – manually test your code when the work is done; think about possible edge cases and execute simple tests
- **Care deeply about edge cases** – go through potential edge cases and confirm with stakeholders what should happen in such scenarios
- Write down (even manual) test cases even before starting development and extend this list as you go and find new, previously unconsidered edge cases
- When the code is ready, test for all cases and only commit the code when it works as it should
- Don't push your code until you've confirmed all of your assumptions
- **Automated testing is a tool commonly used by competent developers** – you have already defined the edge cases and test cases; write the unit and integration tests for them

### Tools of the Productive Engineer / Tools of the Trade

- To be a productive developer, you need a good understanding and control of the tools you use
- How does your tooling, build, deployment, and other ststems work?

Your local development environment
- Master your coding environment
- Get familiar with your IDE and learn its capabilities
- Some capabilities you should find in modern IDEs:
  - Refactoring (built-in refactoring capabilities)
  - Compiling (setting up one-click building/compilation of a project e.g. through a keyboard shortcut or on file saves)
  - Running the project (launching your compiled project to run with a single click or keyboard shortcut)
  - Hot reload (is it possible to make a change to the code while it's running, and have this change be live after file saves)
  - Debugging (how to place a breakpoint, step into/out/over/ functions; where can you see the stack trace; how can you view a local variable)
  - Advanced debugging (using conditional breakpoints; ignoring a condition n times before it breaks; changing variables when the breakpoint is hit)
  - Running tests (run automated tests such as unit or integration tests)
  - Debugging tests (placing breakpoints and debugging a test; debugging a specific test by itself)
  - Creating a pull request (source control management from within the IDE)
- Understanding how to use your IDE effectively will shorten coding iteration cycles and speed up your work
- **Rapid edit, compile/run, output cycle** :arrow_right: don't accept a slow cycle from an edit to the change being live in your environment; figure out how to speed up this process
- Making iterations rapidly will boost your productivity and keep you "in the zone" when working
- **Configure your IDE and workflow** – once you got the hang of the development in your current environment
  - Set up (or figure out keyboard) shortcuts for frequents actions (running your project, running a test, searching the codebase, and more)
  - Configure your color scheme (choose a color scheme which makes your IDE easier to work with)
  - Set up code formatting and linting if needed (ensure your settings match your team's formatting and linting rules if they have some in place; if no rules are enforced, consider selecting a code formatter and linting style)
  - If your IDE has a playground, use it (get familiar with this environment and play around with it, as it might be useful for quick prototyping)
  - Look into alternative development environments and playgrounds (prioritize learning the ones your team has settled on first)
 
Frequently used tools
- Learn version control tooling and the ideas behind **Git**
  - Branching
  - Rebasing
  - Resolving conflicts and merging
  - Cherry picking
- Find a Git client you're comfortable using
- Command-line/terminal
  - Especially useful when working with remote machines when you might need to connect via SSH, and then use the command-line interface
  - Familiarize yourself with common command-line commands
  - Start using it for tasks to get familiar with it
  - The more familiar you're with the command-line, the more effficient your workflow is
- Regular expressions
  - Learn the basic syntax of how they work
  - Use them when searching files and replacing contents
  - Find a tool that helps you test and verify regular expression when needed
- SQL
  - Learn the basics of SQL (creating tables, select, where, order by, group by, having clauses)
  - Understand joining tables and using views
  - Understand the performance of statements and the importance of table indexes in executing more complicated queries
- Development tools at your company
  - Internal (possibly custom) development tools that engineers regularly use
  - Ask fellow engineers which tools they use regularly
  - Make a list and figure out how to access them and how they work
  - Create your own cheatsheet on how to use them efficiently
- **Your productivity cheatsheet** – start with a blank document and add the names of tools with a short description of what they do, links, commands, and other notes

Ways to iterate quickly
- **Read existing code and understand what it does** – challenge with coding is often not how to write, but what to write
- You'll be more productive when you understand how things work, and can navigate the codebase
- A few things you can do:
  - Ask someone (an experienced engineer) to walk you through the structure/parts of the codebase, which parts do what, and what to take note of
  - Draw out classes/modules, and how they connect (create a diagram by hand or a sketching tool) and write down your interpretation of their roles, and what they connect to
  - Share your code map with teammates and ask for feeedback; frequently, it will be you and others that may learn new things about the codebase; others may find pointers to things the code should improve on, or relationships they didn't realize existed
  - Create a cheatsheet – take notes on where to find key parts in the code, and frequently used modules or classes; could be as simple as a text file or doc; record the "a-ha!" moments of clarity
- **Know how to debug the CI/CD**
  - Issues such as unexpectedly failing tests on the CI/CD tend to be rare but can be challenging to pinpoint
  - Understand how CI/CD works at your company or on your team
  - Which scripts run and in what order?
  - How can you inspect the setup?
  - Ask longer-tenured or more experienced engineers (or the dedicated CI/CD team if present) for pinpointers on this system
  - How do you access CI/CD logs?
- **Know how to access production logs and dashboards**
- Debugging production issues is challenging without access to details about what might have happened
- Figure out the options for accessing:
  - Production logs, dashboards and metrics
  - How to filter those logs to certain users
  - How to query various relevant data sources for debugging
  - How to access crash dumps, errors, and exceptions for specific users
  - Processes to follow when debugging production logs (e.g. if you access personal information when debugging production data, there may be a data protection process to follow)
  - If you have a productivity cheat sheet, add details to it for quick reference later
- **Make small code changes when possible** – 

## Credits

<a name="eng-guidebook"></a>\[1\] G. Orosz, "[The Software Engineer's Guidebook: Navigating Senior, Tech Lead, and Staff Engineer Positions at Tech Companies and Startups](https://www.engguidebook.com/)," Self-published, 2023.

\[[1](#eng-guidebook)\]


