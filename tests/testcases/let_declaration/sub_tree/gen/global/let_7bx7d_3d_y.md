# Tenko parser autogenerated test case

- From: tests/testcases/let_declaration/sub_tree/autogen.md
- Path: tests/testcases/let_declaration/sub_tree/gen/global/let_7bx7d_3d_y.md

> :: let declaration : sub tree : gen : global
>
> ::> let 7bx7d 3d y

## Input


`````js
let {x} = y
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
  loc:{start:{line:1,column:0},end:{line:1,column:11},source:''},
  body: [
    {
      type: 'VariableDeclaration',
      loc:{start:{line:1,column:0},end:{line:1,column:11},source:''},
      kind: 'let',
      declarations: [
        {
          type: 'VariableDeclarator',
          loc:{start:{line:1,column:4},end:{line:1,column:11},source:''},
          id: {
            type: 'ObjectPattern',
            loc:{start:{line:1,column:4},end:{line:1,column:7},source:''},
            properties: [
              {
                type: 'Property',
                loc:{start:{line:1,column:5},end:{line:1,column:6},source:''},
                key: {
                  type: 'Identifier',
                  loc:{start:{line:1,column:5},end:{line:1,column:6},source:''},
                  name: 'x'
                },
                kind: 'init',
                method: false,
                computed: false,
                value: {
                  type: 'Identifier',
                  loc:{start:{line:1,column:5},end:{line:1,column:6},source:''},
                  name: 'x'
                },
                shorthand: true
              }
            ]
          },
          init: {
            type: 'Identifier',
            loc:{start:{line:1,column:10},end:{line:1,column:11},source:''},
            name: 'y'
          }
        }
      ]
    }
  ]
}

tokens (8x):
       ID_let PUNC_CURLY_OPEN IDENT PUNC_CURLY_CLOSE PUNC_EQ IDENT ASI
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

## AST Printer

Printer output different from input [sloppy]:

````js
let {x} = y;
````

Produces same AST