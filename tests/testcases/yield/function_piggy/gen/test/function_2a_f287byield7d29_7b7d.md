# Tenko parser autogenerated test case

- From: tests/testcases/yield/function_piggy/autogen.md
- Path: tests/testcases/yield/function_piggy/gen/test/function_2a_f287byield7d29_7b7d.md

> :: yield : function piggy : gen : test
>
> ::> function 2a f287byield7d29 7b7d

## Input


`````js
function * f({yield}) {}
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in four parsing modes: sloppy mode, strict mode script goal, module goal, web compat mode (always sloppy).

Note that the output parts are auto-generated by the test runner to reflect actual result.

### Sloppy mode

Parsed with script goal and as if the code did not start with strict mode header.

`````
throws: Parser error!
  Cannot use this name (`yield`) as a variable name because: Cannot use this reserved word as a variable name inside a generator

start@1:0, error@1:14
╔══╦═════════════════
 1 ║ function * f({yield}) {}
   ║               ^^^^^------- error
╚══╩═════════════════

`````

### Strict mode

Parsed with script goal but as if it was starting with `"use strict"` at the top.

`````
throws: Parser error!
  Cannot use this name (`yield`) as a variable name because: Cannot use this reserved word as a variable name in strict mode

start@1:0, error@1:14
╔══╦═════════════════
 1 ║ function * f({yield}) {}
   ║               ^^^^^------- error
╚══╩═════════════════

`````


### Module goal

Parsed with the module goal.

_Output same as strict mode._

### Web compat mode

Parsed in sloppy script mode but with the web compat flag enabled.

_Output same as sloppy mode._