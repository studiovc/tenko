# Tenko parser autogenerated test case

- From: tests/testcases/var/binding_generic/reserved_words/autogen.md
- Path: tests/testcases/var/binding_generic/reserved_words/gen/export/try.md

> :: var : binding generic : reserved words : gen : export
>
> ::> try

## Input


`````js
export var try = 10;
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in five parsing modes: sloppy, sloppy+annexb, strict script, module, module+annexb.

Note that the output parts are auto-generated by the test runner to reflect actual result.

### Sloppy mode

Parsed with script goal and as if the code did not start with strict mode header.

`````
throws: Parser error!
  The `export` keyword can only be used with the module goal

start@1:0, error@1:0
╔══╦════════════════
 1 ║ export var try = 10;
   ║ ^^^^^^------- error
╚══╩════════════════

`````

### Strict mode

Parsed with script goal but as if it was starting with `"use strict"` at the top.

_Output same as sloppy mode._

### Module goal

Parsed with the module goal.

`````
throws: Parser error!
  Cannot use this name (`try`) as a variable name because: Cannot never use this reserved word as a variable name

start@1:0, error@1:11
╔══╦═════════════════
 1 ║ export var try = 10;
   ║            ^^^------- error
╚══╩═════════════════

`````

### Sloppy mode with AnnexB

Parsed with script goal with AnnexB rules enabled and as if the code did not start with strict mode header.

_Output same as sloppy mode._

### Module goal with AnnexB

Parsed with the module goal with AnnexB rules enabled.

_Output same as module mode._
