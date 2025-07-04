# UNaHur - Características de Lenguajes de Programación - 2025
- Prof.: Mg. Pablo Pandolfo
- Alumno: Sebastián Brandariz

# TP 1

```mermaid
flowchart TD

subgraph DEF["Definición"]
    direction LR
    C["Especificación de tareas computacionales"]
    D["Notación para escribir programas"]
    E["Herramientas fundamentales para la comunicación entre humanos y computadoras"]
end

subgraph HLP["Historia de los LP"]
    direction TB
    H1["Antes de 1940: Programación mediante cableado"] --> H3["Década de 1940: Uso de códigos (Von Neumann). Evita el cableado"]
    H3 --> H4["Lenguaje ensamblador: Lenguaje de bajo nivel que facilitaba la programación mediante abreviaturas"]
    H4 --> H5["Adición de construcciones de alto nivel"]
    H5 --> H6["Transición a lenguajes de alto nivel"]
    H6 --> H7["Independencia de la máquina: Los LP modernos se independizaron de la máquina"]
end

subgraph DDP["Definición de paradigmas"]
    direction TB
    DP1["Conjunto de conceptos"] --> DP2["Cada paradigma tiene su propio enfoque"] --> DP3["Muchos lenguajes soportan más de un paradigma"]
end

subgraph PDP["Paradigmas de Programación"]
    direction TB
    P1["Paradigma Imperativo"] --> PI1["Secuencia de instrucciones"]
    PI1 --> PI2["Uso de variables, selección e iteración"] --> PI3["Ejemplos: C, Fortran, Pascal"]

    P2["Paradigma Orientado a Objetos"] --> POO1["Clases y objetos"]
    POO1 --> POO2["Encapsulamiento, polimorfismo, herencia"] --> POO3["Ejemplos: Java, Python, C++"]

    P3["Paradigma Funcional"] --> PF1["Cálculo lambda y funciones como parámetros"]
    PF1 --> PF2["Evaluación diferida y transparencia referencial"] --> PF3["Ejemplos: Haskell, Scala, F#"]

    P4["Paradigma Lógico"] --> PL1["Hechos y reglas (Cláusulas de Horn)"]
    PL1 --> PL2["Deducción mediante unificación y backtracking"] --> PL3["Ejemplos: Prolog, Mercury"]
end

LP["Lenguajes de Programación (LP)"] --> DEF
LP --> HLP
LP --> DDP
DDP --> PDP
```
## TP 2 - Lenguajes de Programación

En esta planilla colaborativa, se investigaron 180 lenguajes de programación, desde su año de creación, incluyendo Paradigma, Generación del lenguaje, Concurrencia, entre otras características.

Acceso a [Planilla de lenguajes](https://docs.google.com/spreadsheets/d/19aTSzIjQNs6RBNJFz0bftTlqKr-uWbohbBZnxmP0-r0/edit?gid=0#gid=0)

## TP 3 - Lenguaje Backrooms (Esotérico)

Los "Backrooms" son una creepypasta o leyenda urbana que describe un laberinto infinito de cuartos y pasillos de apariencia industrial, normalmente con paredes amarillentas, iluminación artificial y pisos de vinilo. Son descritos como un lugar al que se puede acceder erróneamente desde el mundo real, y que se caracteriza por su naturaleza inquietante y a menudo peligrosa

![image](https://github.com/user-attachments/assets/f52b6447-71a4-46f5-b2ee-a6bee0bc78a7)


Este lenguaje está inspirado en esta "leyenda urbana" de las *Backrooms*, diseñado para simular exploración en un espacio infinito y surrealista mediante instrucciones minimalistas.

## Índice
- [Lenguaje Backrooms (Esotérico)](#lenguaje-backrooms-esotérico)
  - [Índice](#índice)
  - [Características](#características)
  - [Gramáticas Formales](#gramáticas-formales)
    - [Gramática Independiente del Contexto (GIC)](#gramática-independiente-del-contexto-gic)
    - [Backus-Naur Form (BNF)](#backus-naur-form-bnf)
    - [Extendad Backus-Naur Form (EBNF)](#extendad-backus-naur-form-ebnf)
    - [Augmented Backus-Naur Form (ABNF)](#augmented-backus-naur-form-abnf)
    - [Semántica y Ejemplos](#semántica-y-ejemplos)
    - [Programa de Ejemplo](#programa-de-ejemplo)
      - [Descripción:](#descripción)
    - [Enlaces:](#enlaces)

---

## Características
- **Movimiento**: `w` (adelante), `a` (izquierda), `s` (atrás), `d` (derecha).
- **Acciones**: 
  - `e` (interactuar).
  - `q` (acción secundaria, como usar un objeto).
- **Estructuras de control**:
  - `[ ]`: Bucles o repeticiones.
  - `{ }`: Bloques condicionales o de eventos.
- **Operadores aritméticos**: `+`, `-`, `*`, `/` (modifican el entorno).
- **Números**: Enteros positivos (ej. `42` para repeticiones).

---

## Gramáticas Formales

### Gramática Independiente del Contexto (GIC)
```gic
<programa>      → <instrucciones>
<instrucciones> → <instruccion> | <instruccion> <instrucciones>
<instruccion>   → <movimiento> | <accion> | <control> | <operacion> | <numero> 
<movimiento>    → w | a | s | d
<accion>        → e | q
<control>       → '[' <instrucciones> ']' | '{' <instrucciones> '}'
<operacion>     → + | - | * | /
<numero>        → <digito> | <digito> <numero>
<digito>        → 0 | ... | 9
```

### Backus-Naur Form (BNF)
```
<programa>      ::= <instrucciones>
<instrucciones> ::= <instruccion> | <instruccion> <instrucciones>
<instruccion>   ::= <movimiento> | <accion> | <control> | <operacion> | <numero> 
<movimiento>    ::= w | a | s | d
<accion>        ::= e | q
<control>       ::= '[' <instrucciones> ']' | '{' <instrucciones> '}'
<operacion>     ::= + | - | * | /
<numero>        ::= <digito> | <digito> <numero>
<digito>        ::= 0 | ... | 9
```
### Extendad Backus-Naur Form (EBNF)
```
programa     ::=  { instruccion } 
instruccion  ::= movimiento | accion | control | operacion | numero
movimiento   ::= w | a | s | d 
accion       ::= e | q 
control      ::= '[' { instruccion } ']' | '{' { instruccion } '}' 
operacion    ::= '+' | '-' | '*' | '/' 
numero       ::= digito { digito } 
digito       ::= 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 
```
### Augmented Backus-Naur Form (ABNF)

```
programa : *instruccion
instruccion : movimiento
              accion
              control
              operacion
              numero
movimiento : %x77
             %x61
             %x73
             %x64  ; #'w', 'a', 's', 'd' en ASCII
accion : uno de %x65 %x71  ; #'e', 'q'
control : "[" *instruccion "]"
          "{" *instruccion "}"
operacion : uno de + - * /
numero : 1*digito
digito : uno de %x30-%x39  ; #'0'-'9'
```
### Semántica y Ejemplos
Interpretación
[w a s d]: Bucle infinito de movimientos (caminar en círculo).

{e q *}: Ejecuta e, luego q, y aplica una multiplicación al entorno.

3w (extensión propuesta): Avanza 3 veces.

### Programa de Ejemplo
```
w w [a d] e {q * 2}
```
#### Descripción:

Avanza 2 veces (w w).

Entra en un bucle [a d] (izquierda-derecha).

Ejecuta e (interactúa).

Bloque {q * 2}: Usa q y multiplica algo por 2.

## Notas adicionales

- **Backrooms** parece tener una sintaxis minimalista basada en caracteres individuales.
- Los **bloques de control** se representan con `[]` y `{}` según la documentación.
- Las **operaciones matemáticas básicas** están incluidas.
- El **movimiento** usa las teclas WASD típicas en videojuegos.
- Las **acciones** `'e'` y `'q'` representan interacciones especiales.

### Enlaces:

https://rpp.pe/capital/mundo/que-son-los-backrooms-la-pesadilla-que-podria-aterrorizarte-noticias-1435019

https://esolangs.org/wiki/Backrooms


# TP 4 - Gramática Sintáctica de BACKROOMS
Gramática completa del lenguaje esotérico BACKROOMS, expresada en diagrama sintáctico visual que representa todas sus producciones.

### Árbol Sintáctico

![image](https://github.com/user-attachments/assets/8635c3f8-0cb1-4e4b-afc2-e41221d78036)


### Diagrama de CONNWAY para "Backrooms"

![image](https://github.com/user-attachments/assets/54613da8-e04a-4719-b4ce-311614f390d1)

# TP 5
## Tipos de *Binding* en Parámetros

| **Binding** | **¿Qué define?** | **Estático** | **Dinámico** | **Diferencia entre Estático y Dinámico** | **Ejemplos** |
|-------------|------------------|--------------|--------------|------------------------------------------|-------------|
| **De tipo** | Determina qué tipo de datos puede recibir el parámetro. | El tipo está declarado explícitamente y se verifica en tiempo de compilación. | El tipo se determina automáticamente en tiempo de ejecución, según el valor pasado. | En estático, los errores de tipo se detectan antes de ejecutar. En dinámico, pueden aparecer solo cuando se usa el parámetro. | **Estático**: `int suma(int a, int b)` *(C, Java)*<br>**Dinámico**: `def suma(a, b)` *(Python, JS)* |
| **De valor o referencia** | Define si el parámetro recibe una copia del argumento o una referencia a él. | El paso (por valor o por referencia) se indica en la definición de la función o lo impone el lenguaje. | La forma en que se pasa puede variar según el tipo del argumento o cómo se lo utilice en tiempo de ejecución. | En estático, siempre se comporta igual. En dinámico, el mismo código puede funcionar distinto dependiendo del dato pasado. | **Estático**: `void f(int& x)` *(C++, por referencia)*<br>**Dinámico**: `def f(x): x.append(1)` *(Python, depende si es mutable o inmutable)* |
| **De alcance** | Define en qué partes del programa puede accederse al parámetro. | El parámetro solo es accesible dentro del bloque o función donde fue definido. | El parámetro puede mantenerse accesible fuera de su bloque original, si se captura (ej. en closures). | En estático, el alcance es fijo y limitado. En dinámico, puede extenderse más allá del lugar donde se declaró. | **Estático**: `def f(x): return x + 1` *(Python)*<br>**Dinámico**: `def f(): a = 10; return lambda x: x + a` *(Python, el parámetro `a` vive fuera)* |
| **De almacenamiento** | Especifica dónde (en memoria) se guarda el parámetro durante la ejecución. | La ubicación (pila, registros) es definida por el compilador según reglas del lenguaje. | Puede cambiar dinámicamente si, por ejemplo, el parámetro queda retenido en una función anidada o closure. | En estático, el almacenamiento es previsible. En dinámico, el parámetro puede mantenerse vivo más tiempo y en otra zona de memoria. | **Estático**: parámetros por pila en `int f(int x)` *(C)*<br>**Dinámico**: `def outer(): a = 1; return lambda: a` *(Python, `a` queda en el heap)* |
| **De nombre** | Es el identificador con el que se accede al parámetro dentro del cuerpo de la función. | El nombre está definido al declarar la función y no puede cambiar. | Se puede generar, modificar o usar indirectamente mediante programación dinámica o reflexiva. | En estático, el nombre es fijo. En dinámico, el nombre puede construirse o resolverse en ejecución. | **Estático**: `def saludar(nombre): print(nombre)`<br>**Dinámico**: `globals()['saludo'] = lambda x: print(x)` *(Python, nombre generado)* |
| **De tipo de paso** | Indica la estrategia con la que se pasa el parámetro (valor, referencia, nombre, perezoso, etc.). | Se fija por el lenguaje o en la definición de la función. No varía al llamar. | Se determina en tiempo de ejecución o puede variar según el uso del parámetro. | Estático: el paso es siempre el mismo. Dinámico: puede elegirse o inferirse durante la ejecución. | **Estático**: `int f(int x)` *(C, por valor)*<br>**Dinámico**: `let x = lazy (f())` *(OCaml, evaluación diferida/perezosa)* |


## Ejemplos de Binding: 

Binding de Alcance (Scope Binding):

Estático: El valor de una variable se resuelve en tiempo de compilación o antes de la ejecución, basándose en la ubicación léxica del código.
```
def f(x):
    return x + 1
```
Dinámico: El valor de una variable se resuelve en tiempo de ejecución, basándose en el contexto de llamada.

```
def f():
    a = 10
    return lambda x: x + a # La variable 'a' vive fuera de la función lambda
```
Binding de Almacenamiento (Storage Binding):

Dinámico: La variable se almacena en el heap y su vida útil se extiende más allá de la función que la define.

```
def outer():
    a = 1
    return lambda: a # 'a' permanece en el heap y es accesible por la lambda
```
Binding de Nombre (Name Binding):

Dinámico: El nombre de una variable o función es generado o asociado en tiempo de ejecución.

```
globals()['saludo'] = lambda x: print(x) #El nombre 'saludo' se genera dinámicamente
```
# Lenguaje de Programación a Lenguaje Natural

## Lenguaje de Programación: "Caminante"

![image](https://github.com/user-attachments/assets/3bd9ff28-a38c-40ff-8b22-b969af3bb5ce)


### Índice

- [Introducción al Lenguaje "Caminante"](#introducción-al-lenguaje-caminante)
- [Expresiones](#expresiones)
- [Condicionales](#condicionales)
- [Iteración](#iteración)
- [Tipos de Datos](#tipos-de-datos)
- [Gramática BNF para "Caminante"](#gramática-bnf-para-caminante)
- [Ejemplo de Programa en "Caminante"](#ejemplo-de-programa-en-caminante)
- [Aspectos de Diseño del Lenguaje "Caminante"](#aspectos-de-diseño-del-lenguaje-caminante)
  - [Generales](#generales)
    - [Entidades](#entidades)
    - [Ligaduras](#ligaduras)
    - [Reglas de Alcance](#reglas-de-alcance)
    - [Sistemas de Tipos](#sistemas-de-tipos)
    - [Soporte para Definir Subprogramas](#soporte-para-definir-subprogramas)
  - [Específicos](#específicos)
    - [Estructura Estática](#estructura-estática)
    - [Recursividad](#recursividad)
    - [Control](#control)
    - [Métodos de Pasaje de Parámetros](#métodos-de-pasaje-de-parámetros)
    - [Sobrecarga y Polimorfismo](#sobrecarga-y-polimorfismo)
    - [Tipos de los Parámetros](#tipos-de-los-parámetros)
    - [Ambiente de Referenciamiento de Subprogramas](#ambiente-de-referenciamiento-de-subprogramas)

## Introducción al Lenguaje "Caminante"
Imagina que tu código es un "Caminante", una entidad que se mueve a través de los infinitos y extraños Backrooms. 
Este lenguaje, llamado "Caminante", te permite darle instrucciones a este caminante para interactuar con los Niveles y las Entidades que habitan este laberinto. 
Cada instrucción se asemeja a una acción que tomarías o una observación que harías dentro de los Backrooms.

El lenguaje se compone de:

## Expresiones (Detección y Manipulación de Atributos): 
Puedes `"detectar"` o `"establecer"` atributos de tu entorno o de ti mismo. 
Por ejemplo, 
```
"detecta 'humedad' en el Nivel actual"
"establece 'resistencia' a 50"

```
El lenguaje procesará estas detecciones o asignaciones, dándote información o modificando características.

## Condicionales (Decisiones de Supervivencia): 

Puedes hacer que tu caminante tome decisiones críticas.
Si se cumple una condición `"hay una Entidad cerca"`, realizará una acción `"huye"`; si no, hará otra `"continúa explorando"`. 
```
"Si 'peligro_cercano', 
    'corre al zona_segura'
si no
    'busca suministros'"
```

## Iteración (Patrullas y Búsquedas Repetitivas): 

Puedes ordenar al caminante que repita una acción un número específico de veces o hasta que una condición deje de cumplirse (o se cumpla). 
```
 "Recorre el Nivel 10 veces: 'escanear_paredes'"
 "Mientras 'salida_no_encontrada',
    'muévete_aleatoriamente'"
```

## Tipos de Datos (Los Elementos de los Backrooms)
"Caminante" entiende y maneja al menos dos tipos fundamentales de información, cruciales para navegar los Backrooms:

- Niveles/Cantidades (Numéricos):
  Representan los distintos Niveles de los Backrooms (0, 1, 2, etc.) o cantidades como `"estabilidad"` o `"recuentos"`.
  Por ejemplo: `0`, `999`, `3.14`.

- Atributos/Entidades (Cadenas de Texto): 
  Son descripciones de propiedades (`"iluminación"`), nombres de Entidades (`"Sonriente"`), o estados (`"seguro"`). Siempre van entre comillas.
  Por ejemplo: `"Nivel_Infinito"`, `"olor_a_humedad"`, `"Parásito"`.

## Gramática BNF (Backus-Naur Form) para "Caminante"

```
<programa> ::= <instruccion> | <instruccion> <programa>

<instruccion> ::= <declaracion_atributo>
                | <evaluacion_condicional>
                | <ciclo_exploracion>
                | <accion_basica>

<declaracion_atributo> ::= "establece" <identificador> "a" <valor>
                         | "detecta" <atributo_backroom> "en" <lugar> "y guarda en" <identificador>

<valor> ::= <numero>
          | <cadena_texto>
          | <identificador>
          | <expresion_numerica>

<expresion_numerica> ::= <numero>
                       | <identificador>
                       | <expresion_numerica> "mas" <expresion_numerica>
                       | <expresion_numerica> "menos" <expresion_numerica>
                       | <expresion_numerica> "multiplicado_por" <expresion_numerica>
                       | <expresion_numerica> "dividido_por" <expresion_numerica>
                       | "(" <expresion_numerica> ")"

<evaluacion_condicional> ::= "si" <condicion_backroom> "," "entonces" <programa> "sino" <programa>
                           | "si" <condicion_backroom> "," "entonces" <programa>

<condicion_backroom> ::= <identificador> "es" <valor>
                       | <atributo_backroom> "es" <cadena_texto>
                       | <numero> "es_mayor_que" <numero>
                       | <entidad> "esta_presente_en" <lugar>

<ciclo_exploracion> ::= "repite" <numero> "veces" ":" <programa>
                      | "mientras" <condicion_backroom> ":" <programa>

<accion_basica> ::= "mover" <direccion>
                  | "interactuar_con" <entidad>
                  | "manifestar" <valor>
                  | "transicionar_a" <lugar>

<numero> ::= <digito> | <numero> <digito> | <numero> "." <digito>
<digito> ::= "0" | "1" | "2" | "3" | "4" | "5" | "6" | "7" | "8" | "9"

<cadena_texto> ::= "\"" <caracteres> "\""
<caracteres> ::= <caracter> | <caracter> <caracteres>
<caracter> ::= (cualquier letra, número, o símbolo excepto "\"")

<identificador> ::= <letra> | <identificador> <letra> | <identificador> <digito> | <identificador> "_"
<letra> ::= "a"..."z" | "A"..."Z"

<atributo_backroom> ::= "iluminacion" | "humedad" | "ruido" | "estabilidad_nivel" | <cadena_texto>

<lugar> ::= "Nivel_" <numero> | "Nivel_actual" | "zona_segura" | <identificador>

<entidad> ::= "Sonriente" | "Sabueso" | "Limen" | "Parásito" | <cadena_texto>

<direccion> ::= "adelante" | "atras" | "izquierda" | "derecha"
```

## Ejemplo de Programa en "Caminante":
```
detecta "iluminacion" en Nivel_actual y guarda en luz_actual

si luz_actual es "baja", entonces
    manifestar "¡Oscuridad! Buscando una fuente de luz."
    repite 5 veces:
        mover adelante
        detecta "ruido" en Nivel_actual y guarda en ruido_detectado
        si ruido_detectado es "alto", entonces
            manifestar "¡Ruido sospechoso!"
            interactuar_con "Sonriente"
            si "Sonriente" esta_presente_en Nivel_actual, entonces
                transicionar_a Nivel_0
            sino
                manifestar "Falsa alarma"
sino
    manifestar "Nivel bien iluminado. Explorando"
    mientras estabilidad_nivel es_mayor_que 10:
        establece "estabilidad_nivel" a estabilidad_nivel menos 1
        manifestar "Disminuyendo estabilidad..."

```

## Aspectos de Diseño del Lenguaje *Caminante*

### 1. Entidades y Tipos

#### Entidades

Las principales entidades que manipulan y existen en *Caminante* son:

- **Identificadores:** Lugares con nombre para almacenar valores numéricos (como recuentos de anomalías o niveles) y cadenas de texto (como `iluminacion` o `Sonriente`).
- **Literales:** Valores directos como `0`, `10` o `"peligro"`.
- **Atributos de los Backrooms:** Conceptos predefinidos como `iluminacion`, `humedad`, `ruido`, `estabilidad_nivel`. Son identificadores globales implícitos del entorno.
- **Entidades Nombradas:** Criaturas de los Backrooms, como `Sonriente`, `Sabueso`, etc.

#### Sistema de Tipos

*Caminante* posee un sistema de tipos **débil** y **dinámico**, con inferencia implícita:

- **Débil:** Operaciones como `mas` pueden realizar suma o concatenación.
- **Dinámico:** El tipo de un identificador se determina en tiempo de ejecución.
- **Inferencia:** No hay declaración explícita de tipos; el contexto define el tipo.

#### Tipos de Parámetros

Los comandos reciben principalmente **valores numéricos** o **cadenas de texto**. No hay unidades explícitas (como "metros" o "segundos"), el significado se infiere del comando.

---

### 2. Ligaduras y Alcance

#### Ligaduras

Asociación de nombres a significados:

- **Estáticas:** La mayoría de las ligaduras son estáticas. Por ejemplo, `si` siempre implica una condición.
- **Dinámicas:** No hay ligaduras puramente dinámicas. El valor de los identificadores se define en ejecución, pero su existencia y uso están definidos en diseño.

#### Reglas de Alcance

*Caminante* tiene alcance **global** y **anidado estático**:

- Los identificadores definidos tienen visibilidad en su bloque y sub-bloques.
- No hay mecanismos explícitos para variables locales.

---

### 3. Control del Flujo

#### Estructura Estática

El código sigue una estructura clara, lineal, de arriba hacia abajo. El flujo depende de condicionales (`si`) e iteraciones (`repite`, `mientras`). No hay saltos como `goto`.

#### Control (Secuencia, Selección, Iteración)

- **Secuencia:** Las instrucciones se ejecutan en orden.
- **Selección:** Con `si <condicion>, entonces <bloque> [sino <bloque>]`.
- **Iteración:** Con `repite <numero> veces:` y `mientras <condicion>:`.

#### Recursividad

No hay soporte para recursividad, ya que no se permiten subprogramas definidos por el usuario.

---

### 4. Subprogramas y Parámetros

#### Soporte para Subprogramas

*Caminante* no permite definir funciones o procedimientos. Todas las acciones (`mover`, `manifestar`, etc.) son comandos predefinidos.

#### Métodos de Pasaje de Parámetros

- **Por Valor (implícito):** Los comandos reciben copias de los valores. No pueden modificar el identificador original.
- **Correspondencia Posicional:** No hay parámetros con nombre. Se utiliza el orden de aparición.

#### Ambiente de Referenciamiento

No se permiten subprogramas como parámetros. No hay funciones de orden superior, y los comandos son fijos.

---

### 5. Polimorfismo

#### Sobrecarga y Polimorfismo

- **Sobrecarga en operaciones:** `mas` puede sumar números o concatenar cadenas.
- **Polimorfismo en comandos:** `manifestar` puede aceptar texto o números.

No hay polimorfismo paramétrico ni de subtipos ya que no hay jerarquías ni tipos definidos por el usuario.

## Diagrama Connway

```mermaid

graph TD
    A[programa]
    A --> B1[instruccion]
    A --> B2[instruccion + programa]

    B1 --> C1[declaracion_atributo]
    B1 --> C2[evaluacion_condicional]
    B1 --> C3[ciclo_exploracion]
    B1 --> C4[accion_basica]

    %% Declaración de atributos
    C1 --> D1[establece ident = valor]
    C1 --> D2[detecta attr en lugar y guarda en ident]

    %% Evaluación condicional
    C2 --> E1[si cond entonces prog]
    C2 --> E2[si cond entonces prog sino prog]

    %% Ciclos
    C3 --> F1[repite N veces: prog]
    C3 --> F2[mientras cond: prog]

    %% Acciones básicas
    C4 --> G1[mover dir]
    C4 --> G2[interactuar_con entidad]
    C4 --> G3[manifestar valor]
    C4 --> G4[transicionar_a lugar]

    %% Valores y expresiones
    D1 --> H1[valor]
    H1 --> I1[numero]
    H1 --> I2[cadena_texto]
    H1 --> I3[identificador]
    H1 --> I4[expresion_numerica]

    I4 --> J1[a mas b]
    I4 --> J2[a menos b]
    I4 --> J3[a multiplicado_por b]
    I4 --> J4[a dividido_por b]
    I4 --> J5[(expr)]

    %% Condiciones
    E1 --> K1[condicion]
    E2 --> K1
    F2 --> K1

    K1 --> L1[ident es valor]
    K1 --> L2[attr es cadena]
    K1 --> L3[num > num]
    K1 --> L4[entidad en lugar]

    %% Terminales
    subgraph Terminales
        M1[numero: 0, 1, 2...]
        M2[cadena_texto: ejemplo]
        M3[identificador]
        M4[atributo_backroom: iluminacion, humedad...]
        M5[lugar: Nivel_0, zona_segura...]
        M6[entidad: Sonriente, Sabueso...]
        M7[direccion: adelante, atras...]
    end

    G1 --> M7
    G2 --> M6
    G4 --> M5
    D2 --> M4
    D2 --> M5
    D2 --> M3
    L2 --> M4
    L4 --> M6

```
