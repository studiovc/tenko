# Tenko parser test case

- Path: tests/testcases/optional_chaining/template_nl.md

> :: optional chaining
>
> ::> template nl
>
> This is explicitly illegal because the tagged template case is considered an ASI footgun
>
> Note: this is ``LeftHandSideExpression : OptionalChain : `?.` TemplateLiteral``

## FAIL

## Input

`````js
a?.
`foo`
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in five parsing modes: sloppy, sloppy+annexb, strict script, module, module+annexb.

Note that the output parts are auto-generated by the test runner to reflect actual result.

### Sloppy mode

Parsed with script goal and as if the code did not start with strict mode header.

`````
throws: Parser error!
  An value containing the optional chaining operator cannot be followed by a template

start@1:0, error@2:0
╔══╦════════════════
 1 ║ a?.
 2 ║ `foo`
   ║ ^^^^^------- error
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