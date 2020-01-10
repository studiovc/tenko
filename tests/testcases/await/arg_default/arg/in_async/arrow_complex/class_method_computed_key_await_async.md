# Tenko parser test case

- Path: tests/testcases/await/arg_default/arg/in_async/arrow_complex/class_method_computed_key_await_async.md

> :: await : arg default : arg : in async : arrow complex
>
> ::> class method computed key await async
>
> This fails because `await` is considered a keyword in an async context or the modue goal and the computed key expression runs in the context of the parent function

## FAIL

## Input

`````js
async function f(){
  (fail = class A {[await](){}; "x"(){}}) => {}
}
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in four parsing modes: sloppy mode, strict mode script goal, module goal, web compat mode (always sloppy).

Note that the output parts are auto-generated by the test runner to reflect actual result.

### Sloppy mode

Parsed with script goal and as if the code did not start with strict mode header.

`````
throws: Parser error!
  Expected to parse a value

start@1:0, error@2:25
╔══╦═════════════════
 1 ║ async function f(){
 2 ║   (fail = class A {[await](){}; "x"(){}}) => {}
   ║                          ^------- error
 3 ║ }
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