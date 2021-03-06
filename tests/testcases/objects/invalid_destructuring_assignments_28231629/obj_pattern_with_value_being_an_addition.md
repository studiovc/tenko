# Tenko parser test case

- Path: tests/testcases/objects/invalid_destructuring_assignments_28231629/obj_pattern_with_value_being_an_addition.md

> :: objects : invalid destructuring assignments 28231629
>
> ::> obj pattern with value being an addition

## Input


`````js
({a: b + c} = [2])
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in five parsing modes: sloppy, sloppy+annexb, strict script, module, module+annexb.

Note that the output parts are auto-generated by the test runner to reflect actual result.

### Sloppy mode

Parsed with script goal and as if the code did not start with strict mode header.

`````
throws: Parser error!
  Tried to destructure something that is not destructible

start@1:0, error@1:12
╔══╦═════════════════
 1 ║ ({a: b + c} = [2])
   ║             ^------- error
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
