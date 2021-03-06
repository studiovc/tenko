# Tenko parser test case

- Path: tests/testcases/for_statement/for-of/let_as_a_var/let_with_an_array_that_cannot_be_a_pattern_is_not_allowed_in_for-of.md

> :: for statement : for-of : let as a var
>
> ::> let with an array that cannot be a pattern is not allowed in for-of
>
> fails in strict because let is a keyword there, fails in sloppy because the array cant be a pattern

## Input

`````js
for (let[a+b] of x);
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in five parsing modes: sloppy, sloppy+annexb, strict script, module, module+annexb.

Note that the output parts are auto-generated by the test runner to reflect actual result.

### Sloppy mode

Parsed with script goal and as if the code did not start with strict mode header.

`````
throws: Parser error!
  The binding pattern is not destructible

start@1:0, error@1:14
╔══╦═════════════════
 1 ║ for (let[a+b] of x);
   ║               ^^------- error
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
