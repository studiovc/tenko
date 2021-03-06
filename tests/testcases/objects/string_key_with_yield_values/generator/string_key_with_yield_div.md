# Tenko parser test case

- Path: tests/testcases/objects/string_key_with_yield_values/generator/string_key_with_yield_div.md

> :: objects : string key with yield values : generator
>
> ::> string key with yield div

## Input


`````js
function *f(){   s = {"foo": yield / x}   }
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in five parsing modes: sloppy, sloppy+annexb, strict script, module, module+annexb.

Note that the output parts are auto-generated by the test runner to reflect actual result.

### Sloppy mode

Parsed with script goal and as if the code did not start with strict mode header.

`````
throws: Lexer error!
    Regex: Encountered unescaped closing curly `}` while not parsing a quantifier

start@1:0, error@1:35
╔══╦═════════════════
 1 ║ function *f(){   s = {"foo": yield / x}   }
   ║                                    ^^^^------- error
╚══╩═════════════════

`````

### Strict mode

Parsed with script goal but as if it was starting with `"use strict"` at the top.

_Output same as sloppy mode._

### Module goal

Parsed with the module goal.

_Output same as sloppy mode._

### Sloppy mode with AnnexB

Parsed with script goal with AnnexB rules enabled and as if the code did not start with strict mode header.

`````
throws: Lexer error!
    Regex: Encountered unescaped closing curly `}` while not parsing a quantifier; Found EOF before regex was closed

start@1:0, error@1:35
╔══╦═════════════════
 1 ║ function *f(){   s = {"foo": yield / x}   }
   ║                                    ^^^^^^^^------- error
╚══╩═════════════════

`````

### Module goal with AnnexB

Parsed with the module goal with AnnexB rules enabled.

_Output same as sloppy mode with annexB._
