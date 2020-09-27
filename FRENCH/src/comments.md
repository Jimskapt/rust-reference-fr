<!--
# Comments
-->

# Les commentaires

<!--
> **<sup>Lexer</sup>**\
> LINE_COMMENT :\
> &nbsp;&nbsp; &nbsp;&nbsp; `//` (~[`/` `!`] | `//`) ~`\n`<sup>\*</sup>\
> &nbsp;&nbsp; | `//`
>
> BLOCK_COMMENT :\
> &nbsp;&nbsp; &nbsp;&nbsp; `/*` (~[`*` `!`] | `**` | _BlockCommentOrDoc_)
>      (_BlockCommentOrDoc_ | ~`*/`)<sup>\*</sup> `*/`\
> &nbsp;&nbsp; | `/**/`\
> &nbsp;&nbsp; | `/***/`
>
> INNER_LINE_DOC :\
> &nbsp;&nbsp; `//!` ~[`\n` _IsolatedCR_]<sup>\*</sup>
>
> INNER_BLOCK_DOC :\
> &nbsp;&nbsp; `/*!` ( _BlockCommentOrDoc_ | ~[`*/` _IsolatedCR_] )<sup>\*</sup> `*/`
>
> OUTER_LINE_DOC :\
> &nbsp;&nbsp; `///` (~`/` ~[`\n` _IsolatedCR_]<sup>\*</sup>)<sup>?</sup>
>
> OUTER_BLOCK_DOC :\
> &nbsp;&nbsp; `/**` (~`*` | _BlockCommentOrDoc_ )
>              (_BlockCommentOrDoc_ | ~[`*/` _IsolatedCR_])<sup>\*</sup> `*/`
>
> _BlockCommentOrDoc_ :\
> &nbsp;&nbsp; &nbsp;&nbsp; BLOCK_COMMENT\
> &nbsp;&nbsp; | OUTER_BLOCK_DOC\
> &nbsp;&nbsp; | INNER_BLOCK_DOC
>
> _IsolatedCR_ :\
> &nbsp;&nbsp; _A `\r` not followed by a `\n`_
-->

> **<sup>Lexème</sup>**\
> LIGNE_DE_COMMENTAIRE =\
> &nbsp;&nbsp; &nbsp;&nbsp; `//` (~[`/` `!`] | `//`) ~`\n`<sup>\*</sup>\
> &nbsp;&nbsp; | `//`
>
> BLOC_DE_COMMENTAIRE =\
> &nbsp;&nbsp; &nbsp;&nbsp; `/*` (~[`*` `!`] | `**` | _BlocDeCommentaireOuDeDoc_)
>      (_BlocDeCommentaireOuDeDoc_ | ~`*/`)<sup>\*</sup> `*/`\
> &nbsp;&nbsp; | `/**/`\
> &nbsp;&nbsp; | `/***/`
>
> #########################################################
>
> LIGNE_DE_DOCUMENTATION_INTERNE =\
> &nbsp;&nbsp; `//!` ~[`\n` _RetourChariotIsolé_]<sup>\*</sup>
>
> BLOC_DOCUMENTATION_INTERNE =\
> &nbsp;&nbsp; `/*!` ( _BlocDeCommentaireOuDeDoc_ | ~[`*/` _RetourChariotIsolé_] )<sup>\*</sup> `*/`
>
> #########################################################
>
> LIGNE_DE_DOCUMENTATION_EXTERNE :\
> &nbsp;&nbsp; `///` (~`/` ~[`\n` _RetourChariotIsolé_]<sup>\*</sup>)<sup>?</sup>
>
> BLOC_DOCUMENTATION_EXTERNE :\
> &nbsp;&nbsp; `/**` (~`*` | _BlocDeCommentaireOuDeDoc_ )
>              (_BlocDeCommentaireOuDeDoc_ | ~[`*/` _RetourChariotIsolé_])<sup>\*</sup> `*/`
>
> #########################################################
>
> _BlocDeCommentaireOuDeDoc_ =\
> &nbsp;&nbsp; &nbsp;&nbsp; BLOC_DE_COMMENTAIRE\
> &nbsp;&nbsp; | BLOC_DOCUMENTATION_EXTERNE\
> &nbsp;&nbsp; | BLOC_DOCUMENTATION_INTERNE
>
> _RetourChariotIsolé_ =\
> &nbsp;&nbsp; _Un `\r` qui n'est pas suivi d'un `\n`_

<!--
## Non-doc comments
-->

## Les commentaires qui ne sont pas de la documentation

<!--
Comments in Rust code follow the general C++ style of line (`//`) and
block (`/* ... */`) comment forms. Nested block comments are supported.
-->

Les commentaires dans le code Rust suivent le style général des formes des
lignes et des blocs de commentaire du C++ (`/* ... */`). Les blocs de
commentaires imbriqués sont aussi possibles.

<!--
Non-doc comments are interpreted as a form of whitespace.
-->

Les commentaires qui ne sont pas de la documentation sont interprétés comme
étant une forme [d'espace][whitespace].

<!--
## Doc comments
-->

## Commentaires de documentation

<!--
Line doc comments beginning with exactly _three_ slashes (`///`), and block
doc comments (`/** ... */`), both inner doc comments, are interpreted as a
special syntax for [`doc` attributes]. That is, they are equivalent to writing
`#[doc="..."]` around the body of the comment, i.e., `/// Foo` turns into
`#[doc="Foo"]` and `/** Bar */` turns into `#[doc="Bar"]`.
-->

Les commentaires de documentation commencent exactement pas _trois_ barres
obliques (`///`), et les blocs de commentaires de documentation (`/** ... */`),
qu'ils aient une portée interne ou externe, sont interprétés comme étant une
syntaxe spéciale pour [les attributs `doc`][`doc` attributes]. En d'autres
termes, cela revient à écrire `#[doc="..."]` autour du commentaire, par
exemple, `/// Commentaire` équivaut à `#[doc="Commentaire"]` et
`/** Commentaire */` revient à écrire `#[doc="Commentaire"]`.

<!--
Line comments beginning with `//!` and block comments `/*! ... */` are
doc comments that apply to the parent of the comment, rather than the item
that follows.  That is, they are equivalent to writing `#![doc="..."]` around
the body of the comment. `//!` comments are usually used to document
modules that occupy a source file.
-->

Les lignes de commentaires qui commencent par `//!` et les blocs de
commentaires `/*! ... */` sont des commentaires de documentation qui
s'appliquent sur le parent du commentaire, plutôt que sur l'élément qui le
suit. Cela signifie qu'ils sont équivalents à écrire `#![doc="..."]` autour du
commentaire. Les commentaires `//!` sont généralement utilisés pour documenter
les modules qui sont présents dans un fichier source.

<!--
Isolated CRs (`\r`), i.e. not followed by LF (`\n`), are not allowed in doc
comments.
-->

Les retours chariots isolés (`\r`), comme ceux qui ne sont pas suivis par LF
(`\n`), ne sont pas autorisés dans les blocs de commentaires.

<!--
## Examples
-->

## Exemples

<!--
```rust
//! A doc comment that applies to the implicit anonymous module of this crate

pub mod outer_module {

    //!  - Inner line doc
    //!! - Still an inner line doc (but with a bang at the beginning)

    /*!  - Inner block doc */
    /*!! - Still an inner block doc (but with a bang at the beginning) */

    //   - Only a comment
    ///  - Outer line doc (exactly 3 slashes)
    //// - Only a comment

    /*   - Only a comment */
    /**  - Outer block doc (exactly) 2 asterisks */
    /*** - Only a comment */

    pub mod inner_module {}

    pub mod nested_comments {
        /* In Rust /* we can /* nest comments */ */ */

        // All three types of block comments can contain or be nested inside
        // any other type:

        /*   /* */  /** */  /*! */  */
        /*!  /* */  /** */  /*! */  */
        /**  /* */  /** */  /*! */  */
        pub mod dummy_item {}
    }

    pub mod degenerate_cases {
        // empty inner line doc
        //!

        // empty inner block doc
        /*!*/

        // empty line comment
        //

        // empty outer line doc
        ///

        // empty block comment
        /**/

        pub mod dummy_item {}

        // empty 2-asterisk block isn't a doc block, it is a block comment
        /***/

    }

    /* The next one isn't allowed because outer doc comments
       require an item that will receive the doc */

    /// Where is my item?
#   mod boo {}
}
```
-->

```rust
//! Un commentaire de documentation qui s'applique sur le module anonyme
//! implicite de cette crate

pub mod module_externe {

    //!  - Une ligne de documentation interne
    //!! - Toujours une ligne de documentation interne
    //!!   (mais qui commence par un point d'exclamation supplémentaire au début)

    /*!  - Un bloc de documentation interne */
    /*!! - Toujours un bloc de documentation interne
           (mais qui commence par un point d'exclamation supplémentaire au début)
    */

    //   - Un simple commentaire
    ///  - Un commentaire de documentation externe (3 barres obliques précisément)
    //// - Un simple commentaire

    /*   - Un simple commentaire */
    /**  - Un commentaire de documentation externe (2 astérisques précisément) */
    /*** - Un simple commentaire */

    pub mod module_interne {}

    pub mod commentaires_imbrique {
        /* En Rust /* nous pouvons /* imbriquer des commentaires */ */ */

        // Tous les trois types de blocs de commentaires peuvent contenir ou
        // être imbriqué dans n'importe quel autre type de commentaire :

        /*   /* */  /** */  /*! */  */
        /*!  /* */  /** */  /*! */  */
        /**  /* */  /** */  /*! */  */
        pub mod element_bidon {}
    }

    pub mod cas_erreurs {
        // une ligne de documentation interne vide :
        //!

        // un bloc de documentation interne vide :
        /*!*/

        // une ligne de commentaire vide :
        //

        // une ligne de documentation externe vide :
        ///

        // un bloc de comentaire vide :
        /**/

        pub mod element_bidon {}

        // un bloc vide avec 2 astérisques n'est pas interprété comme un bloc
        // de documentation, mais comme un bloc de commentaire :
        /***/
    }

    /* Ce qui suit n'es pas autorisé car les commentaires de documentation
       externes nécéssitent d'avoir un élement sur lequel la documentation va
       s'appliquer
    */

    /// Où est l'élément sur lequel appliquer ce commentaire ?
#   mod boo {}
}
```

<!--
[`doc` attributes]: ../rustdoc/the-doc-attribute.html
-->

[`doc` attributes]: https://doc.rust-lang.org/rustdoc/the-doc-attribute.html

[whitespace]: whitespace.md
