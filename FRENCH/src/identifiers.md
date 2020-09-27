<!--
# Identifiers
-->

# Les identifiants

<!--
> **<sup>Lexer:<sup>**\
> IDENTIFIER_OR_KEYWORD :\
> &nbsp;&nbsp; &nbsp;&nbsp; [`a`-`z` `A`-`Z`]&nbsp;[`a`-`z` `A`-`Z` `0`-`9` `_`]<sup>\*</sup>\
> &nbsp;&nbsp; | `_` [`a`-`z` `A`-`Z` `0`-`9` `_`]<sup>+</sup>
>
> RAW_IDENTIFIER : `r#` IDENTIFIER_OR_KEYWORD <sub>*Except `crate`, `self`, `super`, `Self`*</sub>
>
> NON_KEYWORD_IDENTIFIER : IDENTIFIER_OR_KEYWORD <sub>*Except a [strict] or [reserved] keyword*</sub>
>
> IDENTIFIER :\
> NON_KEYWORD_IDENTIFIER | RAW_IDENTIFIER
-->

> **<sup>Lexème :</sup>**\
> IDENTIFIANT_OU_MOT_CLE =\
> &nbsp;&nbsp; &nbsp;&nbsp; [`a`-`z` `A`-`Z`]&nbsp;[`a`-`z` `A`-`Z` `0`-`9` `_`]<sup>\*</sup>\
> &nbsp;&nbsp; | `_` [`a`-`z` `A`-`Z` `0`-`9` `_`]<sup>+</sup>
>
> IDENTIFIANT_BRUT = `r#` IDENTIFIANT_OU_MOT_CLE <sub>*Excepté `crate`, `self`, `super` ou `Self`*</sub>
>
> IDENTIFIANT_NON_MOT_CLE = IDENTIFCATEUR_OU_MOT_CLE <sub>*Excepté un mot-clé [strict] ou [réservé][reserved]*</sub>
>
> IDENTIFIANT =\
> IDENTIFIANT_NON_MOT_CLE | IDENTIFIANT_BRUT

<!--
An identifier is any nonempty ASCII string of the following form:
-->

Un identifiant est une chaîne de caractères ASCII non vide constitué de :

<!--
Either

* The first character is a letter.
* The remaining characters are alphanumeric or `_`.
-->

Soit ...

* Le premiere caractère est une lettre.
* Les caractères suivants sont alphanumériques ou le caractère `_`.

<!--
Or

* The first character is `_`.
* The identifier is more than one character. `_` alone is not an identifier.
* The remaining characters are alphanumeric or `_`.
-->

... ou alors

* Le premier caractère est `_`.
* L'identifiant est constitué de plus d'un caractère.
  `_` tout seul n'est pas un identifiant.
* Les caractères suivant sont alphanumériques ou le caractère `_`.

<!--
A raw identifier is like a normal identifier, but prefixed by `r#`. (Note that
the `r#` prefix is not included as part of the actual identifier.)
Unlike a normal identifier, a raw identifier may be any strict or reserved
keyword except the ones listed above for `RAW_IDENTIFIER`.
-->

Un identifiant brut est la même chose qu'un identifiant normal, mais
avec un préfixe `r#` (notez que le préfixe `r#` ne fait pas partie de
l'identifiant).
Contrairement à un identifiant normal, un identifiant brut peut être un mot-clé
strict ou réservé, à l'exception de ceux cité au ci-dessus dans la définition
de `IDENTIFIANT_BRUT`.

<!--
[strict]: keywords.md#strict-keywords
[reserved]: keywords.md#reserved-keywords
-->

[strict]: keywords.md#les-mots-cles-stricts
[reserved]: keywords.md#les-mots-cles-reserves
