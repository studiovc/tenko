# Tenko parser autogenerated test case

- From: tests/testcases/operator_precedent/autogen.md
- Path: tests/testcases/operator_precedent/gen/rest_param_destructuring/a_instanceof_b_2b_c.md

> :: operator precedent : gen : rest param destructuring
>
> ::> a instanceof b 2b c

## Input


`````js
([ ... a instanceof b + c ]) => x
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in four parsing modes: sloppy mode, strict mode script goal, module goal, web compat mode (always sloppy).

Note that the output parts are auto-generated by the test runner to reflect actual result.

### Sloppy mode

Parsed with script goal and as if the code did not start with strict mode header.

`````
throws: Parser error!
  The left hand side of the arrow is not destructible so arrow is illegal

start@1:0, error@1:29
╔══╦═════════════════
 1 ║ ([ ... a instanceof b + c ]) => x
   ║                              ^^------- error
╚══╩═════════════════

`````

### Strict mode

Parsed with script goal but as if it was starting with `"use strict"` at the top.

_Output same as sloppy mode._

### Module goal

Parsed with the module goal.

_Output same as sloppy mode._

### Web compat mode

Parsed in sloppy script mode but with the web compat flag enabled.

_Output same as sloppy mode._