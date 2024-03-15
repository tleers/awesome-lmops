# awesome-llmops

# synthetic data

## metadata generation

Figuring out how to generate metadata at scale.

-> Llama-index's abstractions & scope make it difficult to debug numerous issues. Nonetheless, for a quick PoC on limited datasets, you could end up using it. I've tried and failed to scale it up in production settings - maybe review again after their cloud offering becomes more mature?
* Their approach to "extractors" is interesting but is a bit unclear. Documentation is not complete/up to date
* If you deal with a model-as-a-service with a content moderation filter, and use the IngestionPipeline with Extractors, prepare for a bad time. If you're dealing with large amounts of chunks, as you typically would in a production context, you lose all previous calls if you get an error in the pipeline.
* Caching didn't work out of the box.
* Nodes are a first class citizen, but there's little explanation on how to scale it up in practice, or make it work with modern data technologies. You eventually want to bring it into other representations that are simpler and easier to maintain, especially for other contributors/teams, e.g. in the form of dataframes. Conversion between nodes and other llama index objects is not very well documented, let alone to other types.
-> LangChain -> no.
-> Instructor -> possibly? need to check
