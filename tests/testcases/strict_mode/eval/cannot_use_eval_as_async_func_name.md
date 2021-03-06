# Tenko parser test case

- Path: tests/testcases/strict_mode/eval/cannot_use_eval_as_async_func_name.md

> :: strict mode : eval
>
> ::> cannot use eval as async func name

## Input

`````js
async function eval() {}
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in five parsing modes: sloppy, sloppy+annexb, strict script, module, module+annexb.

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
        loc:{start:{line:1,column:15},end:{line:1,column:19},source:''},
        name: 'eval'
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
       ID_async ID_function ID_eval PUNC_PAREN_OPEN PUNC_PAREN_CLOSE
       PUNC_CURLY_OPEN PUNC_CURLY_CLOSE
`````

### Strict mode

Parsed with script goal but as if it was starting with `"use strict"` at the top.

`````
throws: Parser error!
  Cannot use this name (`eval`) as a variable name because: Cannot create a binding named `eval` in strict mode

start@1:0, error@1:15
╔══╦═════════════════
 1 ║ async function eval() {}
   ║                ^^^^------- error
╚══╩═════════════════

`````

### Module goal

Parsed with the module goal.

_Output same as strict mode._

### Sloppy mode with AnnexB

Parsed with script goal with AnnexB rules enabled and as if the code did not start with strict mode header.

_Output same as sloppy mode._

### Module goal with AnnexB

Parsed with the module goal with AnnexB rules enabled.

_Output same as strict mode._

## AST Printer

Printer output was same as input [sloppy][annexb:no]
