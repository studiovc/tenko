# Tenko parser test case

- Path: tests/testcases/regexes/named_capturing_groups/cannot_use_a_name_more_than_once.md

> :: regexes : named capturing groups
>
> ::> cannot use a name more than once

## Input


`````js
/a (?<foo>b) (?<foo>c)/
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in five parsing modes: sloppy, sloppy+annexb, strict script, module, module+annexb.

Note that the output parts are auto-generated by the test runner to reflect actual result.

### Sloppy mode

Parsed with script goal and as if the code did not start with strict mode header.

`````
throws: Lexer error!
    This group name (`foo`) was already used before

start@1:0, error@1:16
╔══╦═════════════════
 1 ║ /a (?<foo>b) (?<foo>c)/
   ║                 ^^^------- error
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
