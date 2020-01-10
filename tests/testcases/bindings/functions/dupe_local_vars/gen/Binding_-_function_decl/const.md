# Tenko parser autogenerated test case

- From: tests/testcases/bindings/functions/dupe_local_vars/autogen.md
- Path: tests/testcases/bindings/functions/dupe_local_vars/gen/Binding_-_function_decl/const.md

> :: bindings : functions : dupe local vars : gen : Binding - function decl
>
> ::> const

## Input


`````js
function g(){ const f = 1; function f() {} }
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in four parsing modes: sloppy mode, strict mode script goal, module goal, web compat mode (always sloppy).

Note that the output parts are auto-generated by the test runner to reflect actual result.

### Sloppy mode

Parsed with script goal and as if the code did not start with strict mode header.

`````
throws: Parser error!
  Found a var binding that is duplicate of a lexical binding on the same or lower statement level

start@1:0, error@1:36
╔══╦═════════════════
 1 ║ function g(){ const f = 1; function f() {} }
   ║                                     ^------- error
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