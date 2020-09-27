<!--
# Keywords
-->

# Les mots-clés

<!--
Rust divides keywords into three categories:
-->

Rust divise ses mots-clés en trois catégories :

<!--
* [strict](#strict-keywords)
* [reserved](#reserved-keywords)
* [weak](#weak-keywords)
-->

* [strictes](#les-mots-cles-stricts)
* [réservés](#les-mots-cles-reserves)
* [légers](#les-mots-cles-legers)

<!--
## Strict keywords
-->

## Les mots-clés stricts

<!--
These keywords can only be used in their correct contexts. They cannot
be used as the names of:
-->

Ces mots-clés peuvent être utilisés uniquement dans leurs contextes respectifs.
Ils ne peuvent pas être utilisés comme noms pour :

<!--
* [Items]
* [Variables] and function parameters
* Fields and [variants]
* [Type parameters]
* Lifetime parameters or [loop labels]
* [Macros] or [attributes]
* [Macro placeholders]
* [Crates]
-->

* [Les éléments][Items]
* [Les variables][Variables] et les paramètres de fonctions
* Les champs et les [variantes][variants]
* [Les paramètres de types][Type parameters]
* Les paramètres de durée de vie ou les [étiquettes de boucles][loop labels]
* [Les macros][Macros] ou [les attributs][attributes]
* [Les emplacements de macro][Macro placeholders]
* [Les crates][Crates]

<!--
> **<sup>Lexer:<sup>**\
> KW_AS             : `as`\
> KW_BREAK          : `break`\
> KW_CONST          : `const`\
> KW_CONTINUE       : `continue`\
> KW_CRATE          : `crate`\
> KW_ELSE           : `else`\
> KW_ENUM           : `enum`\
> KW_EXTERN         : `extern`\
> KW_FALSE          : `false`\
> KW_FN             : `fn`\
> KW_FOR            : `for`\
> KW_IF             : `if`\
> KW_IMPL           : `impl`\
> KW_IN             : `in`\
> KW_LET            : `let`\
> KW_LOOP           : `loop`\
> KW_MATCH          : `match`\
> KW_MOD            : `mod`\
> KW_MOVE           : `move`\
> KW_MUT            : `mut`\
> KW_PUB            : `pub`\
> KW_REF            : `ref`\
> KW_RETURN         : `return`\
> KW_SELFVALUE      : `self`\
> KW_SELFTYPE       : `Self`\
> KW_STATIC         : `static`\
> KW_STRUCT         : `struct`\
> KW_SUPER          : `super`\
> KW_TRAIT          : `trait`\
> KW_TRUE           : `true`\
> KW_TYPE           : `type`\
> KW_UNSAFE         : `unsafe`\
> KW_USE            : `use`\
> KW_WHERE          : `where`\
> KW_WHILE          : `while`
-->

> **<sup>Lexème :<sup>**\
> KW_AS             : `as`\
> KW_BREAK          : `break`\
> KW_CONST          : `const`\
> KW_CONTINUE       : `continue`\
> KW_CRATE          : `crate`\
> KW_ELSE           : `else`\
> KW_ENUM           : `enum`\
> KW_EXTERN         : `extern`\
> KW_FALSE          : `false`\
> KW_FN             : `fn`\
> KW_FOR            : `for`\
> KW_IF             : `if`\
> KW_IMPL           : `impl`\
> KW_IN             : `in`\
> KW_LET            : `let`\
> KW_LOOP           : `loop`\
> KW_MATCH          : `match`\
> KW_MOD            : `mod`\
> KW_MOVE           : `move`\
> KW_MUT            : `mut`\
> KW_PUB            : `pub`\
> KW_REF            : `ref`\
> KW_RETURN         : `return`\
> KW_SELFVALUE      : `self`\
> KW_SELFTYPE       : `Self`\
> KW_STATIC         : `static`\
> KW_STRUCT         : `struct`\
> KW_SUPER          : `super`\
> KW_TRAIT          : `trait`\
> KW_TRUE           : `true`\
> KW_TYPE           : `type`\
> KW_UNSAFE         : `unsafe`\
> KW_USE            : `use`\
> KW_WHERE          : `where`\
> KW_WHILE          : `while`

<!--
The following keywords were added beginning in the 2018 edition.
-->

Les mots-clés suivants ont été ajoutés à la création de l'édition 2018.

<!--
> **<sup>Lexer 2018+</sup>**\
> KW_ASYNC          : `async`\
> KW_AWAIT          : `await`\
> KW_DYN            : `dyn`
-->

> **<sup>Lexème depuis l'édition 2018 et les suivantes :</sup>**\
> KW_ASYNC          : `async`\
> KW_AWAIT          : `await`\
> KW_DYN            : `dyn`

<!--
## Reserved keywords
-->

## Les mots-clés reservés

<!--
These keywords aren't used yet, but they are reserved for future use. They have
the same restrictions as strict keywords. The reasoning behind this is to make
current programs forward compatible with future versions of Rust by forbidding
them to use these keywords.
-->

Ces mots-clés ne sont pas encore utilisés, mais sont réservés pour une
utilisation future. Ils sont soumis aux mêmes restrictions que les mots-clés
stricts. L'idée derrière cela est de rendre les programmes d'aujourd'hui
compatibles avec les versions futures de Rust de demain, en leur interdisant
dès à présent l'utilisation de ces mots-clés.

<!--
> **<sup>Lexer</sup>**\
> KW_ABSTRACT       : `abstract`\
> KW_BECOME         : `become`\
> KW_BOX            : `box`\
> KW_DO             : `do`\
> KW_FINAL          : `final`\
> KW_MACRO          : `macro`\
> KW_OVERRIDE       : `override`\
> KW_PRIV           : `priv`\
> KW_TYPEOF         : `typeof`\
> KW_UNSIZED        : `unsized`\
> KW_VIRTUAL        : `virtual`\
> KW_YIELD          : `yield`
-->

> **<sup>Lexème :</sup>**\
> KW_ABSTRACT       : `abstract`\
> KW_BECOME         : `become`\
> KW_BOX            : `box`\
> KW_DO             : `do`\
> KW_FINAL          : `final`\
> KW_MACRO          : `macro`\
> KW_OVERRIDE       : `override`\
> KW_PRIV           : `priv`\
> KW_TYPEOF         : `typeof`\
> KW_UNSIZED        : `unsized`\
> KW_VIRTUAL        : `virtual`\
> KW_YIELD          : `yield`

<!--
The following keywords are reserved beginning in the 2018 edition.
-->

Le mot-clé suivant est réservé depuis la création de l'édition 2018.

<!--
> **<sup>Lexer 2018+</sup>**\
> KW_TRY   : `try`
-->

> **<sup>Lexème depuis l'édition 2018 et les suivantes :</sup>**\
> KW_TRY   : `try`

<!--
## Weak keywords
-->

## Les mots-clés légers

<!--
These keywords have special meaning only in certain contexts. For example, it
is possible to declare a variable or method with the name `union`.
-->

Ces mots-clés ont un sens particulier uniquement dans certains contextes. Par
exemple, il est possible de déclarer une variable ou une méthode avec le nom
`union`.

<!--
* `union` is used to declare a [union] and is only a keyword when used in a
  union declaration.
* `'static` is used for the static lifetime and cannot be used as a generic
  lifetime parameter
-->

* `union` est utilisé pour déclarer un [union] et n'est seulement qu'un mot-clé
  lorsqu'il est utilisé dans une déclaration d'un union.
* `'static` est utilisé pour la durée de vie statique et ne peut pas être
  utilisé comme étant un parmètre de durée de vie générique.

<!--
  ```compile_fail
  // error[E0262]: invalid lifetime parameter name: `'static`
  fn invalid_lifetime_parameter<'static>(s: &'static str) -> &'static str { s }
  ```
-->

  ```compile_fail
  // error[E0262]: invalid lifetime parameter name: `'static`
  fn parametre_de_duree_de_vie_invalide<'static>(s: &'static str) -> &'static str { s }
  ```

<!--
* In the 2015 edition, [`dyn`] is a keyword when used in a type position
  followed by a path that does not start with `::`.
-->

* Dans l'édition de 2015, [`dyn`] était un mot-clé lorsqu'il est utilisé dans
  un emplacement de type suivi par un chemin qui ne commence pas par `::`.

<!--
  Beginning in the 2018 edition, `dyn` has been promoted to a strict keyword.
-->

  Dès la création de l'édition 2018, `dyn` est devenu un mot-clé strict.

<!--
> **<sup>Lexer</sup>**\
> KW_UNION          : `union`\
> KW_STATICLIFETIME : `'static`
>
> **<sup>Lexer 2015</sup>**\
> KW_DYN            : `dyn`
-->

> **<sup>Lexème</sup>**\
> KW_UNION          : `union`\
> KW_STATICLIFETIME : `'static`
>
> **<sup>Lexème uniquement pour l'édition 2015</sup>**\
> KW_DYN            : `dyn`

<!--
[items]: items.md
[Variables]: variables.md
[Type parameters]: types/parameters.md
[loop labels]: expressions/loop-expr.md#loop-labels
[Macros]: macros.md
[attributes]: attributes.md
[Macro placeholders]: macros-by-example.md
[Crates]: crates-and-source-files.md
[union]: items/unions.md
[variants]: items/enumerations.md
[`dyn`]: types/trait-object.md
-->

[items]: items.md
[Variables]: variables.md
[Type parameters]: types/parameters.md
[loop labels]: expressions/loop-expr.md
[Macros]: macros.md
[attributes]: attributes.md
[Macro placeholders]: macros-by-example.md
[Crates]: crates-and-source-files.md
[union]: items/unions.md
[variants]: items/enumerations.md
[`dyn`]: types/trait-object.md
