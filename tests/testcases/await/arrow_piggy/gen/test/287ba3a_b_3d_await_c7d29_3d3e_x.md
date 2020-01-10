# Tenko parser autogenerated test case

- From: tests/testcases/await/arrow_piggy/autogen.md
- Path: tests/testcases/await/arrow_piggy/gen/test/287ba3a_b_3d_await_c7d29_3d3e_x.md

> :: await : arrow piggy : gen : test
>
> ::> 287ba3a b 3d await c7d29 3d3e x

## Input


`````js
({a: b = await c}) => x
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in four parsing modes: sloppy mode, strict mode script goal, module goal, web compat mode (always sloppy).

Note that the output parts are auto-generated by the test runner to reflect actual result.

### Sloppy mode

Parsed with script goal and as if the code did not start with strict mode header.

`````
throws: Parser error!
  Expected the closing curly `}` for an object, found `c` instead

start@1:0, error@1:15
╔══╦═════════════════
 1 ║ ({a: b = await c}) => x
   ║                ^------- error
╚══╩═════════════════

`````

### Strict mode

Parsed with script goal but as if it was starting with `"use strict"` at the top.

_Output same as sloppy mode._

### Module goal

Parsed with the module goal.

`````
throws: Parser error!
  Cannot use `await` as var when goal=module but found `await` outside an async function

start@1:0, error@1:15
╔══╦═════════════════
 1 ║ ({a: b = await c}) => x
   ║                ^------- error
╚══╩═════════════════

`````


### Web compat mode

Parsed in sloppy script mode but with the web compat flag enabled.

_Output same as sloppy mode._