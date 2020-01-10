# Tenko parser test case

- Path: tests/testcases/parens/arrow/trailing_comma/enabled_ES3d60Infinity60/after_object_destruct_with_default.md

> :: parens : arrow : trailing comma : enabled ES3d60Infinity60
>
> ::> after object destruct with default

## Input

- `es = Infinity`

`````js
({a} = b,) => {}
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
  loc:{start:{line:1,column:0},end:{line:1,column:16},source:''},
  body: [
    {
      type: 'ExpressionStatement',
      loc:{start:{line:1,column:0},end:{line:1,column:16},source:''},
      expression: {
        type: 'ArrowFunctionExpression',
        loc:{start:{line:1,column:0},end:{line:1,column:16},source:''},
        params: [
          {
            type: 'AssignmentPattern',
            loc:{start:{line:1,column:1},end:{line:1,column:8},source:''},
            left: {
              type: 'ObjectPattern',
              loc:{start:{line:1,column:1},end:{line:1,column:4},source:''},
              properties: [
                {
                  type: 'Property',
                  loc:{start:{line:1,column:2},end:{line:1,column:3},source:''},
                  key: {
                    type: 'Identifier',
                    loc:{start:{line:1,column:2},end:{line:1,column:3},source:''},
                    name: 'a'
                  },
                  kind: 'init',
                  method: false,
                  computed: false,
                  value: {
                    type: 'Identifier',
                    loc:{start:{line:1,column:2},end:{line:1,column:3},source:''},
                    name: 'a'
                  },
                  shorthand: true
                }
              ]
            },
            right: {
              type: 'Identifier',
              loc:{start:{line:1,column:7},end:{line:1,column:8},source:''},
              name: 'b'
            }
          }
        ],
        id: null,
        generator: false,
        async: false,
        expression: false,
        body: {
          type: 'BlockStatement',
          loc:{start:{line:1,column:14},end:{line:1,column:16},source:''},
          body: []
        }
      }
    }
  ]
}

tokens (13x):
       PUNC_PAREN_OPEN PUNC_CURLY_OPEN IDENT PUNC_CURLY_CLOSE PUNC_EQ
       IDENT PUNC_COMMA PUNC_PAREN_CLOSE PUNC_EQ_GT PUNC_CURLY_OPEN
       PUNC_CURLY_CLOSE ASI
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
({a} = b) => {};
````

Produces same AST