# Tenko parser test case

- Path: tests/testcases/objects/destructuring/identifier_properties/a3ab_identifier_check/assign_keyword3dimport.md

> :: objects : destructuring : identifier properties : a3ab identifier check
>
> ::> assign keyword3dimport

## Input

`````js
({ggg: import} = null)
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in four parsing modes: sloppy mode, strict mode script goal, module goal, web compat mode (always sloppy).

Note that the output parts are auto-generated by the test runner to reflect actual result.

### Sloppy mode

Parsed with script goal and as if the code did not start with strict mode header.

`````
throws: Parser error!
  Import keyword only allowed on toplevel or in a dynamic import

start@1:0, error@1:7
╔══╦════════════════
 1 ║ ({ggg: import} = null)
   ║        ^^^^^^------- error
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