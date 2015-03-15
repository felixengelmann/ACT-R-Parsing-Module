ACT-R-Parsing-Module
====================

A module for simulating sentence parsing in ACT-R in parallel to other cognition.

The module defines two new retrieval buffers that can be used in parallel:

  - `GRAMMATICAL`
  - `LEXICAL`

For the grammatical buffer, chunk duplication in DM can be switched off with `(sgp :gram-force-merge T)`.

Other buffers are:

  - `CONTEXTUAL` (can be used to, e.g., store the contents of the lexical buffer)
  - `STRUCTURAL`, `STRUCTURAL2`, `STRUCTURAL3` (act like goal buffer, to create syntactic nodes)

The module uses the following parameters:

  - `:gram-lf` (:lf for grammatical buffer)
  - `:gram-rt` (:rt factor for grammatical buffer)
  - `:lex-lf`  (:lf for lexical buffer)
  - `:lex-rt`  (:rt for lexical buffer)
  - `:gram-force-merge` (If T, then chunks retrieved and manipulated in the grammatical buffer will always be merged with their originals in DM by updating their slots, so no chunks will be duplicated in DM.)


### Interface functions

  - `(parsing-begin word index location)` Set begin of attachment.
  - `(parsing-complete)` Set end of attachment.
  - `(parsing-abort)` Set end of attachment, indicating attachment was canceled.
  - `(parsing-check-attached index)` Check if word is already attached.

#### Parsing state information

  - `(parsing-get-index)`
  - `(parsing-get-word)`
  - `(parsing-get-loc)`
  - `(parsing-get-durations)`
  - `(parsing-get-attached-items)`
  - `(parsing-get-attached-positions)`
  - `(parsing-get-unattached-positions)`
  - `(parsing-print-info)` Displays info about parsing state, current word and location, and attached items.

#### IP maintenance
  - `(parsing-current-ip)`
  - `(parsing-set-current-ip)`
  - `(parsing-pop-current-ip)`
  - `(parsing-mod-current-ip)`
  - `(parsing-read-current-ip-slot)`

#### Clause stack maintenance
  - `(parsing-current-clause)`
  - `(parsing-push-clause)`
  - `(parsing-pop-clause)`
