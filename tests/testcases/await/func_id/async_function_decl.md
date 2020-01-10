# Tenko parser test case

- Path: tests/testcases/await/func_id/async_function_decl.md

> :: await : func id
>
> ::> async function decl

## Input

`````js
async function await(){}
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in four parsing modes: sloppy mode, strict mode script goal, module goal, web compat mode (always sloppy).

Note that the output parts are auto-generated by the test runner to reflect actual result.

### Sloppy mode

Parsed with script goal and as if the code did not start with strict mode header.

`````
ast: {
  type: 'Program',
  loc:{start:{line:1,column:0},end:{line:1,column:24},source:''},
  body: [
    {
      type: 'FunctionDeclaration',
      loc:{start:{line:1,column:0},end:{line:1,column:24},source:''},
      generator: false,
      async: true,
      id: {
        type: 'Identifier',
        loc:{start:{line:1,column:15},end:{line:1,column:20},source:''},
        name: 'await'
      },
      params: [],
      body: {
        type: 'BlockStatement',
        loc:{start:{line:1,column:22},end:{line:1,column:24},source:''},
        body: []
      }
    }
  ]
}

tokens (8x):
       ID_async ID_function ID_await PUNC_PAREN_OPEN PUNC_PAREN_CLOSE
       PUNC_CURLY_OPEN PUNC_CURLY_CLOSE
`````

### Strict mode

Parsed with script goal but as if it was starting with `"use strict"` at the top.

_Output same as sloppy mode._

### Module goal

Parsed with the module goal.

`````
throws: Parser error!
  Cannot use this name (`await`) as a variable name because: Await is illegal as var name with module goal

start@1:0, error@1:15
╔══╦═════════════════
 1 ║ async function await(){}
   ║                ^^^^^------- error
╚══╩═════════════════

`````


### Web compat mode

Parsed in sloppy script mode but with the web compat flag enabled.

_Output same as sloppy mode._

## AST Printer

Printer output different from input [sloppy]:

````js
async function await() {}
````

Produces same AST