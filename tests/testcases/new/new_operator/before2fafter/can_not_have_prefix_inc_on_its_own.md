# Tenko parser test case

- Path: tests/testcases/new/new_operator/before2fafter/can_not_have_prefix_inc_on_its_own.md

> :: new : new operator : before2fafter
>
> ::> can not have prefix inc on its own

## Input

`````js
++new x()
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in four parsing modes: sloppy mode, strict mode script goal, module goal, web compat mode (always sloppy).

Note that the output parts are auto-generated by the test runner to reflect actual result.

### Sloppy mode

Parsed with script goal and as if the code did not start with strict mode header.

`````
throws: Parser error!
  Can only increment or decrement an identifier or member expression (at EOF)

start@1:0, error@1:9
╔══╦════════════════
 1 ║ ++new x()
   ║          ^------- error at EOF
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