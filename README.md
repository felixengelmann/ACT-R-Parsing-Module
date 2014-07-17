ACT-R-Parsing-Module
====================

A module for simulating sentence parsing in ACT-R in parallel to other cognition.

The module defines two new retrieval buffers that can be used in parallel:
  - GRAMMATICAL
  - LEXICAL

For the grammatical buffer, chunk duplication in DM can be switched off with (sgp :gram-force-merge T).

Other buffers are:
  - CONTEXTUAL (can be used to, e.g., store the contents of the lexical buffer)
  - STRUCTURAL, STRUCTURAL2, STRUCTURAL3 (act like goal buffer, to create syntactic nodes)

The module uses the following parameters:
  - :gram-lf (:lf for grammatical buffer)
  - :gram-rt (:rt factor for grammatical buffer)
  - :lex-lf  (:lf for lexical buffer)
  - :lex-rt  (:rt for lexical buffer)
  - :gram-force-merge (If T, then chunks retrieved and manipulated in the grammatical buffer will always be merged with their originals in DM by updating their slots, so no chunks will be duplicated in DM.)
