polyisp
=======

<https://github.com/jeremybanks/polyisp>

A lisp-ish language that compiles to Python, PHP or JavaScript.

The first compiler is being written in Python. I intend to have one in each output language, with a lot of common code written in polyisp itself.

The language values efficient portability over power.

The standard library will be macros mapping to different functions/constructs in different languages.

But this makes them not fist-class... hmm. Have some way to compile it so that when you just attempt to execute the function directly, it uses the built-in, but if you attempt to use it as a value, it wraps it in a function variable?

Maybe this requires a multi-step parsing thing?

In PHP 5.3+, by compiling all functions as classes with `__invoke` and replacing instances of the functions being defined with instances of this class being compiled with all of its closures added as properties...

This could be done somehow. Maybe, in macros, all values have an "evaluate" method. `(foo bar bar)` is treated like `foo(bar.evaluate(), bar.evaluate())`. For most things this would return `self`, but in PHP it could be used to create a value from a built-in function.

Syntax
------

Like S-expressions, but with `[]` and `{}` added. These just map as `[1 2]` to `(__bracket 1 2)`, `{1: 2, 3: 4}` to `(__brace 1 2 3 4)`. `,` and `:` are whitespace.

Function definitions with splats!

In PHP they compile to `func_get_args()`, `array_slice()`d as necessary.
