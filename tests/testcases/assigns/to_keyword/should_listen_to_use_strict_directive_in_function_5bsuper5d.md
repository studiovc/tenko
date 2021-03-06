# Tenko parser test case

- Path: tests/testcases/assigns/to_keyword/should_listen_to_use_strict_directive_in_function_5bsuper5d.md

> :: assigns : to keyword
>
> ::> should listen to use strict directive in function 5bsuper5d

## Input

`````js
function f() { "use strict"; (super = "sentinal 79845134"); }
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in five parsing modes: sloppy, sloppy+annexb, strict script, module, module+annexb.

Note that the output parts are auto-generated by the test runner to reflect actual result.

### Sloppy mode

Parsed with script goal and as if the code did not start with strict mode header.

`````
throws: Parser error!
  The `super` keyword can only be used as call or member expression

start@1:0, error@1:30
╔══╦═════════════════
 1 ║ function f() { "use strict"; (super = "sentinal 79845134"); }
   ║                               ^^^^^------- error
╚══╩═════════════════

`````

### Strict mode

Parsed with script goal but as if it was starting with `"use strict"` at the top.

_Output same as sloppy mode._

### Module goal

Parsed with the module goal.

_Output same as sloppy mode._

### Sloppy mode with AnnexB

Parsed with script goal with AnnexB rules enabled and as if the code did not start with strict mode header.

_Output same as sloppy mode._

### Module goal with AnnexB

Parsed with the module goal with AnnexB rules enabled.

_Output same as sloppy mode._
