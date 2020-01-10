# Tenko parser autogenerated test case

- From: tests/testcases/yield/arrow_piggy/autogen.md
- Path: tests/testcases/yield/arrow_piggy/gen/test/function_2a_g2829_7b_async_285ba_3d_yield_b5d29_7d.md

> :: yield : arrow piggy : gen : test
>
> ::> function 2a g2829 7b async 285ba 3d yield b5d29 7d
>            async ([a = yield b])
>          }

## Input


`````js
function * g() {
  async ([a = yield b])
}
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
  loc:{start:{line:1,column:0},end:{line:3,column:1},source:''},
  body: [
    {
      type: 'FunctionDeclaration',
      loc:{start:{line:1,column:0},end:{line:3,column:1},source:''},
      generator: true,
      async: false,
      id: {
        type: 'Identifier',
        loc:{start:{line:1,column:11},end:{line:1,column:12},source:''},
        name: 'g'
      },
      params: [],
      body: {
        type: 'BlockStatement',
        loc:{start:{line:1,column:15},end:{line:3,column:1},source:''},
        body: [
          {
            type: 'ExpressionStatement',
            loc:{start:{line:2,column:2},end:{line:2,column:23},source:''},
            expression: {
              type: 'CallExpression',
              loc:{start:{line:2,column:2},end:{line:2,column:23},source:''},
              callee: {
                type: 'Identifier',
                loc:{start:{line:2,column:2},end:{line:2,column:7},source:''},
                name: 'async'
              },
              arguments: [
                {
                  type: 'ArrayExpression',
                  loc:{start:{line:2,column:9},end:{line:2,column:22},source:''},
                  elements: [
                    {
                      type: 'AssignmentExpression',
                      loc:{start:{line:2,column:10},end:{line:2,column:21},source:''},
                      left: {
                        type: 'Identifier',
                        loc:{start:{line:2,column:10},end:{line:2,column:11},source:''},
                        name: 'a'
                      },
                      operator: '=',
                      right: {
                        type: 'YieldExpression',
                        loc:{start:{line:2,column:14},end:{line:2,column:21},source:''},
                        delegate: false,
                        argument: {
                          type: 'Identifier',
                          loc:{start:{line:2,column:20},end:{line:2,column:21},source:''},
                          name: 'b'
                        }
                      }
                    }
                  ]
                }
              ]
            }
          }
        ]
      }
    }
  ]
}

tokens (18x):
       ID_function PUNC_STAR IDENT PUNC_PAREN_OPEN PUNC_PAREN_CLOSE
       PUNC_CURLY_OPEN ID_async PUNC_PAREN_OPEN PUNC_BRACKET_OPEN
       IDENT PUNC_EQ ID_yield IDENT PUNC_BRACKET_CLOSE
       PUNC_PAREN_CLOSE ASI PUNC_CURLY_CLOSE
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
function* g() {async([a = (yield (b))]);}
````

Produces same AST