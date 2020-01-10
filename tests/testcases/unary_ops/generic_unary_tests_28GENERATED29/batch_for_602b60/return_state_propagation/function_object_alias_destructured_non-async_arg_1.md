# Tenko parser test case

- Path: tests/testcases/unary_ops/generic_unary_tests_28GENERATED29/batch_for_602b60/return_state_propagation/function_object_alias_destructured_non-async_arg_1.md

> :: unary ops : generic unary tests 28GENERATED29 : batch for 602b60 : return state propagation
>
> ::> function object alias destructured non-async arg 1

## Input

`````js
async function f(){   function fh({x: + await x}) {}   }
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in four parsing modes: sloppy mode, strict mode script goal, module goal, web compat mode (always sloppy).

Note that the output parts are auto-generated by the test runner to reflect actual result.

### Sloppy mode

Parsed with script goal and as if the code did not start with strict mode header.

`````
throws: Parser error!
  Expected the closing curly `}` for an object, found `x` instead

start@1:0, error@1:46
╔══╦═════════════════
 1 ║ async function f(){   function fh({x: + await x}) {}   }
   ║                                               ^------- error
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

start@1:0, error@1:46
╔══╦═════════════════
 1 ║ async function f(){   function fh({x: + await x}) {}   }
   ║                                               ^------- error
╚══╩═════════════════

`````


### Web compat mode

Parsed in sloppy script mode but with the web compat flag enabled.

_Output same as sloppy mode._