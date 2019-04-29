# Python:
- https://docs.python.org/2/faq/design.html#how-are-dictionaries-implemented
- Python Objects and Class
    - Constructors in Python: `__init__()`
- There are 33 keywords in Python 3.3
- decorators:
    - A decorator takes in a function, adds some functionality and returns it.
- closure:
    - `nonlocal` variable declaration.
    - Technique by which some data ("Hello") gets attached to the code is called closure in Python.
    - Decorators in Python make an extensive use of closures as well.
- Copy in Python:
    - Difference between *deep_copy* and *shallow_copy*?
    - Copy Module: `import copy`
    - Shallow Copy:
        -  The new_list contains references to original nested objects stored in `old_list`.
        -  However, when you change any nested objects in `old_list`, the changes appear in `new_list`.
    - Deep Copy:
        - A deep copy creates a new object and recursively adds the copies of nested objects present in the original elements.
        - However, if you make changes to any nested objects in original object old_list, you’ll see no changes to the copy new_list.
- Mutable vs Immutable objects
- `assert`: statement is used as debugging tool as it halts the program at the point where an error occurs.
-  A list also has `sort()` method which performs the same way as `sorted()`. Only difference being, `sort()` method doesn't return any value and changes the original list itself.
- `@staticmethod`:
    - create utility methods.
    - prevent overriding at child class.
- Memory Management
    - Memory management in Python involves a private heap containing all Python objects and data structures. The management of this private heap is ensured internally by the Python memory manager. The Python memory manager has different components which deal with various dynamic storage management aspects, like sharing, segmentation, preallocation or caching.
- A directory must contain a file named __init__.py in order for Python to consider it as a package.
- `Exceptions`: try-except-else-finally?
- *intern*:
    - allocating same memory to different variables
    - works well for immutable types like string and not for mutable.
- `del`:
    - `__del__()`: Object destructor. Called when an object is garbage collected.
    -  __del__ method will be called only when the garbage collection kicks in. And this would happens automatically when the reference count of an object becomes zero.
    - del: Decrements reference count
- Why to use?
    - programming language popularity
    - aggregate view shows that Python remains a stable programming language with a growing ecosystem.
    - Python's culture values open source software, community involvement with local, national and international events and teaching to new programmers. 
    - wide array of open source code libraries, package management and ability to work well on platforms other than Windows.
    - https://nothingbutsnark.svbtle.com/how-to-argue-for-pythons-use
- python3:
    - `ayncio`
    - end of `*.pyc`
    - seperate `byte` and `text`
- variable, class and function naming conventions?
- **Comprehensions**
    - a Python language construct for concisely creating data in lists, dictionaries and sets. List comprehensions are included in Python 2 while dictionary and set comprehensions were introduced to the language in Python 3.
- **Anonymous/Lambda Function**
    - `lambda arguments: expression`
    - we generally use it as an argument to a higher-order function (a function that takes in other functions as arguments)
- **Generators**
    - Generator is an iterator that generates one item at a time. A large list of value will take up a lot of memory. Generators are useful in this situation as it generates only one value at a time instead of storing all the values in memory.
    - Generator expressions are similar to list comprehensions. However, they don’t construct list objects. Instead, generator expressions generate values “just in time” like a class-based iterator or generator function would.
    - Once a generator expression has been consumed, it can’t be restarted or reused.
    - Generator expressions are best for implementing simple “ad hoc” iterators. For complex iterators, it’s better to write a generator function or a class-based iterator.
- Python template engines
    - Jinja (Jinja2)
    - Django templating
        - Django templates are different from a project template because they live within a project and are written by the developer to generate output, most commonly HTML.
    - Mako
    - Chameleon
- How to develop custom, complex data structure in python?
- Functional args passing, `*`, `**` etc.
- Better variables, strings concatination strategies
- `import`:
    - https://chrisyeh96.github.io/2017/08/08/definitive-guide-python-imports.html
    - `import`: Module, package, object
    - When a module is imported, Python runs all of the code in the module file
    - When a package is imported, Python runs all of the code in the package’s __init__.py file
    - `sys.path`, `PYTHONPATH`, `$PATH`
    - Python imports are case-sensitive. 
    - Order in which Python searches for modules to import:
        1. Python Standard Library
        2. modules or packages in a directory specified by sys.path
    - Implicit relative imports are only supported in Python 2. They are NOT SUPPORTED IN PYTHON 3.
    - import should be only at beginning of file or intermediate as per requirements?
    - How does python import works? Cyclic import,... etc.
- Which Python `modules` you have used till the date?
    - CSV
    - File
    - Image
    - magic
    - pillow, PIL

    - hashFS
    - Fabric
    - Sphinx
- Does class methods perform slower than standalone functions?
- Why python is performing slow? What are techniques to overcome this issue?
- Python module to benchmark/Profile functions?
- What happen when method from another file is being imported and called? Does it get replaced therein compiled file or what? 
- Multiple, nested import does it slow down performance? Or it is one time time investment till interpritation and compilation?
- what is diff: setup.py vs requirements.txt ?
    - abstract vs concreate dependencies
    - `setup.py` Library or when u want to distribute package of ur repo
- **File**:
    - https://www.programiz.com/python-programming/file-operation
    - https://www.pythonforbeginners.com/cheatsheet/python-file-handling
- WSGI Servers:
    - A Web Server Gateway Interface (WSGI) server implements the web server side of the WSGI interface for running Python web applications.
    - Python community came up with WSGI as a standard interface that modules and containers could implement. WSGI is now the accepted approach for running Python web applications.
    - WSGI container is a separate running process that runs on a different port than your web server
    - Why use WSGI and not just point a web server directly at an application?
        - flexibility:
            - can swap out web stack components 
            - separate choice of framework from choice of web server
        - promote scaling:
            - Serving thousands of requests for dynamic content at once is the domain of WSGI servers, not frameworks.
            - deciding how to communicate requests to an application framework's process.
    - Alternatives: Green Unicorn, uWSGI, mod_wsgi, or gevent
- builtin methods: https://www.programiz.com/python-programming/methods/built-in/filter
- Why to use `import from __future__`
    - A future statement is a directive to the compiler that a particular module should be compiled using syntax or semantics that will be available in a specified future release of Python. The future statement is intended to ease migration to future versions of Python that introduce incompatible changes to the language. It allows use of the new features on a per-module basis before the release in which the feature becomes standard.

- Web frameworks:
    - Pyramid is the most flexible of the three. It can be used for small apps as we've seen here, but it also powers big-name sites like Dropbox. Open Source communities like Fedora choose it for applications like their community badges system, which receives information about events from many of the project's tools to award achievement-style badges to users. One of the most common complaints about Pyramid is that it presents so many options it can be intimidating to start a new project.
    - By far the most popular framework is Django, and the list of sites that use it is impressive. Bitbucket, Pinterest, Instagram, and The Onion use Django for all or part of their sites. For sites that have common requirements, Django chooses very sane defaults and because of this it has become a popular choice for mid- to large-sized web applications.
    - Flask is great for developers working on small projects that need a fast way to make a simple, Python-powered web site. It powers loads of small one-off tools, or simple web interfaces built over existing APIs. Backend projects that need a simple web interface that is fast to develop and will require little configuration often benefit from Flask on the frontend, like jitviewer which provides a web interface for inspecting PyPy just-in-time compiler logs.