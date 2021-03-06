# Tenko parser test case

- Path: tests/testcases/string/escapes/nondirectives/start/octal/escape_9.md

> :: string : escapes : nondirectives : start : octal
>
> ::> escape 9
>
> Only zero is special to escape

## Input

`````js
debugger;
'\9';
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in five parsing modes: sloppy, sloppy+annexb, strict script, module, module+annexb.

Note that the output parts are auto-generated by the test runner to reflect actual result.

### Sloppy mode

Parsed with script goal and as if the code did not start with strict mode header.

`````
throws: Lexer error!
    The grammar does not allow to escape the 8 or the 9 character

start@1:0, error@2:0
╔══╦════════════════
 1 ║ debugger;
 2 ║ '\9';
   ║ ^^^^------- error
╚══╩════════════════

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
