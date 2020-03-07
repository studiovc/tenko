# Tenko parser test case

- Path: tests/testcases/let_declaration/var_paren_wrapped/let_in_bracket_dot_x_parened.md

> :: let declaration : var paren wrapped
>
> ::> let in bracket dot x parened
>
> In this case `(let)[x]` is an expression so the `.foo` should be ok in sloppy

## Input

`````js
(let)[x].foo in x;
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
  loc:{start:{line:1,column:0},end:{line:1,column:18},source:''},
  body: [
    {
      type: 'ExpressionStatement',
      loc:{start:{line:1,column:0},end:{line:1,column:18},source:''},
      expression: {
        type: 'BinaryExpression',
        loc:{start:{line:1,column:0},end:{line:1,column:17},source:''},
        left: {
          type: 'MemberExpression',
          loc:{start:{line:1,column:0},end:{line:1,column:12},source:''},
          object: {
            type: 'MemberExpression',
            loc:{start:{line:1,column:0},end:{line:1,column:8},source:''},
            object: {
              type: 'Identifier',
              loc:{start:{line:1,column:1},end:{line:1,column:4},source:''},
              name: 'let'
            },
            property: {
              type: 'Identifier',
              loc:{start:{line:1,column:6},end:{line:1,column:7},source:''},
              name: 'x'
            },
            computed: true
          },
          property: {
            type: 'Identifier',
            loc:{start:{line:1,column:9},end:{line:1,column:12},source:''},
            name: 'foo'
          },
          computed: false
        },
        operator: 'in',
        right: {
          type: 'Identifier',
          loc:{start:{line:1,column:16},end:{line:1,column:17},source:''},
          name: 'x'
        }
      }
    }
  ]
}

tokens (12x):
       PUNC_PAREN_OPEN ID_let PUNC_PAREN_CLOSE PUNC_BRACKET_OPEN IDENT
       PUNC_BRACKET_CLOSE PUNC_DOT IDENT ID_in IDENT PUNC_SEMI
`````

### Strict mode

Parsed with script goal but as if it was starting with `"use strict"` at the top.

`````
throws: Parser error!
  Can not use `let` as variable name in strict mode

start@1:0, error@1:1
╔══╦════════════════
 1 ║ (let)[x].foo in x;
   ║  ^^^------- error
╚══╩════════════════

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