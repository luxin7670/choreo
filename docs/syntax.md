# Syntax

This document describes the concrete and abstract syntax of My Language.

## Lexical Structure

### Identifiers

```bnf
identifier ::= letter (letter | digit | "_")*
```

### Literals

```bnf
integer ::= digit+
string  ::= '"' character* '"'
```

## Grammar

```bnf
program ::= declaration*

declaration ::= function_decl
              | variable_decl

function_decl ::= "fun" identifier "(" parameters ")" block

parameters ::= ε
             | identifier ("," identifier)*

block ::= "{" statement* "}"

statement ::= expression ";"
            | "if" expression block
            | "while" expression block
            | "return" expression ";"

expression ::= integer
             | identifier
             | expression "+" expression
             | expression "-" expression
             | expression "*" expression
             | expression "/" expression
```

## Examples

### Variable Declaration

```text
let x = 42;
```

### Function

```text
fun add(x, y) {
    return x + y;
}
```

### Conditional

```text
if x > 0 {
    print(x);
}
```

## Abstract Syntax Tree

```text
Expr
├── Int
├── Var
├── Add
├── Sub
├── Mul
└── Div
```
