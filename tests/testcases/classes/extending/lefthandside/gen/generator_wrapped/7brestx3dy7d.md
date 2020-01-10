# Tenko parser autogenerated test case

- From: tests/testcases/classes/extending/lefthandside/autogen.md
- Path: tests/testcases/classes/extending/lefthandside/gen/generator_wrapped/7brestx3dy7d.md

> :: classes : extending : lefthandside : gen : generator wrapped
>
> ::> 7brestx3dy7d

## Input


`````js
function *P(){
  class D extends {...x=y} {}
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
        loc:{start:{line:1,column:10},end:{line:1,column:11},source:''},
        name: 'P'
      },
      params: [],
      body: {
        type: 'BlockStatement',
        loc:{start:{line:1,column:13},end:{line:3,column:1},source:''},
        body: [
          {
            type: 'ClassDeclaration',
            loc:{start:{line:2,column:2},end:{line:2,column:29},source:''},
            id: {
              type: 'Identifier',
              loc:{start:{line:2,column:8},end:{line:2,column:9},source:''},
              name: 'D'
            },
            superClass: {
              type: 'ObjectExpression',
              loc:{start:{line:2,column:18},end:{line:2,column:26},source:''},
              properties: [
                {
                  type: 'SpreadElement',
                  loc:{start:{line:2,column:19},end:{line:2,column:25},source:''},
                  argument: {
                    type: 'AssignmentExpression',
                    loc:{start:{line:2,column:22},end:{line:2,column:25},source:''},
                    left: {
                      type: 'Identifier',
                      loc:{start:{line:2,column:22},end:{line:2,column:23},source:''},
                      name: 'x'
                    },
                    operator: '=',
                    right: {
                      type: 'Identifier',
                      loc:{start:{line:2,column:24},end:{line:2,column:25},source:''},
                      name: 'y'
                    }
                  }
                }
              ]
            },
            body: {
              type: 'ClassBody',
              loc:{start:{line:2,column:27},end:{line:2,column:29},source:''},
              body: []
            }
          }
        ]
      }
    }
  ]
}

tokens (19x):
       ID_function PUNC_STAR IDENT PUNC_PAREN_OPEN PUNC_PAREN_CLOSE
       PUNC_CURLY_OPEN ID_class IDENT ID_extends PUNC_CURLY_OPEN
       PUNC_DOT_DOT_DOT IDENT PUNC_EQ IDENT PUNC_CURLY_CLOSE
       PUNC_CURLY_OPEN PUNC_CURLY_CLOSE PUNC_CURLY_CLOSE
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
function* P() {class D extends ({...x = y}) {}}
````

Produces same AST