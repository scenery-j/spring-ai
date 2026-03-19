# Spring AI [![build status](https://github.com/spring-projects/spring-ai/actions/workflows/continuous-integration.yml/badge.svg)](https://github.com/spring-projects/spring-ai/actions/workflows/continuous-integration.yml) [![build status](https://github.com/spring-projects/spring-ai-integration-tests/actions/workflows/spring-ai-integration-tests.yml/badge.svg)](https://github.com/spring-projects/spring-ai-integration-tests/actions/workflows/spring-ai-integration-tests.yml) [![Maven Central](https://img.shields.io/maven-central/v/org.springframework.ai/spring-ai-model?label=Maven%20Central&versionPrefix=2.0)](https://central.sonatype.com/artifact/org.springframework.ai/spring-ai-model)

### Spring Boot Version Compatibility

> **Spring AI 2.x.x** ([main](https://github.com/spring-projects/spring-ai/tree/main) branch) - Spring Boot `4.x`
>
> **Spring AI 1.1.x** ([1.1.x](https://github.com/spring-projects/spring-ai/tree/1.1.x) branch) - Spring Boot `3.5.x`

The Spring AI project provides a Spring-friendly API and abstractions for developing AI applications.

Its goal is to apply Spring ecosystem design principles like portability and modular design to the AI domain, promoting the use of POJOs as application building blocks in AI development.

![spring-ai-integration-diagram-3](https://docs.spring.io/spring-ai/reference/_images/spring-ai-integration-diagram-3.svg)

> At its core, Spring AI addresses the fundamental challenge of AI integration: Connecting your enterprise __Data__ and __APIs__ with the __AI Models__.

The project draws inspiration from notable Python projects like [LangChain](https://docs.langchain.com/docs/) and [LlamaIndex](https://gpt-index.readthedocs.io/en/latest/getting_started/concepts.html), but Spring AI is not a direct port. The project was founded on the belief that the next wave of Generative AI applications will extend beyond Python developers to become ubiquitous across multiple programming languages.

For additional motivations, see the blog post [Why Spring AI](https://spring.io/blog/2024/11/19/why-spring-ai).

This is a high-level feature overview. Detailed information is available in the [Reference Documentation](https://docs.spring.io/spring-ai/reference/).

* Support for all major [AI Model providers](https://docs.spring.io/spring-ai/reference/api/index.html) including Anthropic, OpenAI, Microsoft, Amazon, Google, and Ollama. Supported model types:
  - [Chat Completion](https://docs.spring.io/spring-ai/reference/api/chatmodel.html)
  - [Embedding](https://docs.spring.io/spring-ai/reference/api/embeddings.html)
  - [Text to Image](https://docs.spring.io/spring-ai/reference/api/imageclient.html)
  - [Audio Transcription](https://docs.spring.io/spring-ai/reference/api/audio/transcriptions.html)
  - [Text to Speech](https://docs.spring.io/spring-ai/reference/api/audio/speech.html)
  - [Moderation](https://docs.spring.io/spring-ai/reference/api/index.html#api/moderation)
  - **Latest Models**: GPT-5 and other cutting-edge models for advanced AI applications.
* Portable API support across AI providers for both synchronous and streaming options, including access to [model-specific features](https://docs.spring.io/spring-ai/reference/api/chatmodel.html#_chat_options).
* [Structured Outputs](https://docs.spring.io/spring-ai/reference/api/structured-output-converter.html) - Mapping AI Model output to POJOs.
* Support for all major [Vector Database providers](https://docs.spring.io/spring-ai/reference/api/vectordbs.html) including *Apache Cassandra, Azure Vector Search, Chroma, Elasticsearch, Milvus, MongoDB Atlas, MariaDB, Neo4j, Oracle, PostgreSQL/PGVector, Pinecone, Qdrant, Redis, and Weaviate*.
* Portable API across Vector Store providers with a novel SQL-like [metadata filter API](https://docs.spring.io/spring-ai/reference/api/vectordbs.html#metadata-filters).
* [Tools/Function Calling](https://docs.spring.io/spring-ai/reference/api/tools.html) - Enables models to request client-side tool/function execution for real-time information access.
* [Observability](https://docs.spring.io/spring-ai/reference/observability/index.html) - Provides insights into AI operations.
* Document injection [ETL framework](https://docs.spring.io/spring-ai/reference/api/etl-pipeline.html) for Data Engineering.
* [AI Model Evaluation](https://docs.spring.io/spring-ai/reference/api/testing.html) - Utilities for evaluating generated content and guarding against hallucinated responses.
* [ChatClient API](https://docs.spring.io/spring-ai/reference/api/chatclient.html) - Fluent API for AI Chat Model communication, similar to WebClient and RestClient APIs.
* [Advisors API](https://docs.spring.io/spring-ai/reference/api/advisors.html) - Encapsulates recurring Generative AI patterns, transforms data for Language Models (LLMs), and ensures portability across models and use cases.
* Support for [Chat Conversation Memory](https://docs.spring.io/spring-ai/reference/api/chatclient.html#_chat_memory) and [Retrieval Augmented Generation (RAG)](https://docs.spring.io/spring-ai/reference/api/chatclient.html#_retrieval_augmented_generation).
* Spring Boot Auto Configuration and Starters for all AI Models and Vector Stores - use [start.spring.io](https://start.spring.io/) to select preferred Models or Vector Stores.

## Getting Started

Refer to the [Getting Started Guide](https://docs.spring.io/spring-ai/reference/getting-started.html) for dependency setup instructions.

## Project Resources

* [Documentation](https://docs.spring.io/spring-ai/reference/)
* [Issues](https://github.com/spring-projects/spring-ai/issues)
<!-- * [Discussions](https://github.com/spring-projects/spring-ai/discussions) - For questions, suggestions, or feedback! -->
* [Awesome Spring AI](https://github.com/spring-ai-community/awesome-spring-ai) - Curated resources, tools, tutorials, and projects for building generative AI applications with Spring AI
* [Spring AI Examples](https://github.com/spring-projects/spring-ai-examples) - Example projects demonstrating specific features.
* [Spring AI Community](https://github.com/spring-ai-community) - Community-driven organization for Spring-based AI integrations.

## Breaking Changes

* See [upgrade notes](https://docs.spring.io/spring-ai/reference/upgrade-notes.html) for upgrading to 1.0.0.M1 or higher.

## Cloning the Repository

This repository contains [large model files](https://github.com/spring-projects/spring-ai/tree/main/models/spring-ai-transformers/src/main/resources/onnx/all-MiniLM-L6-v2). Clone options:

- Ignore large files (doesn't affect functionality): `GIT_LFS_SKIP_SMUDGE=1 git clone git@github.com:spring-projects/spring-ai.git`.
- Install [Git Large File Storage](https://git-lfs.com/) before cloning.

## Building

The project targets Java 17+ compatibility but requires JDK 21 for building (enforced by Maven enforcer plugin).

To build with unit tests:

%%CODEBLOCK_0%%

To build including integration tests:

%%CODEBLOCK_1%%

Note: Set API key environment variables for OpenAI or other model providers before running. Integration tests are skipped if provider API keys are missing.

To run specific integration tests with up to two retry attempts (useful for unreliable services):

%%CODEBLOCK_2%%

### Integration Tests

Given the volume of integration tests, running them all simultaneously is often impractical.

A quick test of key pathways (OpenAI models, autoconfiguration, PGVector, Chroma) can be executed using the `-Pci-fast-integration-tests` profile, which is used in the main CI build.

Full integration tests run twice daily in the [Spring AI Integration Test Repository](https://github.com/spring-projects/spring-ai-integration-tests).

For module-specific integration tests:
1. Compile and install the project:

%%CODEBLOCK_3%%
2. Run integration tests for a specific module using `-pl`:

%%CODEBLOCK_4%%

### Documentation

To build documentation:

%%CODEBLOCK_5%%

Built documentation is located in `spring-ai-docs/target/antora/site/index.html`.

### Source Code Formatting

Code is formatted using the [java-format plugin](https://github.com/spring-io/spring-javaformat) during builds. CI enforces correct formatting.

### Updating License Headers

To update license header years using [license-maven-plugin](https://oss.carbou.me/license-maven-plugin/#goals):

%%CODEBLOCK_6%%

### Javadocs

To check Javadocs using [javadoc:javadoc](https://maven.apache.org/plugins/maven-javadoc-plugin/):

%%CODEBLOCK_7%%

#### Source Code Style

Spring AI follows core Spring Framework checkstyle guidelines with some exceptions. See:
- [Code Style](https://github.com/spring-projects/spring-framework/wiki/Code-Style)
- [IntelliJ IDEA Editor Settings](https://github.com/spring-projects/spring-framework/wiki/IntelliJ-IDEA-Editor-Settings)

## Contributing

Contributions are welcome! Please review the [contribution guidelines](CONTRIBUTING.adoc) first.