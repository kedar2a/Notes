# Programming

- Identifier is the name given to entities like class, functions, variables etc.
+ **Task queues**
    - Task queues manage background work that must be executed outside the usual HTTP request-response cycle.
    - What's the difference between Celeryd and Celerybeat?
        > Celery is the difference between the Celery daemon (celeryd), which executes tasks, Celerybeat, which is a scheduler.
- list all data structures and choose best for problems. Know strengths and weakness of all. 
- Static Site Generator:
    - Why are static site generators useful?
        - Static content files such as HTML, CSS and JavaScript can be served from a content delivery network (CDN) for high scale and low cost. If a statically generated website is hit by high concurrent traffic it will be easily served by the CDN without dropped connections.
        - Python implementations:
            - Pelican
            - Lektor
            - mkDocs
- CDN (Content delivery networks):
    - A content delivery network (CDN) is a third party that stores and serves static files. Amazon CloudFront, Akamai, and Rackspace Cloud Files are examples of CDNs. 
- UML diagrams.
- Commenting:
    - How to comment within code?
    - Apart from PEP standards, standard programming conventions and it's advantages.
- Explicit/hardcoded or dynamic? Adv/Disadv? Long term which approach to follow? What's good for scalable/Large projects?
- How to decide to add a dependecy/plugin in your project?
- What are dirrent ways in which user session can be maintained? Get to know each, along with their adv and disadv.
- What are upcoming newer networking/programming patterns/conventions/flow like webhooks, pubsub protocol.
    - https://business.udemy.com/blog/9-hot-tech-skills-for-2018/
- Tradeoff between: Programming-effort Vs performace with generic coding.
- Decision to use try-catch, if-else? Error, should we raise it? When to raise an error?
- Site customization is a performance hit? Should it be simple and monotonous?
- Authentication, authorization diff? What are different ways to implement authentication? authorization should only be implemented at one end?
- Should we be using our custom code or readymade plugins?
- What are ways to version data?
- How does google handles multiple session from single client?
- Why python is performing slow? What are techniques to overcome this issue?
- Python module to benchmark/Profile functions?
- Authentication for GET/POST from commandline/urls?
- Alternatives to Sphinx
- debugging vs troubleshooting. what's the difference?
- API: standards, conventions, versioning
- Programming paradigmn: http://cs.lmu.edu/~ray/notes/paradigms/
- OOPS:
    - Abstraction.
    - Encapsulation:
        - Encapsulation is an attribute of an object, and it contains all data which is hidden. That hidden data can be restricted to the members of that class.
    - Inheritance:
        - Inheritance is a concept where one class shares the structure and behavior defined in another class
    - Polymorphism.
- Five Basic Programming Elements: https://study.com/academy/lesson/5-basic-elements-of-programming.html
    Programming is somewhat like working with building blocks. Given enough children's toy blocks (and enough time and ingenuity), you can build just about anything with only a few kinds of blocks. The five basic elements in programming are:

    input: getting data and commands into the computer
    output: getting your results out of the computer
    arithmetic: performing mathematical calculations on your data
    conditional: testing to see if a condition is true or false
    looping: cycling through a set of instructions until some condition is met
- Memoization:
    + In computing, memoization or memoisation is an optimization technique used primarily to speed up computer programs by storing the results of expensive function calls and returning the cached result when the same inputs occur again. Memoization has also been used in other contexts (and for purposes other than speed gains), such as in simple mutually recursive descent parsing[1]. Although related to caching, memoization refers to a specific case of this optimization, distinguishing it from forms of caching such as buffering or page replacement.
- Map Reduce:
    + A MapReduce program is composed of a map procedure (or method), which performs filtering and sorting (such as sorting students by first name into queues, one queue for each name), and a reduce method, which performs a summary operation (such as counting the number of students in each queue, yielding name frequencies).
- Lambda Architecture:
    + All data entering the system is dispatched to both the batch layer and the speed layer for processing.
    The batch layer has two functions: (i) managing the master dataset (an immutable, append-only set of raw data), and (ii) to pre-compute the batch views.
    The serving layer indexes the batch views so that they can be queried in low-latency, ad-hoc way.
    The speed layer compensates for the high latency of updates to the serving layer and deals with recent data only.
    Any incoming query can be answered by merging results from batch views and real-time views.
- Kappa Architecture:
    + Kappa Architecture is a software architecture pattern. Rather than using a relational DB like SQL or a key-value store like Cassandra, the canonical data store in a Kappa Architecture system is an append-only immutable log. From the log, data is streamed through a computational system and fed into auxiliary stores for serving.
