# Tenko parser autogenerated test case

- From: tests/testcases/yield/arrow_piggy/autogen.md
- Path: tests/testcases/yield/arrow_piggy/gen/test/async_287ba_3d_yield_b7d29.md

> :: yield : arrow piggy : gen : test
>
> ::> async 287ba 3d yield b7d29

## Input


`````js
async ({a = yield b})
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in four parsing modes: sloppy mode, strict mode script goal, module goal, web compat mode (always sloppy).

Note that the output parts are auto-generated by the test runner to reflect actual result.

### Sloppy mode

Parsed with script goal and as if the code did not start with strict mode header.

`````
throws: Parser error!
  Expected the closing curly `}` for an object, found `b` instead

start@1:0, error@1:18
╔══╦═════════════════
 1 ║ async ({a = yield b})
   ║                   ^------- error
╚══╩═════════════════

`````

### Strict mode

Parsed with script goal but as if it was starting with `"use strict"` at the top.

`````
throws: Parser error!
  Cannot use `yield` outside of generator functions when in strict mode

start@1:0, error@1:12
╔══╦═════════════════
 1 ║ async ({a = yield b})
   ║             ^^^^^------- error
╚══╩═════════════════

`````


### Module goal

Parsed with the module goal.

_Output same as strict mode._

### Web compat mode

Parsed in sloppy script mode but with the web compat flag enabled.

_Output same as sloppy mode._