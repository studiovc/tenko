# Tenko parser test case

- Path: tests/testcases/async_keyword/async_arrow_statement_28useless_but_valid3f29_with_parens_and_zero_args.md

> :: async keyword
>
> ::> async arrow statement 28useless but valid3f29 with parens and zero args

## Input

`````js
async () => bar;
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
        loc:{start:{line:1,column:0},end:{line:1,column:15},source:''},
        params: [],
        id: null,
        generator: false,
        async: true,
        expression: true,
        body: {
          type: 'Identifier',
          loc:{start:{line:1,column:12},end:{line:1,column:15},source:''},
          name: 'bar'
        }
      }
    }
  ]
}

tokens (7x):
       ID_async PUNC_PAREN_OPEN PUNC_PAREN_CLOSE PUNC_EQ_GT IDENT
       PUNC_SEMI
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
async () => (bar);
````

Produces same AST