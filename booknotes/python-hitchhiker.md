# 阅读《Python hitchhiker》笔记

wp_id: 343
Status: publish
Date: 2018-06-22 09:06:00
Modified: 2020-05-16 11:13:01

## Package

A file modu.py in the directory pack/ is imported with the statement import pack.modu. This statement will look for an `__init__.py` file in pack, execute all of its top-level statements. Then it will look for a file named pack/modu.py and execute all of its top-level statements. After these operations, any variable, function, or class defined in modu.py is available in the pack.modu namespace.

A commonly seen issue is to add too much code to `__init__.py` files. When the project complexity grows, there may be sub-packages and sub-sub-packages in a deep directory structure. In this case, importing a single item from a sub-sub-package will require executing all `__init__.py` files met while traversing the tree.

This and other issues led to the idea that using stateless functions is a better programming paradigm.

Another way to say the same thing is to suggest using functions and procedures with as few implicit contexts and side-effects as possible. A function’s implicit context is made up of any of the global variables or items in the persistence layer that are accessed from within the function. Side-effects are the changes that a function makes to its implicit context. If a function saves or deletes data in a global variable or in the persistence layer, it is said to have a side-effect.

## Pure functions

- Pure functions are deterministic: given a fixed input, the output will always be the same.
- Pure functions are much easier to change or replace if they need to be refactored or optimized.
- Pure functions are easier to test with unit-tests: There is less need for complex context setup and data cleaning afterwards.
- Pure functions are easier to manipulate, decorate, and pass around.

However, it may be a good discipline to avoid assigning to a variable more than once, and it helps in grasping the concept of mutable and immutable types.

- A LICENSE file should always be present and specify the license under which the software is made available to the public.
- A TODO file or a TODO section in README should list the planned development for the code.
- A CHANGELOG file or section in README should compile a short overview of the changes in the code base for the latest versions.
- Project Publication

Depending on the project, your documentation might include some or all of the following components:

- An introduction should show a very short overview of what can be done with the product, using one or two extremely simplified use cases. This is the thirty-second pitch for your project.
- A tutorial should show some primary use cases in more detail. The reader will follow a step-by-step procedure to set-up a working prototype.
- An API reference is typically generated from the code (see docstrings). It will list all publicly available interfaces, parameters, and return values.
- Developer documentation is intended for potential contributors. This can include code convention and general design strategy of the project.

put project/ tests/ docs/ directory in side the project