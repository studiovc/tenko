# Tenko parser test case

- Path: tests/testcases/objects/method_names_can_be_60prototype60/gen_async.md

> :: objects : method names can be 60prototype60
>
> ::> gen async

## Input

`````js
x= { async *prototype(){} }
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
  loc:{start:{line:1,column:0},end:{line:1,column:27},source:''},
  body: [
    {
      type: 'ExpressionStatement',
      loc:{start:{line:1,column:0},end:{line:1,column:27},source:''},
      expression: {
        type: 'AssignmentExpression',
        loc:{start:{line:1,column:0},end:{line:1,column:27},source:''},
        left: {
          type: 'Identifier',
          loc:{start:{line:1,column:0},end:{line:1,column:1},source:''},
          name: 'x'
        },
        operator: '=',
        right: {
          type: 'ObjectExpression',
          loc:{start:{line:1,column:3},end:{line:1,column:27},source:''},
          properties: [
            {
              type: 'Property',
              loc:{start:{line:1,column:5},end:{line:1,column:25},source:''},
              key: {
                type: 'Identifier',
                loc:{start:{line:1,column:12},end:{line:1,column:21},source:''},
                name: 'prototype'
              },
              kind: 'init',
              method: true,
              computed: false,
              value: {
                type: 'FunctionExpression',
                loc:{start:{line:1,column:5},end:{line:1,column:25},source:''},
                generator: true,
                async: true,
                id: null,
                params: [],
                body: {
                  type: 'BlockStatement',
                  loc:{start:{line:1,column:23},end:{line:1,column:25},source:''},
                  body: []
                }
              },
              shorthand: false
            }
          ]
        }
      }
    }
  ]
}

tokens (13x):
       IDENT PUNC_EQ PUNC_CURLY_OPEN ID_async PUNC_STAR IDENT
       PUNC_PAREN_OPEN PUNC_PAREN_CLOSE PUNC_CURLY_OPEN
       PUNC_CURLY_CLOSE PUNC_CURLY_CLOSE ASI
`````

### Strict mode

Parsed with script goal but as if it was starting with `"use strict"` at the top.

_Output same as sloppy mode._

### Module goal

Parsed with the module goal.

_Output same as sloppy mode._

### Sloppy mode with AnnexB

Parsed with script goal with AnnexB rules enabled and as if the code did not start with strict mode header.

_Output same as sloppy mode._

### Module goal with AnnexB

Parsed with the module goal with AnnexB rules enabled.

_Output same as sloppy mode._

## AST Printer

Printer output different from input [sloppy][annexb:no]:

````js
x = {async * prototype(){}};
````

Produces same AST
