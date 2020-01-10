# Tenko parser test case

- Path: tests/testcases/var/binding_generic/in_a_for-header/destruct/for-in/array/rest/rest_on_a_nested_destruct.md

> :: var : binding generic : in a for-header : destruct : for-in : array : rest
>
> ::> rest on a nested destruct

## Input

`````js
for (var [...[foo, bar]] in obj);
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
  loc:{start:{line:1,column:0},end:{line:1,column:33},source:''},
  body: [
    {
      type: 'ForInStatement',
      loc:{start:{line:1,column:0},end:{line:1,column:33},source:''},
      left: {
        type: 'VariableDeclaration',
        loc:{start:{line:1,column:5},end:{line:1,column:24},source:''},
        kind: 'var',
        declarations: [
          {
            type: 'VariableDeclarator',
            loc:{start:{line:1,column:9},end:{line:1,column:24},source:''},
            id: {
              type: 'ArrayPattern',
              loc:{start:{line:1,column:9},end:{line:1,column:24},source:''},
              elements: [
                {
                  type: 'RestElement',
                  loc:{start:{line:1,column:10},end:{line:1,column:23},source:''},
                  argument: {
                    type: 'ArrayPattern',
                    loc:{start:{line:1,column:13},end:{line:1,column:23},source:''},
                    elements: [
                      {
                        type: 'Identifier',
                        loc:{start:{line:1,column:14},end:{line:1,column:17},source:''},
                        name: 'foo'
                      },
                      {
                        type: 'Identifier',
                        loc:{start:{line:1,column:19},end:{line:1,column:22},source:''},
                        name: 'bar'
                      }
                    ]
                  }
                }
              ]
            },
            init: null
          }
        ]
      },
      right: {
        type: 'Identifier',
        loc:{start:{line:1,column:28},end:{line:1,column:31},source:''},
        name: 'obj'
      },
      body: {
        type: 'EmptyStatement',
        loc:{start:{line:1,column:32},end:{line:1,column:33},source:''}
      }
    }
  ]
}

tokens (16x):
       ID_for PUNC_PAREN_OPEN ID_var PUNC_BRACKET_OPEN
       PUNC_DOT_DOT_DOT PUNC_BRACKET_OPEN IDENT PUNC_COMMA IDENT
       PUNC_BRACKET_CLOSE PUNC_BRACKET_CLOSE ID_in IDENT
       PUNC_PAREN_CLOSE PUNC_SEMI
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
for (var [...[foo, bar]] in obj) ;
````

Produces same AST