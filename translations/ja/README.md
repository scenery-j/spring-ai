# Spring AI [![build status](https://github.com/spring-projects/spring-ai/actions/workflows/continuous-integration.yml/badge.svg)](https://github.com/spring-projects/spring-ai/actions/workflows/continuous-integration.yml) [![build status](https://github.com/spring-projects/spring-ai-integration-tests/actions/workflows/spring-ai-integration-tests.yml/badge.svg)](https://github.com/spring-projects/spring-ai-integration-tests/actions/workflows/spring-ai-integration-tests.yml) [![Maven Central](https://img.shields.io/maven-central/v/org.springframework.ai/spring-ai-model?label=Maven%20Central&versionPrefix=2.0)](https://central.sonatype.com/artifact/org.springframework.ai/spring-ai-model)

### Spring Boot バージョン互換性

> **Spring AI 2.x.x** ([main](https://github.com/spring-projects/spring-ai/tree/main) ブランチ) - Spring Boot `4.x`
>
> **Spring AI 1.1.x** ([1.1.x](https://github.com/spring-projects/spring-ai/tree/1.1.x) ブランチ) - Spring Boot `3.5.x`

Spring AI プロジェクトは、AI アプリケーションを開発するための Spring フレンドリーな API と抽象化を提供します。

その目標は、AI ドメインに Spring エコシステムの設計原則（ポータビリティやモジュラー設計など）を適用し、アプリケーションの構成ブロックとして POJOs を使用することを AI ドメインに推進することです。

![spring-ai-integration-diagram-3](https://docs.spring.io/spring-ai/reference/_images/spring-ai-integration-diagram-3.svg)

> その核心において、Spring AI は AI 統合の根本的な課題に対処します：エンタープライズの __Data__ と __APIs__ を __AI Models__ と接続すること。

このプロジェクトは、著名な Python プロジェクト（[LangChain](https://docs.langchain.com/docs/) や [LlamaIndex](https://gpt-index.readthedocs.io/en/latest/getting_started/concepts.html) など）からインスピレーションを得ていますが、Spring AI はそれらのプロジェクトの直接の移植ではありません。このプロジェクトは、次のウェーブの生成 AI アプリケーションが Python 開発者のためだけではなく、多くのプログラミング言語に遍在するだろうという信念のもとに設立されました。

追加の動機については、ブログ記事 [Why Spring AI](https://spring.io/blog/2024/11/19/why-spring-ai) を参照してください。

これは高レベルの機能概要です。詳細は [Reference Documentation](https://docs.spring.io/spring-ai/reference/) で確認できます。

* 主要な [AI Model providers](https://docs.spring.io/spring-ai/reference/api/index.html)（Anthropic、OpenAI、Microsoft、Amazon、Google、Ollama など）のサポート。サポートされているモデルタイプには以下が含まれます：
  - [Chat Completion](https://docs.spring.io/spring-ai/reference/api/chatmodel.html)
  - [Embedding](https://docs.spring.io/spring-ai/reference/api/embeddings.html)
  - [Text to Image](https://docs.spring.io/spring-ai/reference/api/imageclient.html)
  - [Audio Transcription](https://docs.spring.io/spring-ai/reference/api/audio/transcriptions.html)
  - [Text to Speech](https://docs.spring.io/spring-ai/reference/api/audio/speech.html)
  - [Moderation](https://docs.spring.io/spring-ai/reference/api/index.html#api/moderation)
  - **最新のモデル**：GPT-5 および高度な AI アプリケーション向けのその他の最先端モデル。
* AI プロバイダー間でのポータブル API サポート（同期およびストリーミングオプションの両方）。[モデル固有の機能](https://docs.spring.io/spring-ai/reference/api/chatmodel.html#_chat_options)へのアクセスも利用可能です。
* [Structured Outputs](https://docs.spring.io/spring-ai/reference/api/structured-output-converter.html) - AI Model の出力を POJOs にマッピング。
* 主要な [Vector Database providers](https://docs.spring.io/spring-ai/reference/api/vectordbs.html)（*Apache Cassandra、Azure Vector Search、Chroma、Elasticsearch、Milvus、MongoDB Atlas、MariaDB、Neo4j、Oracle、PostgreSQL/PGVector、Pinecone、Qdrant、Redis、Weaviate* など）のサポート。
* Vector Store プロバイダー間でのポータブル API には、新しい SQL ライクな [metadata filter API](https://docs.spring.io/spring-ai/reference/api/vectordbs.html#metadata-filters) が含まれます。
* [Tools/Function Calling](https://docs.spring.io/spring-ai/reference/api/tools.html) - モデルがクライアント側のツールと関数の実行を要求できるようにし、必要なリアルタイム情報にアクセスします。
* [Observability](https://docs.spring.io/spring-ai/reference/observability/index.html) - AI 関連の操作に関する洞察を提供します。
* データエンジニアリングのためのドキュメントインジェクション [ETL framework](https://docs.spring.io/spring-ai/reference/api/etl-pipeline.html)。
* [AI Model Evaluation](https://docs.spring.io/spring-ai/reference/api/testing.html) - 生成されたコンテンツを評価し、幻覚応答から保護するためのユーティリティ。
* [ChatClient API](https://docs.spring.io/spring-ai/reference/api/chatclient.html) - AI Chat