AirBnB clone - The console

The travel and accommodation industry has undergone a remarkable transformation with the advent of online platforms. Airbnb, a pioneering company in the sharing economy, has revolutionized the way people travel and connect with local hosts around the world


The project is a hands-on practice showing the implementation of all the fundamental concepts covered in the Alx high-level programming track.

This console is a command interpreter to manipulate data without a visual interface, like in a shell (perfect for development and debugging).


CONTENT
After 4 months

A command interpreter to manipulate data without a visual interface, like in a Shell (perfect for development and debugging)
A website (the front-end) that shows the final product to everybody: static and dynamic
A database or files that store data (data = objects)
An API that provides a communication interface between the front-end and your data (retrieve, create, delete, update them)

Concepts to learn
Unittest - and please work all together on tests cases
Python packages concept page
Serialization/Deserialization
*args, **kwargs
datetime

Overview of  Console
The console
create your data model
manage (create, update, destroy, etc) objects via a console / command interpreter
store and persist objects to a file (JSON file)
The first piece is to manipulate a powerful storage system. This storage engine will give us an abstraction between “My object” and “How they are stored and persisted”. This means: from your console code (the command interpreter itself) and from the front-end and RestAPI you will build later, you won’t have to pay attention (take care) of how your objects are stored.

This abstraction will also allow you to change the type of storage easily without updating all of your codebase.

The console will be a tool to validate this storage engine

Files and Directories
models directory will contain all classes used for the entire project. A class, called “model” in a OOP project is the representation of an object/instance.
tests directory will contain all unit tests.
console.py file is the entry point of our command interpreter.
models/base_model.py file is the base class of all our models. It contains common elements:
attributes: id, created_at and updated_at
methods: save() and to_json()
models/engine directory will contain all storage classes (using the same prototype). For the moment you will have only one: file_storage.py.


Storage
Persistency is really important for a web application. It means: every time your program is executed, it starts with all objects previously created from another execution. Without persistency, all the work done in a previous execution won’t be saved and will be gone.

In this project, you will manipulate 2 types of storage: file and database. For the moment, you will focus on file.

Why separate “storage management” from “model”? It’s to make your models modular and independent. With this architecture, you can easily replace your storage system without re-coding everything everywhere.

You will always use class attributes for any object. Why not instance attributes? For 3 reasons:

Provide easy class description: everybody will be able to see quickly what a model should contain (which attributes, etc…)
Provide default value of any attribute
In the future, provide the same model behavior for file storage or database storage



Main Concepts to familiarize ourselves with:
Cmd Module: It is designed or used as a base class for command interpreters like the console application we are building. What does this entail? By default, the Cmd module uses the readline library to provide functionality for handling user input from the console. A few of the features and functionalities provided by the readline library are listed below:
-> Interactive prompt handling: readline allows the shell to display a prompt to the user, indicating that the shell is ready to accept input. The user can then type a command or other input, which the shell will interpret and execute.

-> Command line editing: readline provides functionality for editing the current command line (i.e., the line of text currently being entered by the user), including features such as moving the cursor, deleting characters, and inserting text.

-> Command completion: readline can also provide tab-completion functionality, which suggests possible completions for the current command or argument based on previously entered commands or other contextual information.
uuid module: Uuid stands for "Universally Unique Identifier." It's a 128-bit identifier that is unique across both space and time. What this entails is that, when we implement it, we will be able to generate hexadecimal digits (959902c6-6bc1-46c9-8b78-e93d6d67aa8c) that are unique across space and time, and the probability of two UUIDs being the same is so low as being impossible. These digits are the ID we will use to identify our objects, and at some point in the project we will have a database, so we need something to uniquely identify the data in each row in our database.

dateTime module: The datetime module supplies us with classes for manipulating dates and times.

*args and **kwags:
These are special parameters in Python, they are arbitrary arguments used when we are unsure of the number of arguments we will pass into our function. 
 *args is for multiple numbers of positional arguments that will be parsed in later, maybe during instantiation (creation of object) in classes, while **kwags is for multiple numbers of keyworded or key-value paired arguments that will be parsed later,

Python packages:
Python package is just a directory with a collection of different modules. A module is simply a .py file (your regular Python file) containing your Python code which might be made up of certain defined functions for a specific task. If we have one or more of these files in a directory, the directory in question is now a package. but it becomes a package only by us adding an empty __init__.py file in that directory.
we import a module or function from a package, by using the dot notation. For example, if I have a module called mymodule inside a package called mypackage, I can import it like this: from mypackage import mymodule. Alternatively, I can use the import statement followed by the package and module names, separated by dots: import mypackage.mymodule. Remember that mypackagehere is the directory containing my modules. I can also import specific functions from a module using the from keyword. For example, to import a function called myfunc from mymodule, I can use: from mypackage.mymodule import myfunc.

unit testing: unit testing is a valuable tool for any software development, although it's not without its challenges and can be time-consuming. but this ensures correctness because, by testing individual functions and methods, you can catch errors and bugs before they make it to a more delicate stage of your application development where things might become more complex to figure out.
