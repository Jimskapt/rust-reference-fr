<!--
# Whitespace
-->

# Les espaces

<!--
Whitespace is any non-empty string containing only characters that have the
[`Pattern_White_Space`] Unicode property, namely:
-->

Un espace est une chaîne de caractères non vide qui contient uniquement des
caractères qui ont uniquement la propriété Unicode [`Pattern_White_Space`], à
savoir :

<!--
- `U+0009` (horizontal tab, `'\t'`)
- `U+000A` (line feed, `'\n'`)
- `U+000B` (vertical tab)
- `U+000C` (form feed)
- `U+000D` (carriage return, `'\r'`)
- `U+0020` (space, `' '`)
- `U+0085` (next line)
- `U+200E` (left-to-right mark)
- `U+200F` (right-to-left mark)
- `U+2028` (line separator)
- `U+2029` (paragraph separator)
-->

- `U+0009` (tabulation horizontale, `'\t'`)
- `U+000A` (saut de ligne, `'\n'`)
- `U+000B` (tabulation verticale)
- `U+000C` (saut de page)
- `U+000D` (retour chariot, `'\r'`)
- `U+0020` (espace, `' '`)
- `U+0085` (ligne suivante)
- `U+200E` (marque de gauche à droite)
- `U+200F` (marque de droite à gauche)
- `U+2028` (séparateur de ligne)
- `U+2029` (séparateur de paragraphe)

<!--
Rust is a "free-form" language, meaning that all forms of whitespace serve only
to separate _tokens_ in the grammar, and have no semantic significance.
-->

Rust est un langage "à forme libre", ce qui veut dire que toutes les formes
d'espaces servent uniquement à séparer les [_symbolisations_][_tokens_] dans la
grammaire, et n'ont pas de sens sémantiquement parlant.

<!--
A Rust program has identical meaning if each whitespace element is replaced
with any other legal whitespace element, such as a single space character.
-->

Un programme Rust est identique si chaque espace est remplacé par n'importe
quel autre type espace reconnu comme tel, comme par exemple un caractère
"espace" simple (`U+0020`).

<!--
[`Pattern_White_Space`]: https://www.unicode.org/reports/tr31/
-->

[`Pattern_White_Space`]: https://www.unicode.org/reports/tr31/

[_tokens_]: tokens.md
