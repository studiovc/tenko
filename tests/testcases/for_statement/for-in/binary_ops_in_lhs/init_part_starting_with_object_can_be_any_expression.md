# Tenko parser test case

- Path: tests/testcases/for_statement/for-in/binary_ops_in_lhs/init_part_starting_with_object_can_be_any_expression.md

> :: for statement : for-in : binary ops in lhs
>
> ::> init part starting with object can be any expression

## Input

`````js
for ({} + b in obj);
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in five parsing modes: sloppy, sloppy+annexb, strict script, module, module+annexb.

Note that the output parts are auto-generated by the test runner to reflect actual result.

### Sloppy mode

Parsed with script goal and as if the code did not start with strict mode header.

`````
throws: Parser error!
  Unknown input followed the left side of a for loop header

start@1:0, error@1:18
╔══╦═════════════════
 1 ║ for ({} + b in obj);
   ║                   ^------- error
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
