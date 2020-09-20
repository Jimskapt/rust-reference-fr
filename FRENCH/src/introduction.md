<!--
# Introduction
-->

# Introduction

<!--
This book is the primary reference for the Rust programming language. It
provides three kinds of material:
-->

Le livre est la référence principale du langage de programmation Rust. Il
fournit trois types de contenu :

<!--
  - Chapters that informally describe each language construct and their use.
  - Chapters that informally describe the memory model, concurrency model,
    runtime services, linkage model, and debugging facilities.
  - Appendix chapters providing rationale and references to languages that
    influenced the design.
-->

- Des chapitres qui décrivent formellement chaque concept du langage et son
  utilisation.
- Des chapitres qui décrivent formellement le système de mémoire, le système
  de concurrence, les services à l'exécution, le système de liaison, et les
  outils de débogage.
- Des chapitres en annexes qui fournissent les justifications et les
  références aux langages qui ont influencé la conception de Rust.

<!--
<div class="warning">

Warning: This book is incomplete. Documenting everything takes a while. See
the [GitHub issues] for what is not documented in this book.

</div>
-->

<div class="warning">

Attention : ce livre est incomplet. Cela prend du temps de tout documenter.
Consultez les [tickets sur GitHub][GitHub issues] pour voir ce qui n'est pas
encore documenté dans ce livre.

</div>

<!--
## What *The Reference* is Not
-->

## Ce que n'est pas *La référence*

<!--
This book does not serve as an introduction to the language. Background
familiarity with the language is assumed. A separate [book] is available to
help acquire such background familiarity.
-->

Ce livre n'a pas vocation à présenter le langage. Il suppose que vous êtes
suffisamment familier avec le langage. Un [livre dédié à cette
familiarisation est disponible séparément][book-fr] (disponible aussi en
[version anglaise][book]).

<!--
This book also does not serve as a reference to the [standard library]
included in the language distribution. Those libraries are documented
separately by extracting documentation attributes from their source code. Many
of the features that one might expect to be language features are library
features in Rust, so what you're looking for may be there, not here.
-->

Ce livre n'a pas non plus pour vocation de servir de référence à la
[bibliothèque standard][standard library] livrée avec le langage. Cette
bibliothèque est documentée séparément en extrayant les attributs de la
documentation de son code source. De nombreuses fonctionnalités dont on
pourrait s'attendre à ce qu'elles soient fournies par le langage sont en fait
fournies par des bibliothèques en Rust, donc ce que vous cherchez se trouvera
peut-être là-bas et non ici.

<!--
Similarly, this book does not usually document the specifics of `rustc` as a
tool or of Cargo. `rustc` has its own [book][rustc book]. Cargo has a
[book][cargo book] that contains a [reference][cargo reference]. There are a few
pages such as [linkage] that still describe how `rustc` works.
-->

Pour les mêmes raisons, ce livre ne documente pas spécialement les
particularités liées aux outils `rustc` ou Cargo. `rust` a [son propre
livre][rustc book]. Cargo a aussi [un livre][cargo book] qui embarque aussi [une
référence][cargo reference]. Nous avons cependant certaines pages comme par
exemple [les liaisons][linkage] qui décrivent quand même un peu comment `rustc`
fonctionne.

<!--
This book also only serves as a reference to what is available in stable
Rust. For unstable features being worked on, see the [Unstable Book].
-->

Ce livre sert de référence uniquement à ce qui est disponible en Rust stable.
Pour en savoir plus sur les fonctionnalités instables qui sont en cours de
construction, consultez le [Unstable Book].

<!--
Finally, this book is not normative. It may include details that are
specific to `rustc` itself, and should not be taken as a specification for
the Rust language. We intend to produce such a book someday, and until then,
the reference is the closest thing we have to one.
-->

Enfin, ce livre n'est pas une norme. Il peut expliquer des détails qui sont
spécifiques à `rustc`, et ne doivent pas être mélangé avec les spécifications
du langage Rust. Nous avons l'intention d'écrire un livre dédié à cela un jour,
mais en attendant, cette présente référence est celle qui s'en approche le
plus.

<!--
## How to Use This Book
-->

## Comment utiliser ce livre

<!--
This book does not assume you are reading this book sequentially. Each
chapter generally can be read standalone, but will cross-link to other chapters
for facets of the language they refer to, but do not discuss.
-->

Ce livre ne nécessite pas que vous le lisiez dans l'ordre. En général, chaque
chapitre peut être lu de manière indépendante, mais peut s'entrecroiser avec
d'autres chapitres à propos d'autres aspects du langage, mais qu'il ne traitera
pas.

<!--
There are two main ways to read this document.
-->

Il y a deux manières de lire ce document.

<!--
The first is to answer a specific question. If you know which chapter answers
that question, you can jump to that chapter in the table of contents. Otherwise,
you can press `s` or the click the magnifying glass on the top bar to search for
keywords related to your question. For example, say you wanted to know when a
temporary value created in a let statement is dropped. If you didn't already
know that the [lifetime of temporaries] is defined in the [expressions chapter],
you could search "temporary let" and the first search result will take you to
that section.
-->

La première est pour répondre à une question précise. Si vous savez quel
chapitre répond à votre question, vous pouvez vous rendre à ce chapitre avec la
table des matières. Sinon, vous pouvez appuyer sur `s` ou cliquer sur la loupe
dans la barre du haut pour rechercher des mots-clés en lien avec votre
question. Par exemple, imaginons que vous souhaitiez savoir quand une valeur
temporaire créée dans une instruction `let` est libérée. Si vous ne savez
connaissez pas le chapitre [durée de vie des éléments
temporaires][lifetime of temporaries] qui est défini dans le chapitre [des
expressions][expressions chapter], vous pouvez alors chercher `let temporaire`
et le premier résultat devrait vous amener à cette section.

<!--
The second is to generally improve your knowledge of a facet of the language.
In that case, just browse the table of contents until you see something you
want to know more about, and just start reading. If a link looks interesting,
click it, and read about that section.
-->

La seconde manière améliore votre connaissance générale sur des parties
précises du langage. Dans ce cas, il vous suffit de parcourir la table des
matières jusqu'à ce que vous voyez quelque chose d'intéressant, puis cliquez
dessus pour commencer à lire. Et si vous découvrez des liens intéressants
pendant votre lecture, n'hésitez pas à l'ouvrir.

<!--
That said, there is no wrong way to read this book. Read it however you feel
helps you best.
-->

Ceci étant dit, il n'y a pas de mauvaise manière de parcourir ce livre. Donc,
lisez-le comme bon vous semble !

<!--
### Conventions
-->

### Les règles

<!--
Like all technical books, this book has certain conventions in how it displays
information. These conventions are documented here.
-->

Comme tout livre technique, ce livre suit certaines règles qui définissent
comment présenter les informations. Cette partie décrit donc ici ces règles.

<!--
* Statements that define a term contain that term in *italics*. Whenever that
  term is used outside of that chapter, it is usually a link to the section that
  has this definition.

  An *example term* is an example of a term being defined.
-->

* Les parties qui définissent un terme contiennent ce terme sont en
  *italique*. A chaque fois que ce terme est utilisé en dehors de la section
  qui la définit, il y aura généralement un lien vers cette définition.

  Un *exemple de terme* est un exemple d'un terme qui est en train d'être
  défini.

<!--
* Differences in the language by which edition the crate is compiled under are
  in a blockquote that start with the words "Edition Differences:" in **bold**.

  > **Edition Differences**: In the 2015 edition, this syntax is valid that is
  > disallowed as of the 2018 edition.
-->

* Les différences entre les éditions du langage dans lesquelles la crate est
  compilée sont signalées dans des blocs de citation qui commencent par les
  mots "Différences entre les éditions :" **en gras**.

  > **Différences entre les éditions :** dans l'édition 2015, cette syntaxe est
  > valide, alors qu'elle est interdite dans l'édition 2018.

<!--
* Notes that contain useful information about the state of the book or point out
  useful, but mostly out of scope, information are in blockquotes that start
  with the word "Note:" in **bold**.

  > **Note**: This is an example note.
-->

* Les remarques qui contiennent des informations importantes sur le statut de
  ce livre ou qui signalent des informations utiles mais souvent hors de la
  portée du livre sont placées dans des blocs de citation qui commencent par
  le mot "Remarque :" **en gras**.

  > **Remarque :** ceci est un exemple de remarque.

<!--
* Warnings that show unsound behavior in the language or possibly confusing
  interactions of language features are in a special warning box.

  <div class="warning">

  Warning: This is an example warning.

  </div>
-->

* Les avertissements qui mettent en évidence un comportement dangereux ou
  ambigü du langage sont insérés dans des boites d'avertissement spéciales.

  <div class="warning">

  Avertissement : ceci est un exemple d'avertissement.

  </div>

<!--
* Code snippets inline in the text are inside `<code>` tags.

  Longer code examples are in a syntax highlighted box that has controls for
  copying, executing, and showing hidden lines in the top right corner.

  ```rust
  # // This is a hidden line.
  fn main() {
      println!("This is a code example");
  }
  ```
-->

* Les extraits de code insérés directement dans le texte sont placés dans des
  balises `<code>`.

  Les exemples de code plus conséquents sont placés dans des boites de code à
  coloration syntaxique afin de plus facilement copier, exécuter, et afficher
  les lignes via les contrôles dans le coin en haut à droite.

<!--
* The grammar and lexical structure is in blockquotes with either "Lexer" or
  "Syntax" in <sup>**bold superscript**</sup> as the first line.

  > **<sup>Syntax</sup>**\
  > _ExampleGrammar_:\
  > &nbsp;&nbsp; &nbsp;&nbsp; `~` [_Expression_]\
  > &nbsp;&nbsp; | `box` [_Expression_]

  See [Notation] for more detail.
-->

* La grammaire et structure lexicale sont placés dans des blocs de citation
  avec en première ligne "Lexer" ou "Syntaxe" en <sup>**exposant gras**</sup>.

  > **<sup>Syntaxe</sup>**\
  > _ExempleDeGrammaire_:\
  > &nbsp;&nbsp; &nbsp;&nbsp; `~` [_Expression_]\
  > &nbsp;&nbsp; | `box` [_Expression_]

  Consultez la page [Annotation][Notation] pour en savoir plus.

<!--
## Contributing
-->

## Contribuer

<!--
We welcome contributions of all kinds.
-->

Nous sommes ouverts aux contributions de n'importe quel type.

<!--
You can contribute to this book by opening an issue or sending a pull
request to [the Rust Reference repository]. If this book does not answer
your question, and you think its answer is in scope of it, please do not
hesitate to file an issue or ask about it in the `#docs` channels on
[Discord]. Knowing what people use this book for the most helps direct our
attention to making those sections the best that they can be.
-->

Vous pouvez contribuer à ce livre en ouvrant un ticket ou envoyer une Pull
Request dans [le dépôt de la référence Rust][the Rust Reference repository]. Si
ce livre ne répond pas à votre question, que vous jugez que la réponse rentre
dans le cadre du livre, n'hésitez pas à ouvrir un ticket ou parlez-en dans les
canaux `#docs` du [Discord]. Cela nous permet d'en savoir plus sur la manière
dont les gens utilisent ce livre pour prioriser l'optimisation de ces sections.

Si vous souhaitez contribuer à la traduction de ce livre en français, vous
pouvez faire de même dans le dépôt GitHub [rust-reference-fr].

<!--
[book]: ../book/index.html
[github issues]: https://github.com/rust-lang/reference/issues
[standard library]: ../std/index.html
[the Rust Reference repository]: https://github.com/rust-lang/reference/
[Unstable Book]: https://doc.rust-lang.org/nightly/unstable-book/
[_Expression_]: expressions.md
[cargo book]: ../cargo/index.html
[cargo reference]: ../cargo/reference/index.html
[expressions chapter]: expressions.html
[lifetime of temporaries]: expressions.html#temporaries
[linkage]: linkage.html
[rustc book]: ../rustc/index.html
[Notation]: notation.md
[Discord]: https://discord.gg/rust-lang
-->

[book]: https://doc.rust-lang.org/book/index.html
[github issues]: https://github.com/rust-lang/reference/issues
[standard library]: https://doc.rust-lang.org/std/index.html
[the Rust Reference repository]: https://github.com/rust-lang/reference/
[Unstable Book]: https://doc.rust-lang.org/nightly/unstable-book/
[_Expression_]: expressions.md
[cargo book]: https://doc.rust-lang.org/cargo/index.html
[cargo reference]: https://doc.rust-lang.org/cargo/reference/index.html
[expressions chapter]: expressions.html
[lifetime of temporaries]: expressions.html
[linkage]: linkage.html
[rustc book]: https://doc.rust-lang.org/rustc/index.html
[Notation]: notation.md
[Discord]: https://discord.gg/rust-lang

[book-fr]: https://jimskapt.github.io/rust-book-fr/
[rust-reference-fr]: https://github.com/Jimskapt/rust-reference-fr
