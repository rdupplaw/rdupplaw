- :wave: Hi, I’m Robert.
- :office: I'm currently working as a software developer at Heywood Pension Technologies.
- :coffee: I write Java (as well as any other language I need to use).
- :sparkling_heart: I love agile/XP development practices like test-driven development, pairing and mobbing,  and continuous integration/delivery.
- :books: I read a lot and try to apply it to my work (see my [bookshelf](#bookshelf)).
- :man_student: I graduated from Makers web development bootcamp July 2021.
- :link: [LinkedIn](https://www.linkedin.com/in/robert-dupplaw/), [Twitter](https://twitter.com/robert_dupplaw), [Blog](https://rdupplaw.github.io/blog/).

## Bookshelf

In descending order of date read.

### Amazon Web Services in Action, Third Edition

A useful book to acquaint yourself with the most important AWS services and how they can fit together.

The first part of the book is an introduction to the cloud and a quick overview of various AWS services, followed by a brief example of deploying WordPress on AWS.

In parts two and three, each chapter covers a service, or a small group of related services. The coverage of each service is good enough to give you an idea of what kind of problems that service is suitable for.

The fourth part (the last ~150 pages of the book) was the most valuable for me, as it covered some services and architectural concepts for designing and delivering good systems on AWS. 

Chapter 16 was especially good, as they walked through designing a fault-tolerant application, including auto-scaling EC2 groups connected by an SQS queue, and using S3 and DynamoDB. The conceptual explanation of an idempotent finite state machine, as a way to model resilient architecture, was interesting. Chapter 17 added to this by showing how to scale the number of EC2 instances up and down based on CloudWatch metrics.

The tutorials confused me at first, because there's not really anything to follow along with. Most of them just give you a CloudFormation template to deploy, then explain what it does. Which is fine, because the CloudFormation templates are more useful and easier to understand, at least for me, than a tutorial of clicking around the AWS console.

### Understanding Distributed Systems, 2nd Edition

The best way to describe this book is "practical theory". It doesn't exhaustively cover the theory of distributed systems (which would be impossible in one book). Instead, it covers a wide range of concepts at the level required to build the kind of distributed systems that most developers would build in practice. Personally, it has helped me design a (relatively simple) distributed system at work.

The first part of the book gives an overview of networking concepts, highlighting the leaks in the lower level abstractions that we need to be aware of when building on them. For example, when covering TCP, it focusses on the connection lifecycle, flow control, and congestion control, which can be important when building systems that communicate using this protocol.

The second part of the book builds on these basic technical concepts, explaining how we can achieve some level of coordination despite unreliable networks and applications. Raft leader election and state machine replication are particularly interesting. The CAP and PACELC theorems are useful ways of thinking about trade-offs in distributed systems. On the other hand, the CALM theorem states that a monotonic system doesn't require any of this complicated coordination.

The third and fourth parts of the book explain various tactics to achieve scalability and resilience in distributed applications, while the fifth and final part of the book briefly touches on how to develop and operate a distributed system: testing, continuous delivery, and monitoring.

### xUnit Test Patterns: Refactoring Test Code

This is a huge, comprehensive book, containing every testing pattern I knew of and many more.

The first ~200 pages build up a convincing narrative of philosophies and practices around automated testing strategy, touching on important patterns as they come up.

The remaining ~600 pages explain each smell and pattern in detail. This pattern catalogue shouldn't be read front to back. I skimmed it, and paid more attention to interesting or important patterns. I'm sure I will refer back to it in the future.

The most interesting set of patterns for me are the ones related to test doubles. The author's categorisation of different types of test double (stubs, spies, mocks and fakes) clears up a lot of the arguments seen online about the subject, and helped me to understand the different reasons we replace dependencies during tests. For example, mocking is useful if you need to verify indirect outputs (if they would otherwise be untested), and stubbing is useful if I need to provide specific indirect inputs (e.g. to inject an exception or another output that's hard to generate from the real dependency).

The strength of this book is that it doesn't present just a single view of testing, but many. The author treats each point of view fairly and respectfully, explaining the rationale behind every pattern, where it can be useful, and what are its drawbacks.

The only thing I think was missing from this book was: what should the system under test be? One class, one module? Should you test non-public classes and methods? Should you test only through the ports of the ports and adapters pattern? It's mentioned that it's best to test through the "front door", i.e. the public API, and that system-level tests can test through the UI or, ideally, directly on the service layer, and in most of the examples it's implied that we're only testing one class or a small group of related classes. It would have been interesting to read some discussion specifically about test granularity.

### Core Java, Volume II: Advanced Features, 12th Edition

More of the same from the first volume, but about more specialised topics like XML parsing, annotation processing, networking, security, and database programming.

### Core Java, Volume I: Fundamentals, 12th Edition

Extensive and meticulous coverage of the fundamentals of the Java language and standard library. Dull at times, but overall not bad for a Java textbook. It's good that the author explains why things have been designed in a certain way, what problems each thing solves, where each of the available options would be suitable, and any pitfalls. The copious example programs also demonstrate how each feature is meant to be used.

### Learning SQL, 3rd Edition

Well-structured overview of SQL and relational databases. I had limited practical experience with SQL before reading, so this book introduced me to some useful features, like set operations, views, and window functions. It also clarified some of the features I didn't properly understand, like indexes, the different join types, and concurrency control (transactions, isolation levels, read phenomena, locking and versioning).

The book uses MySQL for most examples while also mentioning Oracle and MS SQL differences, but almost completely ignores PostgreSQL. Luckily, PostgreSQL has great documentation, so I never ran into any trouble adjusting the examples and exercises (which I was running against a PostgreSQL docker container with the sakila data preloaded). In particular, the whole of chapter 7 is about various built-in functions related to strings, numbers, and dates, so it's not very useful if you're not using one of the three covered RDBMSs.

The exercises at the end of each chapter are fairly good at reviewing the concepts learned.

In hindsight, although this book is good, I'd recommend just reading through the excellent PostgreSQL documentation instead, which has both greater breadth and depth than this book.

### Working Effectively with Legacy Code

Working Effectively with Legacy Code provides an effective conceptual framework for thinking about legacy code, alongside a versatile catalogue of concrete techniques. I've applied the concepts and several of the techniques in my day-to-day work on a legacy codebase and they've served me well.

The central line of argument of the book is as follows:
- Legacy code is code without unit tests
- To maintain legacy code, we need to write unit tests
- To unit test legacy code, we need to instantiate it, exercise its methods and sense its effects
- To instantiate and exercise legacy code, we need to break difficult dependencies on other objects and resources

Seams are the places where we can break dependencies. By identifying places where we can introduce seams (such as object seams provided by polymorphism and dependency injection) we can break difficult dependencies, allowing us to instantiate and test objects more easily.

This book doesn't tell you how to take poorly-written code and transform it into clear, maintainable, idiomatic software. In fact, many of the techniques result in worse code in terms of readability. This book is about taking the first, tiny step towards better code by making it testable. After that, it's up to you to improve the design, with your new tests as guard rails. For that, I would recommend Martin Fowler's Refactoring.

### Refactoring: Improving the Design of Existing Code, 2nd Edition

This book explains the underlying principles of refactoring and contains a detailed catalogue of the most common and important refactorings, including tutorials for most of them. Fowler does a great job of explaining the importance of refactoring, as well as demonstrating refactorings in practical examples. This is probably my favourite book on programming so far, due to all the nuggets of practical wisdom contained.

Refactoring (verb) is the process of improving the design of software without changing its observable behaviour. This isn't just a cosmetic concern. The practical purpose of refactoring is to make it easier to add or change features by removing duplication and making the code easier to understand. It's absolutely essential in modern software development that we improve the design of our software as our understanding of the problem develops, otherwise it will become harder and harder to add or change features.

Refactoring goes hand-in-hand with adding or changing features. First refactor to make it easy to add the feature, then add the feature. This is often missed in corporate development departments, where refactoring is seen as a separate task.

A solid suite of unit tests is required as a safety net for most refactoring. If one doesn't exist, create it before refactoring.

Refactoring should be carried out as a series of small steps (if you haven't seen someone working like this before, the tiny size of these steps will surprise you). At each step, the software should still work (the tests should pass). If you're refactoring and the software doesn't work for a long period of time, you're not refactoring correctly and you're more likely to make mistakes.

The size of your steps can change depending on your confidence. If the change is obvious, you can take large steps. If you encounter an unexpected test failure, revert to your last known working version (e.g. using git) and try again with smaller steps.

The book also contains a catalogue of code smells (software red flags) with the refactorings which can remedy them.

### Test-Driven Development: By Example

A brilliant, careful way to design software. I wish I had read this much sooner. I had previously learned TDD at my bootcamp, supplemented with a few online resources, but this book cleared up a lot of issues I had been having. 

For example, up to now I had only ever used the Triangulation style of TDD, where you only generalise code when you have multiple examples (i.e. multiple tests for the same behaviour), but now I know that this is the most conservative strategy. Instead I can use Fake It (then refactor) or Obvious Implementation to quickly get to green when I don't feel the need to be so careful.

Because I had previously only used Triangulation, I also misunderstood the refactoring step slightly. Beck's explanation of this step as removing duplication, including between the code and the tests, cleared things up for me. For example, when you have a test to check a method returns 1 with some input, and you hard code return 1 into the method, there is duplication between the test and the code. You can refactor this to use variables instead of constants in order to remove duplication, with no need to triangulate and add a test for returning 2.

I've also learned that my definition of a "single change" is much bigger than Beck's definition, and I can now take much smaller steps when I need to. 

### Clean Code

This book describes the Object Mentor School of Clean Code. Object Mentor was a software consultancy founded by Martin, and the other Object Mentors (Jeff Langr, Tim Ottinger and others) also contributed to this book.

The book can be divided into three main parts. The first part explains what clean code is and why we should strive for it, as well as explaining how it applies to specific subjects like functions, classes, comments and formatting. The second part takes you through a couple of large-scale, step-by-step refactorings of real code, showing how clean code applies in practice. This is probably the most valuable part of the book. The third part is a catalogue of code smells for reference, where each item is basically a short refresher of something covered in the previous two parts.

Clean code can be described in many ways, but essentially it is code that is readable, flexible and maintainable, or in other words, easy to change. I think the rules, code smells and heuristics contained within this book are pretty good at helping us to achieve that. 

### Clean Architecture

A really interesting look at how to design software well. The book starts by explaining the point of software architecture/design. Part II explains the implications of programming paradigms (structured, object-oriented, functional) on architecture. Part III explains the SOLID principles, which apply to modules (classes in OOP), and Part IV covers some component principles, which apply to components (groups of modules). Part V justifies the Clean Architecture and describes its ingredients. Part VI explains how databases, the web and frameworks fit into the Clean Architecture (hint: they're details which belong in the outer circle of the Clean Architecture i.e. your domain code should not depend on them). The last part of the book is a brief autobiography of some of Martin's projects from the 1960s to the 1990s which vindicate some of his architectural principles.

The "Clean Architecture" is similar to Ports & Adapters, Hexagonal Architecture and Onion Architecture. I think it's a good architecture for large projects to avoid becoming big balls of mud. Probably overkill for a small project, but still useful to keep in mind as your project grows.

I particularly liked Martin's idea of the "screaming architecture", that "the architecture of a software application [should] scream about the use cases of the application", instead of being about controllers, services, repositories, entities...

I also enjoyed Simon Brown's chapter about actually implementing the Clean Architecture (or something similar to it), and James Grenning's chapter on using the Clean Architecture in embedded software.

### Building a Career in Software: A Comprehensive Guide to Success in the Software Industry

This is a solid book for beginner software engineers. Covers a lot of important professional skills that I haven't seen in similar books. This book is like having a really good mentor. Lots of very practical advice.

Most of the book relates to non-tech skills, like managing projects, working with others, and writing emails. There's also some coverage of job search skills (writing CVs, interviews) and technical skills (coding, debugging, designing reliable systems). 

### Modern Software Engineering

I think this book is worthy of its title. It sets out to define an engineering approach to software development and I think it succeeds. The book distills a huge number of important concepts in software development in a very cohesive and accessible way, while remaining paradigm-agnostic.

Farley posits that there are two main focuses in software engineering. The first is learning. The second is managing complexity. Learning essentially refers to the iterative, agile approach to building software. Managing complexity is how we retain our ability to change and iterate software without our systems becoming big balls of mud. Iteration, feedback, incrementalism, experimentation and empiricism are linked to our ability to learn; modularity, cohesion, separation of concerns, abstraction and loose coupling are linked to our ability to manage complexity.

Drawing from Accelerate, Farley puts forward stability and throughput as the two basic measures of an effective software engineering team. These measures provide further justification for the tools and techniques that he describes for optimising learning and managing complexity. 

### Head First Design Patterns

This is a great book not just on design patterns but also the object-oriented design principles that underlie them.

Each pattern is explained thoroughly with text and annotated diagrams. Complexity is built up gradually with each step being explained and justified. Questions are anticipated and answered satisfactorily.

Every pattern is explained in the context of the object-oriented design principles that are introduced alongside them.

It covers a selection of the most important patterns from the original Design Patterns book.

The style is irreverent and the text is relatively light and digestible but the concepts are heavy.

### Extreme Programming Explained: Embrace Change

This book describes the values of Extreme Programming, the principles that follow from these values, and the practices which align with these principles. It also expounds the philosophy of XP: where the ideas came from and why it works.

Beck describes a workplace which sounds almost utopian but is actually quite realistic and attainable. A fulfilling place to work that also fulfils the needs of the business.

XP largely focuses on how developers should work together, with less emphasis on the organisational structure or project/product management than e.g. Scrum. I think the ideas are sometimes less concrete but often more widely applicable than Scrum.

I think the ideas in this book are still highly relevant for helping us to build better software faster, more cheaply with fewer defects. Even if many of the practices are now fairly common, it’s useful to think about the justification for them so that we can practice them effectively. The values and principles of XP also help us to evaluate new practices.

In my experience, our industry is far from the ideal described in this book. I hope that reading this will help me to make some positive change. I’m sure if everyone read this and applied it, our industry would be far better off, for us developers, our employers and our customers.

### Effective Java

This book contains 90 items of more or less concrete advice for writing better Java, i.e. Java that is more readable, easier to change, more performant or less error-prone. Bloch explains common pitfalls and gives various solutions that fit different situations.

Important sentences are bolded for easy skim-reading, and most items have a summary paragraph at the end for easy recap.

This is not a book for beginners. General programming and Java knowledge are prerequisites (Bloch recommends Java Precisely) and it would probably be best to have some experience writing Java professionally or in a side project.

A lot of the advice is transferable to other languages, but most is specific to the quirks of Java.

### The Pragmatic Programmer

Good, general advice for software development. 

### Growing Object-Oriented Software, Guided by Tests

A comprehensive explanation and demonstration of how to do test-driven development in a way that helps produce well-designed object oriented software. In particular, they cover the use of mocks to drive discovery of new roles (i.e. interfaces) in your program.

Their version of TDD starts every new feature with an acceptance test which exercises the whole application. This is followed by unit tests and units of functionality to make the acceptance test pass.

I think this is an improvement on some people's idea of TDD, in which you might start with unit tests for individual units of functionality and only test those units together at the end. The method in this book involves adding vertical slices of functionality that pass through every layer of the application, rather than taking a bottom-up or top-down approach where you write the application layer by layer.

I've personally applied this approach to projects and found that it has led to much higher quality software, at least in my opinion. Starting with a vertical slice of functionality through your software gets the hard part out of the way as early as possible (i.e. your whole build and deployment pipeline) so that for subsequent features you can simply build upon the existing skeleton.

The first two parts of the book explain the theory of TDD. The third part contains a fairly long worked example which shows how TDD can deal with complex software, not just a toy example. Part four contains guidelines for writing tests which are maintanable and useful over time, and part five gives solutions for testing pain-points (persistence, threads and asynchrony).

### Apprenticeship Patterns

I don't find the analogy between software engineering and medieval craftsmanship to be very compelling or useful, but the advice in the book is still very worthwhile.

### Spring Start Here

As a junior Java developer just starting with Spring, I found this book extremely helpful in dispelling some of the magic of Spring.

It begins by explaining what Spring is: the Spring framework itself vs the Spring ecosystem including Spring Boot. The book then covers the fundamentals of the Spring framework: the context, beans, annotations, dependency injection and aspect-oriented programming. Further chapters explore other useful parts of the Spring ecosystem like Spring Boot, Spring Web and Spring Data.

Code examples are thoroughly explained in the text, supplemented by diagrams illustrating behaviour. All the code in the book is available online, with snapshots for every section to illustrate each technique.

Appendices cover related topics (such as architectural approaches and HTTP) in enough detail to understand the main text if you're unfamiliar.

### Real–World Software Development: A Project-Driven Guide to Fundamentals in Java

Gives a high-level overview of various principles (e.g. SOLID), patterns (e.g. Builder) and practices (e.g. TDD) that make for good software. The project-based approach, building a semi-realistic application, shows how each topic applies in practice. Although each topic isn't covered in deep detail, there is enough to build a working knowledge and to stimulate further research.

### Letters To A New Developer

Many short essays, styled as letters, containing advice for new developers.

### Practical Object-Oriented Design: An Agile Primer Using Ruby

Shows how the SOLID principles apply in practice in Ruby, as well as: how to manage dependencies with dependency injection; when to use classical inheritance vs modules vs composition/aggregation; how to implement common interfaces across multiple classes (duck typing); and how to design cost-effective tests.

### Don't Make Me Think, Revisited: A Common Sense Approach to Web Usability

Common-sense guidance for web usability.

### Grokking Algorithms An Illustrated Guide For Programmers and Other Curious People

An interesting, illustrated guide to some fundamental algorithms and algorithmic concepts.

### Your First Year in Code

Advice from experienced programmers for getting through the initial stages of your development career.
