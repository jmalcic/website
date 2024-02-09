---
title: Experimental version control system
---

Prototype VCS tracking AST mutations (not plaintext) in a language-independent format, to allow more granular and intuitive change history, and more extensive and accurate automatic conflict resolution.

Language Server API used to create temporary source trees with syntactic features and random node IDs. File modifications drive continuous subtree matching on syntactic features, to keep IDs stable across edits. ID set comparison, and node pair equality checks for parent and position, give changes between base and revision. Commits record tree mutations—insertion, deletion, transposition—not unstructured diffs. IDs allows ‘identical’ nodes with distinct origins to be distinguished over time.
