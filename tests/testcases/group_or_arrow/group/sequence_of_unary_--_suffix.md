# Tenko parser test case

- Path: tests/testcases/group_or_arrow/group/sequence_of_unary_--_suffix.md

> :: group or arrow : group
>
> ::> sequence of unary -- suffix

## Input

`````js
(x--, y);
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
  loc:{start:{line:1,column:0},end:{line:1,column:9},source:''},
  body: [
    {
      type: 'ExpressionStatement',
      loc:{start:{line:1,column:0},end:{line:1,column:9},source:''},
      expression: {
        type: 'SequenceExpression',
        loc:{start:{line:1,column:1},end:{line:1,column:7},source:''},
        expressions: [
          {
            type: 'UpdateExpression',
            loc:{start:{line:1,column:1},end:{line:1,column:4},source:''},
            argument: {
              type: 'Identifier',
              loc:{start:{line:1,column:1},end:{line:1,column:2},source:''},
              name: 'x'
            },
            operator: '--',
            prefix: false
          },
          {
            type: 'Identifier',
            loc:{start:{line:1,column:6},end:{line:1,column:7},source:''},
            name: 'y'
          }
        ]
      }
    }
  ]
}

tokens (8x):
       PUNC_PAREN_OPEN IDENT PUNC_MIN_MIN PUNC_COMMA IDENT
       PUNC_PAREN_CLOSE PUNC_SEMI
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

Printer output was same as input [sloppy][annexb:no]
