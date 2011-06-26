Gull
====

<https://github.com/jeremybanks/gull>

Gull will be a Lisp-style language with compilers in and compiling to Python 2.5+, PHP 5.3+ and ECMAScript 3+. The Python compiler and PHP target are being developed first.

Syntax
------

The syntax tree is entirely s-expressions, but various sugars are available.

- List and map literals: `[1 2 3]`, `{"foo": 4, "bar": 6}`
- List and map lookup: `x[1]`, `bar["foo"]`
- Splats: `(fn [first rest...] (first rest...))`
- Attributes/methods: `(foo.bar foo.bat)`
- "` \t\n\r:,`" are whitespace.
- Any otherwise unused characters can be used as identifiers.

Macros
------

The macro system will be good. Probably more powerful than Lisp's, in order to handle the multiple target languages effectively.

Components
----------

- Interpreter for Gull, in each target language: parses and executes Gull code; Implements the language core in the target language.
- Standard Library in Gull: macros and functions building on those provided by the interpreter core.
- Compiler, for each target language, in Gull: macros and functions to convert Gull code to the target language.
