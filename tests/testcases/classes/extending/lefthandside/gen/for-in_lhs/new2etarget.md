# Tenko parser autogenerated test case

- From: tests/testcases/classes/extending/lefthandside/autogen.md
- Path: tests/testcases/classes/extending/lefthandside/gen/for-in_lhs/new2etarget.md

> :: classes : extending : lefthandside : gen : for-in lhs
>
> ::> new2etarget

## Input


`````js
for (new.target in x) ;
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in four parsing modes: sloppy mode, strict mode script goal, module goal, web compat mode (always sloppy).

Note that the output parts are auto-generated by the test runner to reflect actual result.

### Sloppy mode

Parsed with script goal and as if the code did not start with strict mode header.

`````
throws: Parser error!
  Must be inside/nested a regular function to use `new.target`

start@1:0, error@1:5
╔══╦════════════════
 1 ║ for (new.target in x) ;
   ║      ^^^^------- error
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