# Tenko parser autogenerated test case

- From: tests/testcases/regexes/regular_expression_disambiguation/keyword_asi_div/autogen.md
- Path: tests/testcases/regexes/regular_expression_disambiguation/keyword_asi_div/keyword_asi_div/with.md

> :: regexes : regular expression disambiguation : keyword asi div : keyword asi div
>
> ::> with
>
> `with` must be followed by `(`

## FAIL

## Input

`````js
with
/x
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in five parsing modes: sloppy, sloppy+annexb, strict script, module, module+annexb.

Note that the output parts are auto-generated by the test runner to reflect actual result.

### Sloppy mode

Parsed with script goal and as if the code did not start with strict mode header.

`````
throws: Parser error!
  Expected to parse an opening paren, found `/`

start@1:0, error@2:0
╔══╦════════════════
 1 ║ with
 2 ║ /x
   ║ ^------- error
╚══╩════════════════

`````

### Strict mode

Parsed with script goal but as if it was starting with `"use strict"` at the top.

`````
throws: Parser error!
  The `with` statement is not allowed in strict mode

start@1:0, error@1:0
╔══╦════════════════
 1 ║ with
   ║ ^^^^------- error
 2 ║ /x
╚══╩════════════════

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
