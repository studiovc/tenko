# Tenko parser test case

- Path: tests/testcases/var/binding_generic/in_a_for-header/destruct/for-of/object/double_var_simple_1.md

> :: var : binding generic : in a for-header : destruct : for-of : object
>
> ::> double var simple 1

## Input

`````js
for (var {x, y} of obj);
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
  loc:{start:{line:1,column:0},end:{line:1,column:24},source:''},
  body: [
    {
      type: 'ForOfStatement',
      loc:{start:{line:1,column:0},end:{line:1,column:24},source:''},
      left: {
        type: 'VariableDeclaration',
        loc:{start:{line:1,column:5},end:{line:1,column:15},source:''},
        kind: 'var',
        declarations: [
          {
            type: 'VariableDeclarator',
            loc:{start:{line:1,column:9},end:{line:1,column:15},source:''},
            id: {
              type: 'ObjectPattern',
              loc:{start:{line:1,column:9},end:{line:1,column:15},source:''},
              properties: [
                {
                  type: 'Property',
                  loc:{start:{line:1,column:10},end:{line:1,column:11},source:''},
                  key: {
                    type: 'Identifier',
                    loc:{start:{line:1,column:10},end:{line:1,column:11},source:''},
                    name: 'x'
                  },
                  kind: 'init',
                  method: false,
                  computed: false,
                  value: {
                    type: 'Identifier',
                    loc:{start:{line:1,column:10},end:{line:1,column:11},source:''},
                    name: 'x'
                  },
                  shorthand: true
                },
                {
                  type: 'Property',
                  loc:{start:{line:1,column:13},end:{line:1,column:14},source:''},
                  key: {
                    type: 'Identifier',
                    loc:{start:{line:1,column:13},end:{line:1,column:14},source:''},
                    name: 'y'
                  },
                  kind: 'init',
                  method: false,
                  computed: false,
                  value: {
                    type: 'Identifier',
                    loc:{start:{line:1,column:13},end:{line:1,column:14},source:''},
                    name: 'y'
                  },
                  shorthand: true
                }
              ]
            },
            init: null
          }
        ]
      },
      right: {
        type: 'Identifier',
        loc:{start:{line:1,column:19},end:{line:1,column:22},source:''},
        name: 'obj'
      },
      await: false,
      body: {
        type: 'EmptyStatement',
        loc:{start:{line:1,column:23},end:{line:1,column:24},source:''}
      }
    }
  ]
}

tokens (13x):
       ID_for PUNC_PAREN_OPEN ID_var PUNC_CURLY_OPEN IDENT PUNC_COMMA
       IDENT PUNC_CURLY_CLOSE ID_of IDENT PUNC_PAREN_CLOSE PUNC_SEMI
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
for (var {x, y} of obj) ;
````

Produces same AST