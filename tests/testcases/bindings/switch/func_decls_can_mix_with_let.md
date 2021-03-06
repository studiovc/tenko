# Tenko parser test case

- Path: tests/testcases/bindings/switch/func_decls_can_mix_with_let.md

> :: bindings : switch
>
> ::> func decls can mix with let
> 
> https://tc39.github.io/ecma262/#sec-switch-statement-static-semantics-early-errors
> 
> > It is a Syntax Error if the LexicallyDeclaredNames of CaseBlock contains any duplicate entries.
> 
> > It is a Syntax Error if any element of the LexicallyDeclaredNames of CaseBlock also occurs in the VarDeclaredNames of CaseBlock.
> 
> https://tc39.github.io/ecma262/#sec-switch-duplicates-allowed-static-semantics
> 
> duplicate function decl names do not cause an error in BlockStatement and SwitchStatement

## Input

`````js
switch (x) {case a: function f(){}; break; case b: let f; break; }
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in five parsing modes: sloppy, sloppy+annexb, strict script, module, module+annexb.

Note that the output parts are auto-generated by the test runner to reflect actual result.

### Sloppy mode

Parsed with script goal and as if the code did not start with strict mode header.

`````
throws: Parser error!
  Attempted to create a lexical binding for `f` but another binding already existed on the same level

start@1:0, error@1:55
╔══╦═════════════════
 1 ║ switch (x) {case a: function f(){}; break; case b: let f; break; }
   ║                                                        ^------- error
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

_Output same as sloppy mode._

### Module goal with AnnexB

Parsed with the module goal with AnnexB rules enabled.

_Output same as sloppy mode._
