# Tenko parser test case

- Path: tests/testcases/for_statement/for-of/destructuring_with_dynamic_property_2.md

> :: for statement : for-of
>
> ::> destructuring with dynamic property 2

## Input

`````js
for ({a: b.c}[x] of d) e
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
      type: 'ForOfStatement',
      loc:{start:{line:1,column:0},end:{line:1,column:24},source:''},
      left: {
        type: 'MemberExpression',
        loc:{start:{line:1,column:5},end:{line:1,column:16},source:''},
        object: {
          type: 'ObjectExpression',
          loc:{start:{line:1,column:5},end:{line:1,column:13},source:''},
          properties: [
            {
              type: 'Property',
              loc:{start:{line:1,column:6},end:{line:1,column:12},source:''},
              key: {
                type: 'Identifier',
                loc:{start:{line:1,column:6},end:{line:1,column:7},source:''},
                name: 'a'
              },
              kind: 'init',
              method: false,
              computed: false,
              value: {
                type: 'MemberExpression',
                loc:{start:{line:1,column:9},end:{line:1,column:12},source:''},
                object: {
                  type: 'Identifier',
                  loc:{start:{line:1,column:9},end:{line:1,column:10},source:''},
                  name: 'b'
                },
                property: {
                  type: 'Identifier',
                  loc:{start:{line:1,column:11},end:{line:1,column:12},source:''},
                  name: 'c'
                },
                computed: false
              },
              shorthand: false
            }
          ]
        },
        property: {
          type: 'Identifier',
          loc:{start:{line:1,column:14},end:{line:1,column:15},source:''},
          name: 'x'
        },
        computed: true
      },
      right: {
        type: 'Identifier',
        loc:{start:{line:1,column:20},end:{line:1,column:21},source:''},
        name: 'd'
      },
      await: false,
      body: {
        type: 'ExpressionStatement',
        loc:{start:{line:1,column:23},end:{line:1,column:24},source:''},
        expression: {
          type: 'Identifier',
          loc:{start:{line:1,column:23},end:{line:1,column:24},source:''},
          name: 'e'
        }
      }
    }
  ]
}

tokens (18x):
       ID_for PUNC_PAREN_OPEN PUNC_CURLY_OPEN IDENT PUNC_COLON IDENT
       PUNC_DOT IDENT PUNC_CURLY_CLOSE PUNC_BRACKET_OPEN IDENT
       PUNC_BRACKET_CLOSE ID_of IDENT PUNC_PAREN_CLOSE IDENT ASI
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
for ((({a:b.c})[x]) of d) e;
````

Produces same AST
