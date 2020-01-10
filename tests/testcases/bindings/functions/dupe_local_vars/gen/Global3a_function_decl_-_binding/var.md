# Tenko parser autogenerated test case

- From: tests/testcases/bindings/functions/dupe_local_vars/autogen.md
- Path: tests/testcases/bindings/functions/dupe_local_vars/gen/Global3a_function_decl_-_binding/var.md

> :: bindings : functions : dupe local vars : gen : Global3a function decl - binding
>
> ::> var

## Input


`````js
function f() {} var f = 1;
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
      type: 'FunctionDeclaration',
      loc:{start:{line:1,column:0},end:{line:1,column:15},source:''},
      generator: false,
      async: false,
      id: {
        type: 'Identifier',
        loc:{start:{line:1,column:9},end:{line:1,column:10},source:''},
        name: 'f'
      },
      params: [],
      body: {
        type: 'BlockStatement',
        loc:{start:{line:1,column:13},end:{line:1,column:15},source:''},
        body: []
      }
    },
    {
      type: 'VariableDeclaration',
      loc:{start:{line:1,column:16},end:{line:1,column:26},source:''},
      kind: 'var',
      declarations: [
        {
          type: 'VariableDeclarator',
          loc:{start:{line:1,column:20},end:{line:1,column:25},source:''},
          id: {
            type: 'Identifier',
            loc:{start:{line:1,column:20},end:{line:1,column:21},source:''},
            name: 'f'
          },
          init: {
            type: 'Literal',
            loc:{start:{line:1,column:24},end:{line:1,column:25},source:''},
            value: 1,
            raw: '1'
          }
        }
      ]
    }
  ]
}

tokens (12x):
       ID_function IDENT PUNC_PAREN_OPEN PUNC_PAREN_CLOSE
       PUNC_CURLY_OPEN PUNC_CURLY_CLOSE ID_var IDENT PUNC_EQ
       NUMBER_DEC PUNC_SEMI
`````

### Strict mode

Parsed with script goal but as if it was starting with `"use strict"` at the top.

_Output same as sloppy mode._

### Module goal

Parsed with the module goal.

`````
throws: Parser error!
  Found a var binding that is duplicate of a lexical binding on the same or lower statement level

start@1:0, error@1:20
╔══╦═════════════════
 1 ║ function f() {} var f = 1;
   ║                     ^------- error
╚══╩═════════════════

`````


### Web compat mode

Parsed in sloppy script mode but with the web compat flag enabled.

_Output same as sloppy mode._

## AST Printer

Printer output different from input [sloppy]:

````js
function f() {}
var f = 1;
````

Produces same AST