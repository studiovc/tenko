# Tenko parser test case

- Path: tests/testcases/for_statement/should_not_over_accept_an_60of60_after_an_60in60_1.md

> :: for statement
>
> ::> should not over accept an 60of60 after an 60in60 1

## Input

`````js
for (x in y of) ;
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in five parsing modes: sloppy, sloppy+annexb, strict script, module, module+annexb.

Note that the output parts are auto-generated by the test runner to reflect actual result.

### Sloppy mode

Parsed with script goal and as if the code did not start with strict mode header.

`````
throws: Parser error!
  Missing closing paren of the `for` header, found `of` instead

start@1:0, error@1:12
╔══╦═════════════════
 1 ║ for (x in y of) ;
   ║             ^^------- error
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
