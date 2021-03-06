# Tenko parser test case

- Path: tests/testcases/var/destructuring_case.md

> :: var
>
> ::> destructuring case

## Input

`````js
var {[2]: y = 1} = {2:3}
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
      type: 'VariableDeclaration',
      loc:{start:{line:1,column:0},end:{line:1,column:24},source:''},
      kind: 'var',
      declarations: [
        {
          type: 'VariableDeclarator',
          loc:{start:{line:1,column:4},end:{line:1,column:24},source:''},
          id: {
            type: 'ObjectPattern',
            loc:{start:{line:1,column:4},end:{line:1,column:16},source:''},
            properties: [
              {
                type: 'Property',
                loc:{start:{line:1,column:5},end:{line:1,column:15},source:''},
                key: {
                  type: 'Literal',
                  loc:{start:{line:1,column:6},end:{line:1,column:7},source:''},
                  value: 2,
                  raw: '2'
                },
                kind: 'init',
                method: false,
                computed: true,
                value: {
                  type: 'AssignmentPattern',
                  loc:{start:{line:1,column:10},end:{line:1,column:15},source:''},
                  left: {
                    type: 'Identifier',
                    loc:{start:{line:1,column:10},end:{line:1,column:11},source:''},
                    name: 'y'
                  },
                  right: {
                    type: 'Literal',
                    loc:{start:{line:1,column:14},end:{line:1,column:15},source:''},
                    value: 1,
                    raw: '1'
                  }
                },
                shorthand: false
              }
            ]
          },
          init: {
            type: 'ObjectExpression',
            loc:{start:{line:1,column:19},end:{line:1,column:24},source:''},
            properties: [
              {
                type: 'Property',
                loc:{start:{line:1,column:20},end:{line:1,column:23},source:''},
                key: {
                  type: 'Literal',
                  loc:{start:{line:1,column:20},end:{line:1,column:21},source:''},
                  value: 2,
                  raw: '2'
                },
                kind: 'init',
                method: false,
                computed: false,
                value: {
                  type: 'Literal',
                  loc:{start:{line:1,column:22},end:{line:1,column:23},source:''},
                  value: 3,
                  raw: '3'
                },
                shorthand: false
              }
            ]
          }
        }
      ]
    }
  ]
}

tokens (18x):
       ID_var PUNC_CURLY_OPEN PUNC_BRACKET_OPEN NUMBER_DEC
       PUNC_BRACKET_CLOSE PUNC_COLON IDENT PUNC_EQ NUMBER_DEC
       PUNC_CURLY_CLOSE PUNC_EQ PUNC_CURLY_OPEN NUMBER_DEC PUNC_COLON
       NUMBER_DEC PUNC_CURLY_CLOSE ASI
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
var {[2]:y = 1} = {2:3};
````

Produces same AST
