# Tenko parser autogenerated test case

- From: tests/testcases/group_or_arrow/arrow/position/autogen.md
- Path: tests/testcases/group_or_arrow/arrow/position/gen/template/async_async_3d3e_ok.md

> :: group or arrow : arrow : position : gen : template
>
> ::> async async 3d3e ok

## Input


`````js
`a ${async async => ok} b`
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
  loc:{start:{line:1,column:0},end:{line:1,column:26},source:''},
  body: [
    {
      type: 'ExpressionStatement',
      loc:{start:{line:1,column:0},end:{line:1,column:26},source:''},
      expression: {
        type: 'TemplateLiteral',
        loc:{start:{line:1,column:0},end:{line:1,column:26},source:''},
        expressions: [
          {
            type: 'ArrowFunctionExpression',
            loc:{start:{line:1,column:5},end:{line:1,column:22},source:''},
            params: [
              {
                type: 'Identifier',
                loc:{start:{line:1,column:11},end:{line:1,column:16},source:''},
                name: 'async'
              }
            ],
            id: null,
            generator: false,
            async: true,
            expression: true,
            body: {
              type: 'Identifier',
              loc:{start:{line:1,column:20},end:{line:1,column:22},source:''},
              name: 'ok'
            }
          }
        ],
        quasis: [
          {
            type: 'TemplateElement',
            loc:{start:{line:1,column:1},end:{line:1,column:3},source:''},
            tail: false,
            value: { raw: 'a ', cooked: 'a ' }
          },
          {
            type: 'TemplateElement',
            loc:{start:{line:1,column:23},end:{line:1,column:25},source:''},
            tail: true,
            value: { raw: ' b', cooked: ' b' }
          }
        ]
      }
    }
  ]
}

tokens (8x):
       TICK_HEAD ID_async ID_async PUNC_EQ_GT IDENT TICK_TAIL ASI
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
`a ${async async => (ok)} b`;
````

Produces same AST