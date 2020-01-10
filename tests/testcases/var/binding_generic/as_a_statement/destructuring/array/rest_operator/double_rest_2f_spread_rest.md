# Tenko parser test case

- Path: tests/testcases/var/binding_generic/as_a_statement/destructuring/array/rest_operator/double_rest_2f_spread_rest.md

> :: var : binding generic : as a statement : destructuring : array : rest operator
>
> ::> double rest 2f spread rest

## Input

`````js
var [... ...foo] = obj;
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in four parsing modes: sloppy mode, strict mode script goal, module goal, web compat mode (always sloppy).

Note that the output parts are auto-generated by the test runner to reflect actual result.

### Sloppy mode

Parsed with script goal and as if the code did not start with strict mode header.

`````
throws: Parser error!
  Can not rest twice

start@1:0, error@1:5
╔══╦════════════════
 1 ║ var [... ...foo] = obj;
   ║      ^^^^^^^------- error
╚══╩════════════════

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