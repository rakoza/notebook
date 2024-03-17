# PSALM

https://psalm.dev/

https://github.com/vimeo/psalm

Psalm is a static analysis tool that attempts to dig into your program and find as many type-related bugs as possible.

It has a few features that go further than other similar tools:

**Mixed type warnings**

If Psalm cannot infer a type for an expression then it uses a mixed placeholder type. mixed types can sometimes mask bugs, so keeping track of them helps you avoid a number of common pitfalls.

**Intelligent logic checks**

Psalm keeps track of logical assertions made about your code, so if ($a && $a) {} and if ($a && !$a) {} are both treated as issues. Psalm also keeps track of logical assertions made in prior code paths, preventing issues like if ($a) {} elseif ($a) {}.

**Property initialisation checks**

Psalm checks that all properties of a given object have values after the constructor is called.

**Taint analysis**

Psalm can detect security vulnerabilities in your code.

**Language Server**

Psalm has a Language Server that’s compatible with a range of different IDEs.

**Automatic fixes**

Psalm can fix many of the issues it finds automatically.

**Automatic refactoring**

Psalm can also perform simple refactors from the command line.


