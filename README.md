- :wave: Hi, I’m Rob.
- :office: I'm currently working as a software developer at Capgemini.
- :coffee: I write Java with Spring, deployed on Kubernetes with GitLab CI/CD.
- :sparkling_heart: I love agile/XP development practices like test-driven development, pairing and mobbing, continuous integration/delivery.
- :books: I read a lot and try to apply it to my work (see my [bookshelf](#bookshelf)).
- :man_student: I graduated from Makers web development bootcamp July 2021.
- :link: [LinkedIn](https://www.linkedin.com/in/robert-dupplaw/), [Twitter](https://twitter.com/robert_dupplaw), [Blog](https://write.as/rdupplaw/).

## Bookshelf

In descending order of date read.

### Clean Architecture

*in progress*

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
