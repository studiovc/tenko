# Tenko parser test case

- Path: tests/testcases/bindings/export/multiple_exports/a_a_b.md

> :: bindings : export : multiple exports
>
> ::> a a b
> 
> https://tc39.github.io/ecma262/#sec-module-semantics-static-semantics-early-errors
> 
> > It is a Syntax Error if the ExportedNames of ModuleItemList contains any duplicate entries.
> 
> > The duplicate ExportedNames rule implies that multiple export default ExportDeclaration items within a ModuleBody is a Syntax Error.
> 
> > It is a Syntax Error if any element of the ExportedBindings of ModuleItemList does not also occur in either the VarDeclaredNames of ModuleItemList, or the LexicallyDeclaredNames of ModuleItemList.


## Input


`````js
var a,b;
export {a};
export {a, b};
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in five parsing modes: sloppy, sloppy+annexb, strict script, module, module+annexb.

Note that the output parts are auto-generated by the test runner to reflect actual result.

### Sloppy mode

Parsed with script goal and as if the code did not start with strict mode header.

`````
throws: Parser error!
  The `export` keyword can only be used with the module goal

start@1:0, error@2:0
╔══╦════════════════
 1 ║ var a,b;
 2 ║ export {a};
   ║ ^^^^^^------- error
 3 ║ export {a, b};
╚══╩════════════════

`````

### Strict mode

Parsed with script goal but as if it was starting with `"use strict"` at the top.

_Output same as sloppy mode._

### Module goal

Parsed with the module goal.

`````
throws: Parser error!
  Tried to export the name `a` twice

start@1:0, error@3:0
╔══╦════════════════
 1 ║ var a,b;
 2 ║ export {a};
 3 ║ export {a, b};
   ║ ^^^^^^------- error
╚══╩════════════════

`````

### Sloppy mode with AnnexB

Parsed with script goal with AnnexB rules enabled and as if the code did not start with strict mode header.

_Output same as sloppy mode._

### Module goal with AnnexB

Parsed with the module goal with AnnexB rules enabled.

_Output same as module mode._
