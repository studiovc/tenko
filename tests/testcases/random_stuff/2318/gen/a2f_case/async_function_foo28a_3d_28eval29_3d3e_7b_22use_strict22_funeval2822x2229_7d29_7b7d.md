# Tenko parser autogenerated test case

- From: tests/testcases/random_stuff/2318/autogen.md
- Path: tests/testcases/random_stuff/2318/gen/a2f_case/async_function_foo28a_3d_28eval29_3d3e_7b_22use_strict22_funeval2822x2229_7d29_7b7d.md

> :: random stuff : 2318 : gen : a2f case
>
> ::> async function foo28a 3d 28eval29 3d3e 7b 22use strict22 funeval2822x2229 7d29 7b7d

## Input


`````js
async function foo(a = (eval) => { "use strict"; funeval("x"); }) {}
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in five parsing modes: sloppy, sloppy+annexb, strict script, module, module+annexb.

Note that the output parts are auto-generated by the test runner to reflect actual result.

### Sloppy mode

Parsed with script goal and as if the code did not start with strict mode header.

`````
throws: Parser error!
  Can only declare use strict if func params are "simple"

start@1:0, error@1:49
╔══╦═════════════════
 1 ║ async function foo(a = (eval) => { "use strict"; funeval("x"); }) {}
   ║                                                  ^^^^^^^------- error
╚══╩═════════════════

`````

### Strict mode

Parsed with script goal but as if it was starting with `"use strict"` at the top.

`````
throws: Parser error!
  The left hand side of the arrow is not destructible so arrow is illegal

start@1:0, error@1:30
╔══╦═════════════════
 1 ║ async function foo(a = (eval) => { "use strict"; funeval("x"); }) {}
   ║                               ^^------- error
╚══╩═════════════════

`````

### Module goal

Parsed with the module goal.

_Output same as strict mode._

### Sloppy mode with AnnexB

Parsed with script goal with AnnexB rules enabled and as if the code did not start with strict mode header.

_Output same as sloppy mode._

### Module goal with AnnexB

Parsed with the module goal with AnnexB rules enabled.

_Output same as strict mode._
