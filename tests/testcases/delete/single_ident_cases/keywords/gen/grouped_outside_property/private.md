# Tenko parser autogenerated test case

- From: tests/testcases/delete/single_ident_cases/keywords/autogen.md
- Path: tests/testcases/delete/single_ident_cases/keywords/gen/grouped_outside_property/private.md

> :: delete : single ident cases : keywords : gen : grouped outside property
>
> ::> private

## Input


`````js
delete (private).prop
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
        type: 'UnaryExpression',
        loc:{start:{line:1,column:0},end:{line:1,column:21},source:''},
        operator: 'delete',
        prefix: true,
        argument: {
          type: 'MemberExpression',
          loc:{start:{line:1,column:7},end:{line:1,column:21},source:''},
          object: {
            type: 'Identifier',
            loc:{start:{line:1,column:8},end:{line:1,column:15},source:''},
            name: 'private'
          },
          property: {
            type: 'Identifier',
            loc:{start:{line:1,column:17},end:{line:1,column:21},source:''},
            name: 'prop'
          },
          computed: false
        }
      }
    }
  ]
}

tokens (8x):
       ID_delete PUNC_PAREN_OPEN ID_private PUNC_PAREN_CLOSE PUNC_DOT
       IDENT ASI
`````

### Strict mode

Parsed with script goal but as if it was starting with `"use strict"` at the top.

`````
throws: Parser error!
  Cannot use this name (`private`) as a variable name because: Cannot use this reserved word as a variable name in strict mode

start@1:0, error@1:8
╔══╦════════════════
 1 ║ delete (private).prop
   ║         ^^^^^^^------- error
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

Printer output different from input [sloppy][annexb:no]:

````js
delete private.prop;
````

Produces same AST
