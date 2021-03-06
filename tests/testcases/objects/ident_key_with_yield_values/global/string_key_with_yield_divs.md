# Tenko parser test case

- Path: tests/testcases/objects/ident_key_with_yield_values/global/string_key_with_yield_divs.md

> :: objects : ident key with yield values : global
>
> ::> string key with yield divs

## Input

`````js
s = {foo: yield /x/g}
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
  loc:{start:{line:1,column:0},end:{line:1,column:21},source:''},
  body: [
    {
      type: 'ExpressionStatement',
      loc:{start:{line:1,column:0},end:{line:1,column:21},source:''},
      expression: {
        type: 'AssignmentExpression',
        loc:{start:{line:1,column:0},end:{line:1,column:21},source:''},
        left: {
          type: 'Identifier',
          loc:{start:{line:1,column:0},end:{line:1,column:1},source:''},
          name: 's'
        },
        operator: '=',
        right: {
          type: 'ObjectExpression',
          loc:{start:{line:1,column:4},end:{line:1,column:21},source:''},
          properties: [
            {
              type: 'Property',
              loc:{start:{line:1,column:5},end:{line:1,column:20},source:''},
              key: {
                type: 'Identifier',
                loc:{start:{line:1,column:5},end:{line:1,column:8},source:''},
                name: 'foo'
              },
              kind: 'init',
              method: false,
              computed: false,
              value: {
                type: 'BinaryExpression',
                loc:{start:{line:1,column:10},end:{line:1,column:20},source:''},
                left: {
                  type: 'BinaryExpression',
                  loc:{start:{line:1,column:10},end:{line:1,column:18},source:''},
                  left: {
                    type: 'Identifier',
                    loc:{start:{line:1,column:10},end:{line:1,column:15},source:''},
                    name: 'yield'
                  },
                  operator: '/',
                  right: {
                    type: 'Identifier',
                    loc:{start:{line:1,column:17},end:{line:1,column:18},source:''},
                    name: 'x'
                  }
                },
                operator: '/',
                right: {
                  type: 'Identifier',
                  loc:{start:{line:1,column:19},end:{line:1,column:20},source:''},
                  name: 'g'
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
       IDENT PUNC_EQ PUNC_CURLY_OPEN IDENT PUNC_COLON ID_yield
       PUNC_DIV IDENT PUNC_DIV IDENT PUNC_CURLY_CLOSE ASI
`````

### Strict mode

Parsed with script goal but as if it was starting with `"use strict"` at the top.

`````
throws: Parser error!
  Cannot use `yield` outside of generator functions when in strict mode

start@1:0, error@1:10
╔══╦═════════════════
 1 ║ s = {foo: yield /x/g}
   ║           ^^^^^------- error
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

Printer output different from input [sloppy][annexb:no]:

````js
s = {foo:(yield / x) / g};
````

Produces same AST
