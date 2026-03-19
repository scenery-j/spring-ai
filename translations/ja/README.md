# Spring AI [![build status](https://github.com/spring-projects/spring-ai/actions/workflows/continuous-integration.yml/badge.svg)](https://github.com/spring-projects/spring-ai/actions/workflows/continuous-integration.yml) [![build status](https://github.com/spring-projects/spring-ai-integration-tests/actions/workflows/spring-ai-integration-tests.yml/badge.svg)](https://github.com/spring-projects/spring-ai-integration-tests/actions/workflows/spring-ai-integration-tests.yml) [![Maven Central](https://img.shields.io/maven-central/v/org.springframework.ai/spring-ai-model?label=Maven%20Central&versionPrefix=2.0)](https://central.sonatype.com/artifact/org.springframework.ai/spring-ai-model)

### Spring Boot バージョン互換性

> **Spring AI 2.x.x** ([main](https://github.com/spring-projects/spring-ai/tree/main) ブランチ) - Spring Boot `4.x`
>
> **Spring AI 1.1.x** ([1.1.x](https://github.com/spring-projects/spring-ai/tree/1.1.x) ブランチ) - Spring Boot `3.5.x`

Spring AIプロジェクトは、AIアプリケーションを開発するためのSpringフレンドリーなAPIと抽象化を提供します。

その目標は、AIドメインにSpringエコシステムの設計原則（移植性やモジュール設計など）を適用し、AIドメインにPOJOをアプリケーションのビルディングブロックとして使用することを促進することです。

![spring-ai-integration-diagram-3](https://docs.spring.io/spring-ai/reference/_images/spring-ai-integration-diagram-3.svg)

> その核心において、Spring AIはAI統合の基本的な課題に対処します：エンタープライズの__データ__と__API__を__AIモデル__に接続すること。

このプロジェクトは、[LangChain](https://docs.langchain.com/docs/)や[LlamaIndex](https://gpt-index.readthedocs.io/en/latest/getting_started/concepts.html)などの注目すべきPythonプロジェクトからインスピレーションを得ていますが、Spring AIはそれらのプロジェクトの直接の移植ではありません。このプロジェクトは、次世代のGenerative AIアプリケーションがPython開発者だけでなく、多くのプログラミング言語に広く普及するという信念のもとに設立されました。

追加の動機については、ブログ記事[Why Spring AI](https://spring.io/blog/2024/11/19/why-spring-ai)をご覧ください。

以下は、高レベルの機能概要です。
詳細については、[リファレンスドキュメント](https://docs.spring.io/spring-ai/reference/)をご覧ください。

* Anthropic、OpenAI、Microsoft、Amazon、Google、Ollamaなどの主要な[AIモデルプロバイダー](https://docs.spring.io/spring-ai/reference/api/index.html)のサポート。サポートされるモデルタイプは以下の通りです：
  - [チャット補完](https://docs.spring.io/spring-ai/reference/api/chatmodel.html)
  - [埋め込み](https://docs.spring.io/spring-ai/reference/api/embeddings.html)
  - [テキストから画像](https://docs.spring.io/spring-ai/reference/api/imageclient.html)
  - [音声文字起こし](https://docs.spring.io/spring-ai/reference/api/audio/transcriptions.html)
  - [テキストから音声](https://docs.spring.io/spring-ai/reference/api/audio/speech.html)
  - [モデレーション](https://docs.spring.io/spring-ai/reference/api/index.html#api/moderation)
  - **最新モデル**: GPT-5やその他の先進的なAIアプリケーションのための最先端モデル。
* AIプロバイダー間での同期およびストリーミングオプションの移植可能なAPIサポート。[モデル固有の機能](https://docs.spring.io/spring-ai/reference/api/chatmodel.html#_chat_options)へのアクセスも可能です。
* [構造化出力](https://docs.spring.io/spring-ai/reference/api/structured-output-converter.html) - AIモデルの出力をPOJOにマッピングします。
* *Apache Cassandra、Azure Vector Search、Chroma、Elasticsearch、Milvus、MongoDB Atlas、MariaDB、Neo4j、Oracle、PostgreSQL/PGVector、Pinecone、Qdrant、Redis、Weaviate*などの主要な[ベクトルデータベースプロバイダー](https://docs.spring.io/spring-ai/reference/api/vectordbs.html)のサポート。
* ベクトルストアプロバイダー間での移植可能なAPI、新しいSQLライクな[メタデータフィルターAPI](https://docs.spring.io/spring-ai/reference/api/vectordbs.html#metadata-filters)を含みます。
* [ツール/関数呼び出し](https://docs.spring.io/spring-ai/reference/api/tools.html) - モデルがクライアントサイドのツールや関数の実行を要求し、必要なリアルタイム情報にアクセスできるようにします。
* [可観測性](https://docs.spring.io/spring-ai/reference/observability/index.html) - AI関連の操作に関する洞察を提供します。
* データエンジニアリングのためのドキュメント注入[ETLフレームワーク](https://docs.spring.io/spring-ai/reference/api/etl-pipeline.html)。
* [AIモデル評価](https://docs.spring.io/spring-ai/reference/api/testing.html) - 生成されたコンテンツを評価し、幻覚的な応答から保護するためのユーティリティ。
* [ChatClient API](https://docs.spring.io/spring-ai/reference/api/chatclient.html) - AIチャットモデルと通信するためのフルーエントAPIで、WebClientやRestClient APIと類似しています。
* [アドバイザーAPI](https://docs.spring.io/spring-ai/reference/api/advisors.html) - 繰り返し発生するGenerative AIパターンをカプセル化し、Language Models (LLMs)に送受信されるデータを変換し、さまざまなモデルとユースケース間での移植性を提供します。
* [チャット会話メモリ](https://docs.spring.io/spring-ai/reference/api/chatclient.html#_chat_memory)と[Retrieval Augmented Generation (RAG)](https://docs.spring.io/spring-ai/reference/api/chatclient.html#_retrieval_augmented_generation)のサポート。
* すべてのAIモデルとベクトルストアのSpring Boot自動設定とスターター - [start.spring.io](https://start.spring.io/)を使用して、選択したモデルまたはベクトルストアを選択します。

## はじめに

依存関係を追加するための手順については、[はじめにガイド](https://docs.spring.io/spring-ai/reference/getting-started.html)をご参照ください。

## プロジェクトリソース

* [ドキュメント](https://docs.spring.io/spring-ai/reference/)
* [Issues](https://github.com/spring-projects/spring-ai/issues)
<!-- * [ディスカッション](https://github.com/spring-projects/spring-ai/discussions) - 質問、提案、フィードバックがある場合はこちらへ！ -->
* [Awesome Spring AI](https://github.com/spring-ai-community/awesome-spring-ai) - Spring AIを使用してGenerative AIアプリケーションを構築するためのリソース、ツール、チュートリアル、プロジェクトのキュレーションされたリスト
* [Spring AI サンプル](https://github.com/spring-projects/spring-ai-examples) 特定の機能を詳細に説明するサンプルプロジェクトが含まれています。
* [Spring AI コミュニティ](https://github.com/spring-ai-community) - AIモデル、エージェント、ベクトルデータベースなどとのSpringベースの統合を構築するためのコミュニティ主導の組織。

## 破壊的変更

* 1.0.0.M1以降へのアップグレード方法については、[アップグレードノート](https://docs.spring.io/spring-ai/reference/upgrade-notes.html)をご参照ください。

## リポジトリのクローン

このリポジトリには[大規模なモデルファイル](https://github.com/spring-projects/spring-ai/tree/main/models/spring-ai-transformers/src/main/resources/onnx/all-MiniLM-L6-v2)が含まれています。
クローンするには、以下のいずれかの方法を使用してください：

- 大規模なファイルを無視する（spring-aiの動作には影響しません）：`GIT_LFS_SKIP_SMUDGE=1 git clone git@github.com:spring-projects/spring-ai.git`。
- または、リポジトリをクローンする前に[Git Large File Storage](https://git-lfs.com/)をインストールしてください。

## ビルド

このプロジェクトはJava 17+互換のターゲットとビルドアーティファクトを対象としていますが、ビルドにはJDK 21が必要です。これはmaven enforcerプラグインによって強制されます。

ユニットテストを実行してビルドするには

%%CODEBLOCK_0%%

統合テストを含めてビルドするには

%%CODEBLOCK_1%%

特定のモデルプロバイダーのAPIキー環境変数を設定する必要があります。特定のモデルプロバイダーのAPIキーが設定されていない場合、統合テストはスキップされます。

特定の統合テストを実行し、最大2回の試行を許可します。ホストされたサービスが信頼できない場合やタイムアウトする場合に便利です。
%%CODEBLOCK_2%%

### 統合テスト

多くの統合テストがあるため、すべてを一度に実行することは現実的ではありません。

最も重要なパスウェイを素早く通過するために、以下の統合テストを実行します：

* OpenAIモデル
* OpenAI自動設定
* PGVector
* Chroma

これはプロファイル`-Pci-fast-integration-tests`を使用して行うことができ、このプロジェクトのメインCIビルドで使用されています。

完全な統合テストは、[Spring AI Integration Test Repository](https://github.com/spring-projects/spring-ai-integration-tests)で1日に2回実行されます。

コードの一部で統合テストを実行する1つの方法は、まずプロジェクトを素早くコンパイルしてインストールすることです

%%CODEBLOCK_3%%
次に、`-pl`オプションを使用して特定のモジュールの統合テストを実行します

%%CODEBLOCK_4%%

### ドキュメント

ドキュメントをビルドするには
%%CODEBLOCK_5%%

ドキュメントはディレクトリ`spring-ai-docs/target/antora/site/index.html`にあります

### ソースコードのフォーマット

コードはビルドの一部として[java-formatプラグイン](https://github.com/spring-io/spring-javaformat)を使用してフォーマットされます。正しいフォーマットはCIによって強制されます。

### ライセンスヘッダーの更新

[license-maven-plugin](https://oss.carbou.me/license-maven-plugin/#goals)を使用してライセンスヘッダーの年を更新するには
%%CODEBLOCK_6%%
### Javadocs

[javadoc:javadoc](https://maven.apache.org/plugins/maven-javadoc-plugin/)を使用してjavadocsをチェックするには
%%CODEBLOCK_7%%

#### ソースコードスタイル

Spring AIのソースコードチェックスタイルは、コアSpring Frameworkプロジェクトで使用されているチェックスタイルガイドラインに従おうとしていますが、いくつかの例外があります。
[コードスタイル](https://github.com/spring-projects/spring-framework/wiki/Code-Style)と
[IntelliJ IDEAエディター設定](https://github.com/spring-projects/spring-framework/wiki/IntelliJ-IDEA-Editor-Settings)
のWikiページでは、私たちが使用するソースファイルのコーディング標準と、カスタマイズするいくつかのIDEAエディター設定を定義しています。

## 貢献

あなたの貢献はいつでも歓迎です！まずは[貢献ガイドライン](CONTRIBUTING.adoc)をお読みください。