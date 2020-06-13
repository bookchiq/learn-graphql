---
title: "認証"
metaTitle: "Hasura での認証 | Hasura GraphQL チュートリアル"
metaDescription: "このチュートリアルでは、Auth0のような認証プロバイダーと統合することにより、Hasura GraphQL エンジンで認証を行う方法について説明します"
---

このチュートリアルでは、認証プロバイダーを統合する方法について説明します。

リアルタイムの ToDo アプリは、ログインインターフェースで保護する必要があります。この例では、アイデンティティ/認証プロバイダーとして [Auth0](https://auth0.com) を使います。

**注意**: Auth0 には、最大7000人のアクティブユーザーまでを扱える無料プランがあります。

基本的な考え方は、ユーザーが Auth0 で認証すると、クライアントアプリがトークンを受け取り、 そのトークンを GraphQL リクエストの `Authorization` ヘッダーに含んで送信されます。Hasura GraphQL エンジンは、トークンが有効かどうかを確認し、ユーザーが適切なクエリを実行できるようにします。

それでは始めましょう！