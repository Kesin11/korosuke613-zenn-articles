---
title: ＜ここにタイトルを入力＞｜Productivity Weekly(2024-08-28,08-21)
emoji: 🌀
type: idea
topics:
  - ProductivityWeekly
  - 生産性向上
published: false
publication_name: cybozu_ept
user_defined: 
  publish_link: https://zenn.dev/cybozu_ept/articles/productivity-weekly-20240828
  note: |
    _本項の執筆者: [@korosuke613](https://zenn.dev/korosuke613)_
    _本項の執筆者: [@defaultcf](https://zenn.dev/defaultcf)_
    _本項の執筆者: [@Kesin11](https://zenn.dev/kesin11)_
    _本項の執筆者: [@r4mimu](https://zenn.dev/r4mimu)_
    _本項の執筆者: [@uta8a](https://zenn.dev/uta8a)_
---

こんにちは。サイボウズ株式会社 [生産性向上チーム](https://note.com/cybozu_dev/n/n1c1b44bf72f6)の平木場です。

僕たち生産性向上チームは毎週水曜日に Productivity Weekly という「1 週間の間に発見された開発者の生産性向上に関するネタを共有する会」を社内で開催しています。
本記事はその時のネタをまとめたものです。


2023-01-25 号から、基本的に隔週で連載することとしました。たまに単独でも投稿するかもしれません。
今週は 2024-08-21, 2024-08-28 合併号です。

今回が第 164 回目です。過去の記事は[こちら](https://zenn.dev/topics/productivityweekly?order=latest)。

:::message
2023-05-10 号から、生産性向上チームの他メンバーにいくつかのトピックを紹介していただくことにしています。

対象のトピックでは、文章の最後に `本項の執筆者: <執筆者名>` を追加しています。

今週の共同著者は次の方です。
- [@korosuke613](https://zenn.dev/korosuke613)
<!-- - [@defaultcf](https://zenn.dev/defaultcf) -->
<!-- - [@Kesin11](https://zenn.dev/kesin11) -->
<!-- - [@r4mimu](https://zenn.dev/r4mimu) -->
<!-- - [@uta8a](https://zenn.dev/uta8a) -->

:::

# news 📺

## Notice of upcoming deprecations and breaking changes in GitHub Actions runners - GitHub Changelog
https://github.blog/changelog/2024-08-19-notice-of-upcoming-deprecations-and-breaking-changes-in-github-actions-runners/

GitHub Actions における、今後半年以内に非推奨となる機能や破壊的変更のある機能のまとめお知らせです。

次の内容が書かれています。

- actions/upload-artifact v3, v4 においてデフォルトで隠しファイルが除外されるように変更 (9 月〜)
- Ubuntu Arm ランナーの Ubuntu 22/20 ベースイメージが利用不可能に (9 月〜)
  - 代わりに [Arm が提供する Ubuntu 24/22 イメージ](https://github.com/actions/partner-runner-images/tree/5e496b5c1eddaf72d0ae87d98d8de6ac5554357e)の使用が推奨されます
- actions/runner において .Net6 から .Net8 へ移行 (10 月〜)
  - セルフホストランナーを立てる際は、今後はランナー設定前に .Net8 が必要になります
- macOS 12 ランナーが非推奨に（12 月までに完全に引退）
- macOS のいくつかのラベルが利用不可能に（12 月〜）
  - `macos-11.0`, `macos-12-xl`, `macos-13-xl`, `macos-13-xl-arm64`, `macos-latest-xl`, `macos-latest-xl-arm64`

いろいろありますが、特に気をつけたいのが actions/upload-artifact の変更ですね。セキュリティアップデートという意味合いからか、メジャーアップデートではないため、`actions/upload-artifact@v4` のような指定をしている場合は変更が自動で適用されることになります（記事執筆時点ですでに期日を超えてしまっていますが）。

さっそく検証してくれた方が記事を出してくれているので、どういう挙動になったかはこちらがわかりやすいです。

- [actions/upload-artifact はデフォルトでは隠しファイルをアップロードしなくなった](https://zenn.dev/kou_pg_0131/articles/gh-actions-upload-artifact-hidden-files)

この変更は以前話題になった、リポジトリ全体をアップロード対象に指定してしまうと `.git` にある `GITHUB_TOKEN` もアップロードされてしまい、セキュリティ的に問題があることを受けての変更だと思われます。

> actions/checkoutはデフォルトでローカルの.gitにGITHUB_TOKENを保存するので、そのままartifactとしてリポジトリ全体をアップロードしてはいけない。
> > ArtiPACKED: Hacking Giants Through a Race Condition in GitHub Actions Artifacts
https://x.com/minamijoyo/status/1824997760107716906

そのためメジャーアップデートでの変更とはならなかったようですが、この変更に関する Issue ([Upcoming breaking change: Hidden Files will be excluded by default · Issue #602 · actions/upload-artifact](https://github.com/actions/upload-artifact/issues/602)) では多くの down vote が付いており、この対応に満足していないユーザーは多そうでした。[指摘](https://unit42.paloaltonetworks.com/github-repo-artifacts-leak-tokens/)された一週間後にアナウンスを出し、その二週間後には変更されているため、変更されることを知らない人も多かったことでしょう。難しいですね。

そもそもバージョンを厳密に固定してこまめにアップデートする運用をしておけばいきなり仕様が変わって困るということも回避できたと思うので、GitHub 公式アクションだとしてもバージョン固定するのがいいかもしれませんね。

_本項の執筆者: [@korosuke613](https://zenn.dev/korosuke613)_

## Copilot Enterprise now helps you fix failed Actions jobs, plus other August updates (public beta) - GitHub Changelog
https://github.blog/changelog/2024-08-15-copilot-enterprise-now-helps-you-fix-failed-actions-jobs-plus-other-august-updates-public-beta/

## AWS CodeBuild now supports using GitHub Apps to access source repositories - AWS
https://aws.amazon.com/jp/about-aws/whats-new/2024/08/aws-codebuild-github-apps-access-source-repositories/

## AWS CodeBuild が macOS でのビルドをサポートしました | DevelopersIO
https://dev.classmethod.jp/articles/codebuild-mac-builds/

## Amazon S3 now supports conditional writes - AWS
https://aws.amazon.com/jp/about-aws/whats-new/2024/08/amazon-s3-conditional-writes/

## Amazon ECS provides the ability to restart containers without requiring a task relaunch
https://aws.amazon.com/jp/about-aws/whats-new/2024/08/amazon-ecs-restart-containers-task-relaunch/

## Node.js Support | aqua
https://aquaproj.github.io/docs/reference/nodejs-support/

## Deno 1.46: The Last 1.x Release
https://deno.com/blog/v1.46

## Google Cloud Functions is now Cloud Run functions | Google Cloud Blog
https://cloud.google.com/blog/products/serverless/google-cloud-functions-is-now-cloud-run-functions

## Host your LLMs on Cloud Run | Google Cloud Blog
https://cloud.google.com/blog/products/application-development/run-your-ai-inference-applications-on-cloud-run-with-nvidia-gpus

## Terraform provider for Google Cloud 6.0 is now GA
https://www.hashicorp.com/blog/terraform-provider-for-google-cloud-6-0-is-now-ga

## 即座にリアルタイムを実現: 最新のインサイトを提供する BigQuery の継続的クエリを導入 | Google Cloud 公式ブログ
https://cloud.google.com/blog/ja/products/data-analytics/bigquery-continuous-queries-makes-data-analysis-real-time/

## Custom models for GitHub Copilot are now in Limited Public Beta - GitHub Changelog
https://github.blog/changelog/2024-08-27-custom-models-for-github-copilot-are-now-in-limited-public-beta/

## AWS Lambda introduces recursive loop detection APIs | AWS Compute Blog 
https://aws.amazon.com/jp/blogs/compute/aws-lambda-introduces-recursive-loop-detection-apis/

## Amazon Bedrock now supports cross-region inference
https://aws.amazon.com/jp/about-aws/whats-new/2024/08/amazon-bedrock-cross-region-inference/

# know-how 🎓

## Terraform AWS Provider で AWS Chatbot を構築する - kakakakakku blog
https://kakakakakku.hatenablog.com/entry/2024/08/04/132435


## GitHubで扱うPersonal access tokenの利用方法をセキュアにする - 10X Product Blog
https://product.10x.co.jp/entry/2024/08/19/164039

## GitHub Actions ステップアップ Tips 〜高速化・セキュリティ・設計〜 #GitHubActions_findy | ドクセル
https://www.docswell.com/s/uta8a/KYDW9P-2024-08-22-github-actions-tips

## Go製アプリケーション/ライブラリにおけるメンテナンス性を重視したGoのバージョン管理戦略 - Diary of a Perpetual Student
https://blog.arthur1.dev/entry/2024/08/27/120000

# tool 🔨

## Navigate and refactor your code with ease
https://haystackeditor.com/

# read more 🍘
Productivity Weekly で出たネタを全て紹介したいけど紹介する体力が持たなかったネタを一言程度で書くコーナーです。

- **news 📺**
- **know-how 🎓**
- **tool 🔨**

# あとがき


サイボウズの生産性向上チームでは社内エンジニアの開発生産性を上げるための活動を行なっています。そんな生産性向上チームが気になる方は下のリンクをクリック！
https://www.docswell.com/s/cybozu-tech/5R2X3N-engineering-productivity-team-recruitment-information

<!-- :::message すみません、今週もおまけはお休みです...:::-->

<!-- ## omake 🃏: -->
<!-- 今週のおまけです。-->
