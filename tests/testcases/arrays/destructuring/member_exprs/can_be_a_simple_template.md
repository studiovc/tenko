# Tenko parser test case

- Path: tests/testcases/arrays/destructuring/member_exprs/can_be_a_simple_template.md

> :: arrays : destructuring : member exprs
>
> ::> can be a simple template

## Input

`````js
[`x`.length] = x
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
  loc:{start:{line:1,column:0},end:{line:1,column:16},source:''},
  body: [
    {
      type: 'ExpressionStatement',
      loc:{start:{line:1,column:0},end:{line:1,column:16},source:''},
      expression: {
        type: 'AssignmentExpression',
        loc:{start:{line:1,column:0},end:{line:1,column:16},source:''},
        left: {
          type: 'ArrayPattern',
          loc:{start:{line:1,column:0},end:{line:1,column:12},source:''},
          elements: [
            {
              type: 'MemberExpression',
              loc:{start:{line:1,column:1},end:{line:1,column:11},source:''},
              object: {
                type: 'TemplateLiteral',
                loc:{start:{line:1,column:1},end:{line:1,column:4},source:''},
                expressions: [],
                quasis: [
                  {
                    type: 'TemplateElement',
                    loc:{start:{line:1,column:2},end:{line:1,column:3},source:''},
                    tail: true,
                    value: { raw: 'x', cooked: 'x' }
                  }
                ]
              },
              property: {
                type: 'Identifier',
                loc:{start:{line:1,column:5},end:{line:1,column:11},source:''},
                name: 'length'
              },
              computed: false
            }
          ]
        },
        operator: '=',
        right: {
          type: 'Identifier',
          loc:{start:{line:1,column:15},end:{line:1,column:16},source:''},
          name: 'x'
        }
      }
    }
  ]
}

tokens (9x):
       PUNC_BRACKET_OPEN TICK_PURE PUNC_DOT IDENT PUNC_BRACKET_CLOSE
       PUNC_EQ IDENT ASI
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
[`x`.length] = x;
````

Produces same AST
