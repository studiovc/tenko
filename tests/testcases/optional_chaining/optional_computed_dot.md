# Tenko parser test case

- Path: tests/testcases/optional_chaining/optional_computed_dot.md

> :: optional chaining
>
> ::> optional computed dot
## PASS

## Input

`````js
d?.[e].f
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
  loc:{start:{line:1,column:0},end:{line:1,column:8},source:''},
  body: [
    {
      type: 'ExpressionStatement',
      loc:{start:{line:1,column:0},end:{line:1,column:8},source:''},
      expression: {
        type: 'OptionalMemberExpression',
        loc:{start:{line:1,column:0},end:{line:1,column:8},source:''},
        optional: false,
        computed: false,
        object: {
          type: 'OptionalMemberExpression',
          loc:{start:{line:1,column:0},end:{line:1,column:6},source:''},
          optional: true,
          computed: true,
          object: {
            type: 'Identifier',
            loc:{start:{line:1,column:0},end:{line:1,column:1},source:''},
            name: 'd'
          },
          property: {
            type: 'Identifier',
            loc:{start:{line:1,column:4},end:{line:1,column:5},source:''},
            name: 'e'
          }
        },
        property: {
          type: 'Identifier',
          loc:{start:{line:1,column:7},end:{line:1,column:8},source:''},
          name: 'f'
        }
      }
    }
  ]
}

tokens (9x):
       IDENT QMARK_DOT PUNC_BRACKET_OPEN IDENT PUNC_BRACKET_CLOSE
       PUNC_DOT IDENT ASI
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
(d)?.[e]?.f;
````

Produces same AST