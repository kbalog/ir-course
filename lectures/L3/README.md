# L3: Search engine architecture and basic retrieval models

This is the first of several lectures on to the topic of information retrieval. After clarifying the differences from database systems, we discuss the architecture of search engines and two main processes (indexing and querying). We introduce a special data structure, the inverted index, to allow for efficient scoring of large document collections. Finally, we present two main families of retrieval models (vector space and language models) and some of their variants.

## Lecture videos and slides

| **Module** | **Topic** | **Lecture material** | 
| -- | -- | -- | 
| L3-1 | Search engine architecture | [lecture video](https://youtu.be/ar_XNgaimys), [slides](https://speakerdeck.com/kbalog/information-retrieval-and-text-mining-2021-search-engine-architecture) |
| L3-2 | Indexing and query processing | [lecture video](https://youtu.be/JNXn6BV9lMM), [slides](https://speakerdeck.com/kbalog/information-retrieval-and-text-mining-2021-indexing-and-query-processing) |
| L3-3 | Retrieval models | [lecture video](https://youtu.be/EAqjKmSbIzk), [slides](https://speakerdeck.com/kbalog/information-retrieval-and-text-mining-2021-retrieval-models) |

## Reading

  * Text Data Management and Analysis (Zhai & Massung)
    - Chapter 5: Sections 5.3, 5.4
    - Chapter 6
    - Chapter 8: Sections 8.2, 8.3 (optionally, 8.5, 8.6)
    - Chapter 10: Section 10.1 (optionally, 10.2)
  
## Summary

Key concepts in this lecture:

  * The problem of information retrieval and core issues (information needs, relevance, evaluation)
  * Main components of search engines; indexing and querying processes
  * Inverted index (posting list, posting)
  * Index creation (without payload, with counts, with position information)
  * Query processing (term-at-a-time and document-at-a-time scoring)
  * General scoring function
  * Vector space model, TF-IDF and BM25 retrieval models
  * Language models (query likelihood scoring, different smoothing methods)
  * Fielded extensions of retrieval models (BM25F, MLM)
