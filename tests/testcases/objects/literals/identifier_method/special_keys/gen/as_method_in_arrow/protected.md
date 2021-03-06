# Tenko parser autogenerated test case

- From: tests/testcases/objects/literals/identifier_method/special_keys/autogen.md
- Path: tests/testcases/objects/literals/identifier_method/special_keys/gen/as_method_in_arrow/protected.md

> :: objects : literals : identifier method : special keys : gen : as method in arrow
>
> ::> protected

## Input


`````js
({protected(){}}) => x;
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in five parsing modes: sloppy, sloppy+annexb, strict script, module, module+annexb.

Note that the output parts are auto-generated by the test runner to reflect actual result.

### Sloppy mode

Parsed with script goal and as if the code did not start with strict mode header.

`````
throws: Parser error!
  The left hand side of the arrow is not destructible so arrow is illegal

start@1:0, error@1:18
╔══╦═════════════════
 1 ║ ({protected(){}}) => x;
   ║                   ^^------- error
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
