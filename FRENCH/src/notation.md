<!--
# Notation
-->

# Annotation

<!--
## Grammar
-->

## Grammaire

<!--
The following notations are used by the *Lexer* and *Syntax* grammar snippets:
-->

Les annotations suivantes sont utilisées dans les extraits de code pour le
*Lexer* et la *Syntaxe* :

<!--
| Notation          | Examples                      | Meaning                                   |
|-------------------|-------------------------------|-------------------------------------------|
| CAPITAL           | KW_IF, INTEGER_LITERAL        | A token produced by the lexer             |
| _ItalicCamelCase_ | _LetStatement_, _Item_        | A syntactical production                  |
| `string`          | `x`, `while`, `*`             | The exact character(s)                    |
| \\x               | \\n, \\r, \\t, \\0            | The character represented by this escape  |
| x<sup>?</sup>     | `pub`<sup>?</sup>             | An optional item                          |
| x<sup>\*</sup>    | _OuterAttribute_<sup>\*</sup> | 0 or more of x                            |
| x<sup>+</sup>     |  _MacroMatch_<sup>+</sup>     | 1 or more of x                            |
| x<sup>a..b</sup>  | HEX_DIGIT<sup>1..6</sup>      | a to b repetitions of x                   |
| \|                | `u8` \| `u16`, Block \| Item  | Either one or another                     |
| [ ]               | [`b` `B`]                     | Any of the characters listed              |
| [ - ]             | [`a`-`z`]                     | Any of the characters in the range        |
| ~[ ]              | ~[`b` `B`]                    | Any characters, except those listed       |
| ~`string`         | ~`\n`, ~`*/`                  | Any characters, except this sequence      |
| ( )               | (`,` _Parameter_)<sup>?</sup> | Groups items                              |
-->

| Annotation              | Exemples                      | Signification                                    |
|-------------------------|-------------------------------|--------------------------------------------------|
| MAJUSCULE               | KW_IF, INTEGER_LITERAL        | Un élément produit par le lexer                  |
| _CamelCase en italique_ | _LetStatement_, _Item_        | Un élément syntaxique qui a été produit          |
| `une chaîne`            | `x`, `while`, `*`             | Ces caractères bien précis                       |
| \\x                     | \\n, \\r, \\t, \\0            | Le caractère représenté par cet échappement      |
| x<sup>?</sup>           | `pub`<sup>?</sup>             | Un élément optionnel                             |
| x<sup>\*</sup>          | _OuterAttribute_<sup>\*</sup> | 0 élément x ou plus                              |
| x<sup>+</sup>           |  _MacroMatch_<sup>+</sup>     | 1 élément x ou plus                              |
| x<sup>a..b</sup>        | HEX_DIGIT<sup>1..6</sup>      | Répétitions de a vers b de l'élément x           |
| \|                      | `u8` \| `u16`, Block \| Item  | Soit l'un, soit l'autre                          |
| [ ]                     | [`b` `B`]                     | Un caractère parmi ceux listés                   |
| [ - ]                   | [`a`-`z`]                     | Un caractère présent dans cet intervalle         |
| ~[ ]                    | ~[`b` `B`]                    | N'importe quel caractère, excepté ceux listés    |
| ~`chaîne`               | ~`\n`, ~`*/`                  | N'importe quels caractères, excepté cette chaîne |
| ( )                     | (`,` _Parameter_)<sup>?</sup> | Groupe d'éléments                                |

<!--
## String table productions
-->

## Les représentations des chaînes de caractères

<!--
Some rules in the grammar &mdash; notably [unary operators], [binary
operators], and [keywords] &mdash; are given in a simplified form: as a listing
of printable strings. These cases form a subset of the rules regarding the
[token][tokens] rule, and are assumed to be the result of a lexical-analysis
phase feeding the parser, driven by a <abbr title="Deterministic Finite
Automaton">DFA</abbr>, operating over the disjunction of all such string table
entries.
-->

Certaines règles de grammaire &mdash; en particulier les [opérateurs
unaires][unary operators], les [opérateurs binaires][binary operators], et
les [mots-clés][keywords] &mdash; sont représentées de manière simplifiée :
elles sont affichées sous la forme de chaînes de caractères. Elles représentent
alors un sous-ensemble des règles relatives à la règle de [la
symbolisation][tokens], et sont supposés être le résultat d'une opération
d'analyse lexicale qui alimente l'analyseur syntaxique, piloté par un
<abbr title="Automate Fini Déterministe">AFD</abbr>, et qui agit sur la
décomposition de toutes les entrées de la table des chaînes de caractères.

<!--
When such a string in `monospace` font occurs inside the grammar,
it is an implicit reference to a single member of such a string table
production. See [tokens] for more information.
-->

Lorsqu'un texte est affiché avec une police de type `monospace` dans de la
grammaire, il s'agit alors d'une référence implicite à un seul membre des
représentations des chaînes de caractères. Consultez la page des
[symbolisations][tokens] pour en savoir plus.

<!--
[binary operators]: expressions/operator-expr.md#arithmetic-and-logical-binary-operators
[keywords]: keywords.md
[tokens]: tokens.md
[unary operators]: expressions/operator-expr.md#borrow-operators
-->

[binary operators]: expressions/operator-expr.md
[keywords]: keywords.md
[tokens]: tokens.md
[unary operators]: expressions/operator-expr.md
