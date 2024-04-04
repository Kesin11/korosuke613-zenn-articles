---
title: ＜ここにタイトルを入力＞｜Productivity Weekly(2024-03-27)
emoji: 🍄
type: idea
topics:
  - ProductivityWeekly
  - 生産性向上
published: false
publication_name: cybozu_ept
user_defined: 
  publish_link: https://zenn.dev/cybozu_ept/articles/productivity-weekly-20240327
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
今週は 2024-03-27 単独号です。

今回が第 147 回目です。過去の記事は[こちら](https://zenn.dev/topics/productivityweekly?order=latest)。

:::message
2023-05-10 号から、生産性向上チームの他メンバーにいくつかのトピックを紹介していただくことにしています。

対象のトピックでは、文章の最後に `本項の執筆者: <執筆者名>` を追加しています。

今週の共同著者は次の方です。
- [@korosuke613](https://zenn.dev/korosuke613)
- [@defaultcf](https://zenn.dev/defaultcf)
<!-- - [@Kesin11](https://zenn.dev/kesin11) -->
<!-- - [@r4mimu](https://zenn.dev/r4mimu) -->
<!-- - [@uta8a](https://zenn.dev/uta8a) -->

:::

# news 📺

## GitHub Copilot General Availability in the CLI - The GitHub Blog
https://github.blog/changelog/2024-03-21-github-copilot-general-availability-in-the-cli/

## AWS announces a 7-day window to return Savings Plans
https://aws.amazon.com/jp/about-aws/whats-new/2024/03/aws-7-day-window-return-savings-plans/

AWS の Saving Plans について、購入 7 日以内であれば返品できるようになりました。

丁度プライベートのプロジェクトで長期間動かし続けるコンピューティングワークフローがあるので、Saving Plan を買ってみて返品の流れだけ見てみようと思います。

![Saving Plan 購入の際のカート](/images/productivity-weekly-20240327/saving_plan_cart_20240327.png)

詳細画面で購入した Saving Plan を確認できます。

![購入した Saving Plan の詳細画面](/images/productivity-weekly-20240327/saving_plan_describe_20240327.png)

この画面の中に「Return Saving Plan」があり、これを押すと返品を進められます。

![Saving Plan の返品画面](/images/productivity-weekly-20240327/return_saving_plan_20240327.png)

以前は Saving Plans の購入は取り消すことができず、非常に慎重に購入をする必要がありました。
しかしこれからはちょっとだけ肩の力を抜いて購入できそうです。

_本項の執筆者: [@defaultcf](https://zenn.dev/defaultcf)_

## Enablement trends for security products (public beta) - The GitHub Blog
https://github.blog/changelog/2024-03-19-enablement-trends-for-security-products-public-beta/

## Security overview dashboard: Alert age trends, custom repository and severity filters, and date pickers - The GitHub Blog
https://github.blog/changelog/2024-03-20-security-overview-dashboard-alert-age-trends-custom-repository-and-severity-filters-and-date-pickers/

## Fig is sunsetting, migrate to Amazon CodeWhisperer | Fig
https://fig.io/blog/post/fig-is-sunsetting

## EC2 Mac Dedicated Hosts now provide visibility into supported macOS versions
https://aws.amazon.com/jp/about-aws/whats-new/2024/03/ec2-mac-dedicated-hosts-visibility-supported-macos-versions/

macOS 専有ホストは長期間運用しているとファームウェアが古くなり、新しい macOS のバージョンを利用できないことがあります。
今回、そのホストがサポートしている最新の macOS のバージョンが分かるようになりました。嬉しい変更ですね。

macOS 専有ホストの詳細画面の「Latest supported macOS versions」で確認できます。

![macOS 専有ホストの詳細画面](/images/productivity-weekly-20240327/dedicated_mac_host_20240327.png)

なおサポートしている macOS のバージョンが古い場合は、インスタンスを停止または終了することで自動的にファームウェアが更新されるそうです。

_本項の執筆者: [@defaultcf](https://zenn.dev/defaultcf)_

# know-how 🎓

## PATを使わずにGitHub Appを使ってGitHub ActionsでPrivate Repoを参照する話 - Google スライド
https://docs.google.com/presentation/d/10-HgSST2xR5H3xCwGLKCk_PBwq4zHcxD2393ifwOsiM/edit#slide=id.p

## リリース戦略を支えるCI/CDパイプライン | ドクセル
https://www.docswell.com/s/katzumi/58G8J9-empowering-release-strategies-cicd-pipelines

## CI の DX とセキュリティ - Google スライド
https://docs.google.com/presentation/d/1rN4kTtvErrheZ3SXNr49XUHbiGIoorpfiLGXjLt5vsc

## 業務で使えるかもしれない…！？GitHub Actions の Tips 集 / CI/CD Test Night #7 - Speaker Deck
https://speakerdeck.com/ponkio_o/cd-test-night-number-7

## Reduce, reuse, recycle: McDonald’s reusable workflows | by Global Technology | McDonald’s Technical Blog | Feb, 2024 | Medium
https://medium.com/mcdonalds-technical-blog/reduce-recycle-reuse-03a57554ee6a

## Actions Runner Controller Deep Dive - Speaker Deck
https://speakerdeck.com/jnytnai0613/actions-runner-controller-deep-dive

## システムや開発プロセスは変更せずに開発チームの生産性を上げる5つの方法
https://note.com/hamchance/n/n3e31fc8e4679?sub_rt=share_pw

# tool 🔨

## GitHub ActionsでファイルをS3にキャッシュするアクションを作りました - プログラムモグモグ
https://itchyny.hatenablog.com/entry/2024/03/22/090000

## JSON をプレビューしながら jq のフィルタを書くことができる「jnv」を試してみる
https://zenn.dev/kou_pg_0131/articles/jnv-introduction

jq はもはや JSON をクエリできるデファクトスタンダードで、GitHub Actions のランナーイメージにデフォルトでインストールされていることから世界的に多くの方が使用していると言えると思っています。
https://github.com/actions/runner-images/blob/df41637c07f1752efadfa844f2951744affb3e32/images/ubuntu/Ubuntu2204-Readme.md?plain=1#L85

ただ jq のフィルタの構文は少々独特で、試しに書いて出力してを繰り返し、理想のフィルタを作ることがほとんどです。
このサイクルを素早くできるツールが、この jnv だと思います。試しに使ってみました。

```bash
curl https://dummyjson.com/users | jnv
```

するとインタラクティブな UI が開き、フィルタを変更するたびにその結果を確認できます。
タブキーでの補完機能もあるようですが、`.users[].f` まで打ってからタブキーを押しても `.users[].firstName` を補完まではしてくれませんでした。配列内の子までは対応していないようです。

フィルタを書く際に非常に重宝するので、今後も使っていきたいと思います。

_本項の執筆者: [@defaultcf](https://zenn.dev/defaultcf)_

## suzuki-shunsuke/pinact: Pin GitHub Actions versions
https://github.com/suzuki-shunsuke/pinact

# read more 🍘
Productivity Weekly で出たネタを全て紹介したいけど紹介する体力が持たなかったネタを一言程度で書くコーナーです。

- **news 📺**
- **know-how 🎓**
- **tool 🔨**

# あとがき


サイボウズの生産性向上チームでは社内エンジニアの開発生産性を上げるための活動を行なっています。そんな生産性向上チームが気になる方は下のリンクをクリック！
https://speakerdeck.com/cybozuinsideout/engineering-productivity-team-recruitment-information

<!-- :::message すみません、今週もおまけはお休みです...:::-->

<!-- ## omake 🃏: -->
<!-- 今週のおまけです。-->
