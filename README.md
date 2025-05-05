# TP 3
Características de Lenguajes de Programación

# Gramáticas del Lenguaje Esotérico Backrooms

## 1. Gramática Independiente del Contexto (GIC)

```gic
<programa> -> <instrucciones>
<instrucciones> -> <instruccion> | <instruccion> <instrucciones>
<instruccion> -> <movimiento> | <accion> | <control> | <operacion>
<movimiento> -> w | a | s | d
<accion> -> e | q
<control> -> "[" <instrucciones> "]" | "{" <instrucciones> "}"
<operacion> -> + | - | * | /
<numero> -> <digito> | <digito> <numero>
<digito> -> 0 | ... | 9
```

---

## 2. BNF (Forma Normal de Backus)

```bnf
<program> ::= <statements>
<statements> ::= <statement> | <statement> <statements>
<statement> ::= <movement> | <action> | <control> | <operation>
<movement> ::= w | a | s | d
<action> ::= e | q
<control> ::= [ <statements> ] | { <statements> }
<operation> ::= + | - | * | /
<number> ::= <digit> | <digit> <number>
<digit> ::= 0 | ... | 9
```

---

## 3. EBNF (Extended BNF)

```ebnf
program ::= { statement }
statement ::= movement | action | control | operation
movement ::= w | a | s | d
action ::= e | q
control ::= "[" { statement } "]" | "{" { statement } "}"
operation ::= + | - | * | /
number ::= digit { digit }
digit ::= 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9
```

---

## 4. ABNF (Augmented BNF)

```abnf
program : *statement
statement : movement
            action
            control
            operation
movement : uno de "w"  "a"  "s"  "d"
action : uno de "e"  "q"
control : "[" *statement "]" 
          "{" *statement "}"
operation : uno de + - * /
number : 1*digit
digit : %x30-39  ; 0-9 en ASCII
```

---

## Notas adicionales

- **Backrooms** parece tener una sintaxis minimalista basada en caracteres individuales.
- Los **bloques de control** se representan con `[]` y `{}` según la documentación.
- Las **operaciones matemáticas básicas** están incluidas.
- El **movimiento** usa las teclas WASD típicas en videojuegos.
- Las **acciones** `'e'` y `'q'` parecen representar interacciones especiales.
