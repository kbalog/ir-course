# L6: Entity-Oriented Search Part I: Entity Ranking

This module is the first of a series on entity-oriented search.  It introduces the concept of entities, the problem of entity-oriented search, and relevant data sources.  Then, it deals in depth with the problem of ad hoc entity retrieval, which is the task of ranking entities given a keyword query.  A core part revolves around constructing term-based representations of entities, which can then be ranked using traditional document retrieval models (such as LM, BM25 or their fielded variants).  Some more advanced document retrieval models will also be introduced, which may be applied for entities (PRMS, SDM, FSDM).  Finally, we will consider enriching these term-based representations with explicit references to entities.

**NOTE**: Pay attention to which specific sections from the book are marked as part of the curriculum.  Specifically, some sections are either not needed (e.g., Section 1.2) or have already been covered in previous lectures (retrieval models LM, BM25 and their fielded variants, as well as evaluation in Chapter 3).  Of course, you're welcome to read those parts as well if you are interested (or want a refresher).  Generally, the slides provide guidance on what is included and what is not.

**NOTE 2**: As mentioned before, there will be videos for the entity-oriented search modules, but those will come later.

## Lecture videos and slides

| **Module** | **Topic** | **Lecture material** | 
| -- | -- | -- | 
| L6-1 | Entities and data sources | Read: Balog: Chapters 1 and 2, [slides]() |
| L6-2 | Entity ranking | Read: Balog: Chapters 3 and 4, [slides]() |

## Reading

  * Entity-Oriented Search (Balog)
    - Chapter 1, except 1.2
    - Chapter 2
    - Chapter 3, until 3.3.2 (inclusive)
    - Chapter 4: Sections 4.1 and 4.2.2
  
## Summary

Key concepts in this lecture:

  * Entities (named entities vs. concepts)
  * Entity-oriented search vs. semantic search
  * Properties of entities (unique IDs, names, types, attributes, relationships)
  * Entity catalog, knowledge repository, knowledge base/graph
  * Wikipedia article structure
  * Resource Description Framework (RDF)
  * The ad hoc entity retrieval task
  * Constructing entity description documents from unstructured, semi-structured, and structured sources
  * Working with SPO triples (predicate folding and URI resolution)
  * Ranking entities using standard document retrieval models (LM, BM25, MLM, BM25F)
  * Sequential Dependence Models (SDM) and fielded variant (FSDM)
  * Probabilistic Retrieval Model for Semi-Structured Data (PRMS)
  * Dual entity representation, Entity Linking incorporated Retrieval (ELR) model