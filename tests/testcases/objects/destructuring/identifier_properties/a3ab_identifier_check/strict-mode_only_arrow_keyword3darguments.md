# Tenko parser test case

- Path: tests/testcases/objects/destructuring/identifier_properties/a3ab_identifier_check/strict-mode_only_arrow_keyword3darguments.md

> :: objects : destructuring : identifier properties : a3ab identifier check
>
> ::> strict-mode only arrow keyword3darguments

## Input

`````js
({xxxx:arguments}) => null
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
        type: 'ArrowFunctionExpression',
        loc:{start:{line:1,column:0},end:{line:1,column:26},source:''},
        params: [
          {
            type: 'ObjectPattern',
            loc:{start:{line:1,column:1},end:{line:1,column:17},source:''},
            properties: [
              {
                type: 'Property',
                loc:{start:{line:1,column:2},end:{line:1,column:16},source:''},
                key: {
                  type: 'Identifier',
                  loc:{start:{line:1,column:2},end:{line:1,column:6},source:''},
                  name: 'xxxx'
                },
                kind: 'init',
                method: false,
                computed: false,
                value: {
                  type: 'Identifier',
                  loc:{start:{line:1,column:7},end:{line:1,column:16},source:''},
                  name: 'arguments'
                },
                shorthand: false
              }
            ]
          }
        ],
        id: null,
        generator: false,
        async: false,
        expression: true,
        body: {
          type: 'Literal',
          loc:{start:{line:1,column:22},end:{line:1,column:26},source:''},
          value: null,
          raw: 'null'
        }
      }
    }
  ]
}

tokens (11x):
       PUNC_PAREN_OPEN PUNC_CURLY_OPEN IDENT PUNC_COLON ID_arguments
       PUNC_CURLY_CLOSE PUNC_PAREN_CLOSE PUNC_EQ_GT ID_null ASI
`````

### Strict mode

Parsed with script goal but as if it was starting with `"use strict"` at the top.

`````
throws: Parser error!
  The left hand side of the arrow is not destructible so arrow is illegal

start@1:0, error@1:19
╔══╦═════════════════
 1 ║ ({xxxx:arguments}) => null
   ║                    ^^------- error
╚══╩═════════════════

`````


### Module goal

Parsed with the module goal.

_Output same as strict mode._

### Web compat mode

Parsed in sloppy script mode but with the web compat flag enabled.

_Output same as sloppy mode._

## AST Printer

Printer output different from input [sloppy]:

````js
({xxxx:arguments}) => (null);
````

Produces same AST