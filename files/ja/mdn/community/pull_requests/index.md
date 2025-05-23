---
title: プルリクエストの提出とレビューのガイドライン
slug: MDN/Community/Pull_requests
l10n:
  sourceCommit: 6610050dace0bfa2bba703576225aef6f84f36fe
---

{{MDNSidebar}}

この記事では、協力者が MDN Web Docs に変更を加える方法と、変更がどのようにレビューされ、サイトに掲載されるかを記述しています。
MDN Web Docs へのコンテンツの変更には以下のものが含まれます。

- **日々のコンテンツ改善作業** - API、CSS プロパティ、プラットフォームの更新、コンテンツの追加などのドキュメント。
  これは通常、Mozilla、Google、Open Web Docs、Samsung などで働く MDN スタッフによって行われますが、コミュニティのボランティアによっても行われることがあります。
- **小さな修正** と小さな更新。 誤字脱字、文法的な問題、技術的な不正確さを修正するために行われる小さな更新です。
  通常は MDN Web Docs の読者によって見つけられたものです。
- **コンテンツのバグ修正**。通常はボランティアによって行われ、[`mdn/content` リポジトリーにある課題](https://github.com/mdn/content/issues)を閉じるためのものです。

どのような形で行うコンテンツの変更であっても、GitHub でプルリクエストとして送信されます。
コンテンツの変更は、MDN Web Docs で公開されるまでに以下の段階を経ます。

1. **変更の送信:** プルリクエストの作成者として、プルリクエストを開いて変更を送信します。
   [始める前に](#始める前に)、[プルリクエストを開く](#プルリクエストを開く)、[プルリクエストを開いた後](#プルリクエストを開いた後)の節を参照して、プロセスについてもっと学びましょう。
2. **変更点のレビュー:** 変更点は MDN メンバーとボランティアがレビューします。
   詳細は[プルリクエストのレビュープロセス](#プルリクエストのレビュープロセス)の節を参照してください。
3. **発行された変更の閲覧:** `mdn/content` で更新されたコンテンツは、24 時間に一度のサイト再構築により、マージされてから 1 日以内に公開されます。

## 変更の提出

### 価値と参加

私たちは MDN Web Docs が、誰もが誇りに思えるような、歓迎され、友好的なコミュニティであることを望んでいます。
すべての参加者は、私たちの[行動規範](https://github.com/mdn/content/blob/main/CODE_OF_CONDUCT.md)に従う必要があり、それは [Mozilla コミュニティ参加ガイドライン](https://www.mozilla.org/ja/about/governance/policies/participation/)を遵守することを意味します。
プルリクエストを開くため、レビューコメントを書くため、プルリクエスト作成者や他のコミュニティメンバーと対話するときは、礼儀正しく、建設的であるべきです。
あなたや他の誰かが、違法である可能性のある行動を経験したり、安全でない、歓迎されていない、または不快に感じたりした場合は、[報告する](https://www.mozilla.org/ja/about/governance/policies/participation/reporting/) ことをお勧めします。

### 始める前に

MDNで作業を始める前に、下記の一覧にある推奨事項とガイドラインに目を通してください。

**プルリクエストは、既存の課題 (issue) を解決するか、部分的に修正するものにしてください。**
このような制約があるのは、他の誰かがすでに作業している可能性のある種類の作業を始めることを避けるためです。
協力したい [MDN リポジトリー](https://github.com/orgs/mdn/repositories) の課題やプルリクエストを検索し、始めたい作業がすでに作業されていないことを確認してください。
MDN プロジェクトに協力しようとするとき、あなたは以下のようないずれかの状況に置かれるでしょう。

- **プロジェクトに協力したい場合**、[MDN GitHub リポジトリー](https://github.com/orgs/mdn/repositories)（例: [`mdn/content` の issues](https://github.com/mdn/content/issues)）と私たちの [public GitHub project boards](https://github.com/orgs/mdn/projects) にある 'Issues' でタスクを探すことができます。
  その課題が誰かに割り当てられていないこと、誰もそのタスクのためのプルリクエストを開いていないことを確認してください。
  `good first issue` とラベル付けされた課題は、手始めに良いものです。

- **MDN で問題を見つけた場合**、まず課題を開いてください。**課題は、作業を始める前にメンテナーからのレスポンスが必要**です。これにより、プルリクエストで対処した問題が有効であり、プルリクが受け入れられることがわかるからです。その課題に関するより詳しい情報は、[GitHub の課題に関するコミュニティのページ](https://github.com/mdn/mdn/issues/new?labels=proposal%2Cneeds+triage&template=content-or-feature-suggestion.yml&title=Enter+your+proposal+here)で見つけることができます。

- **新しいコンテンツや機能を提案したい場合**は、 'New content or feature suggestion' という [GitHub の課題テンプレート](https://github.com/mdn/mdn/issues/new/choose)から送信してください。

どこから始めたらいいかわからない場合は、 [Discord サーバー](/discord)で私たちに声をかけてフィードバックを求めてください。

### プルリクエストを開く

プルリクエストを開くための準備ができたら、以下のガイドラインに従ってください。

- **プルリクエストは短く、1 つの課題に焦点を当てたものであるべきです。** 可能であれば、関連のある一連の変更を複数の小さなプルリクエストにまとめてください。
  プルリクエストが大きすぎた場合、レビュアーはそのプルリクエストを閉じ、一緒になっている論理的な変更の集合ごとにプルリクエストを送信するように要求することがあります。
- **変更点の説明を追加してください。** プルリクエストのコンテキストと根拠をできるだけ多く指定されたものを提供します。
- **閉じる課題へのリンクを追加してください。** プルリクエストの説明文に、その課題を完全に解決する場合は 'Fixes' を、関連する課題である場合は 'Relates to' を追加します。
  プルリクエストの課題へのリンクに関する詳しい情報は、[GitHub のドキュメント](https://docs.github.com/en/issues/tracking-your-work-with-issues/linking-a-pull-request-to-an-issue#linking-a-pull-request-to-an-issue-using-a-keyword)にあります。
- 先にマージしなければならないプルリクエストがある場合、依存関係へのリンクを持つ **'depends on' を追加してください**（例：他のリポジトリーにあるコードの例など）。
- **サンプルコードの変更は、コンテンツの変更と一緒に行ってください。** これは、更新された例が正しく提供されることを確実にするために重要です。
  例が使用される方法に影響を与えるようなコンテンツの変更を行う場合、関連するサンプルコードも更新する必要があります。
- **レビュアーを追加します。** チームメンバーやトピックオーナーなど、プルリクエストをレビューすべき人が既に決まっている場合、レビュアーを追加することができます。
- **文法だけの変更はしないでください。** MDN Web Docs は技術ドキュメントです。文法が間違っている場合を除いて、文のスタイルの変更を提案すべきではありません。
- 特定の書式設定に従ったページでは、**むやみに改行を追加したり削除したりしないようにしましょう。**
- **auto-merge を有効にしないでください。**

### プルリクエストを開いた後

- **CI の失敗を処理してください**。 GitHub Actions として自動テストが行われます。（`.github/workflows` を参照）
  これらのテストのうち 1 つ以上が失敗した場合、問題を解決するのはあなたの責任です。
  もし、問題を解決する方法がわからなければ、助けを求めることができます。
- **マージの競合を解決してください**。メインブランチとの競合が発生した場合、解決するのはあなたの責任です。
  これを行うには、`mdn/main` ブランチを自分のブランチにマージしてください。
  詳しくは、GitHub ドキュメントの [pull request の同期を維持する方法について](https://docs.github.com/ja/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/keeping-your-pull-request-in-sync-with-the-base-branch#pull-request-%E3%81%AE%E5%90%8C%E6%9C%9F%E3%82%92%E7%B6%AD%E6%8C%81%E3%81%99%E3%82%8B%E6%96%B9%E6%B3%95%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6)を参照してください。
- **フィードバックに対応してください。**
  これは、レビューに基づいてプルリクエストに変更を加える準備をしておくということです。
  レビューが行われ、変更が行われなかった場合、そのプルリクエストは閉じられるかもしれません。
- **レビュー中は忍耐強く。**
  MDN の組織は大量のプルリクエストを受け取っており、チームがあなたの協力をレビューするのに時間を必要とする場合があります。
- **閉じられたプルリクエストを再開しないでください。**
  新しいプルリクエストを作成する必要がある場合は、閉じたプルリクエストを参照させてください。

## プルリクエストのレビュープロセス

プルリクエストを開くと、レビュアーが `CODEOWNERS` ファイルに基づいて自動的に割り当てられますが、レビューを依頼したい特定の人物がいる場合は、手動で[レビューを依頼](https://docs.github.com/ja/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/requesting-a-pull-request-review)することができます。
また、私たちはプルリクエストのトリアージに役立つように、プルリクエストに自動ラベル付けを使用します。
メンテナーはプルリクエストをさらにトリアージし、コンテキストに基づいて必要であれば、`needs-info` や `on-hold` のような追加のラベルを追加することができます。

もしあなたがプルリクエストをレビューしたいが、レビュアーとして掲載されていない場合、あなた自身をレビュアーとして追加することができます。
レビューを始めるつもりであることをプルリクエストにコメントすることによって、最初に既存のレビュアーに確認するのが礼儀です。

### レビュアーと担当者

MDN Web Docs チームは、レビュアーと担当者 (assignee) を使用して、プルリクエストの状態を追跡しています。

- **レビュアー**とは、プルリクエストの変更点を評価し、作成者にフィードバックを提供する人たちです。
- **担当者** は、プルリクエストがブロックされないようにするための責任者です。
  すべてのプルリクエストに担当者がいるわけではありませんが、もしいれば、彼らはプルリクエストの進行を確認する責任があります。
  担当者は、マージも、クローズも、ブロックもされていない作業を自分自身で引き受けることによって、作業を完結させることを助けます。

プルリクエストのレビュアーや担当者は、変更点をマージする責任を負います。

レビューを始めるには、プルリクエストの説明を調べて、特定の誰もレビューすべきではないことを確認してください。
すべての継続的インテグレーション (CI) タスクが完全に完了し、マージの競合がないことを確認してください。

もしタスクが失敗したり、マージの競合があったりした場合は、作成者にそのことを伝えてください。作成者が責任をもって対処する必要があります。
作成者を **担当者** に設定すると、レビューを始める前に作成者に対してプルリクエストに注意を促すことができます。
作成者が助けを求めるためのドアを開けておいてください。特にプロジェクトに新しく参加した協力者の場合です。

### プルリクエストのレビュー

プルリクエストの変更点に関して言えば、コンテンツと文章は [MDN 執筆スタイルガイド](/ja/docs/MDN/Writing_guidelines/Writing_style_guide)に、サンプルコードは[コードスタイルガイド](/ja/docs/MDN/Writing_guidelines/Code_style_guide)に従わなければなりません。

プルリクエストをレビューするときは、次のようにしてください。

- プルリクエストに**コメントを追加**して、作者にあなたがプルリクエストに気づき、レビューを始めることを知らせてください。
  これは、他の誰かが不必要に同時にプルリクエストのレビューを始めるようなケースを避けるためです。
- プルリクエストに含まれる変更点のみに**レビューの範囲を限定**してください。
  プルリクエストに含まれていない他の改善点を解決するためには、その課題またはプルリクエストを開いてください。
- レビューに技術的な支援が必要な場合は、**助けを求めて** `review-help-need` ラベルを追加してください。
- 複雑すぎる、あるいは無関係な変更が複数格納されている場合、**無関係な変更を含むプルリクエストを閉じてください**。
  そのような場合、プルリクエストの作成者に、変更をより小さく分割して送信するよう依頼してください。
- あなたの仕事が手一杯で、レビューのための余裕がない場合は、**負荷分散をリクエストしてください**。
  `@core-yari-content` チームにタグ付けして、他の誰かが手順を踏めるかどうか依頼してください。
- 'depends on' で示されたプルリクエストが先にマージされていない状態で、 **マージを行わないでください**。
- **テストに失敗したプルリクエストをマージしないでください。**
  [オープンソースのエチケット](/ja/docs/MDN/Community/Open_source_etiquette) として、 `main` ブランチを安定に保つことは、協力者やメンテナー、自動化されたプロセスの混乱を避けるために良いことです。
  不安定な `main` ブランチは、他のすべてのプルリクエストをブロックし、他の貢献者のレビューやマージが困難になります。
  さらに、リポジトリーを見ている協力者は大量の通知を受け取り、テストの失敗によって発生させられる不要なノイズに苛立つことになります。
  失敗したテストを修正する方法がわからない場合は、[助けを求める](/ja/docs/MDN/Community/Communication_channels)か、プルリクエストを他の人に割り当ててください。

もしプルリクエストが、小さな誤字や他にも小さな課題を除けば良いものに見えたら、その問題を直接修正したいと思うかもしれません。
[プルリクエストが変更を許可する](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/allowing-changes-to-a-pull-request-branch-created-from-a-fork)ように設定されている場合は、これを行うことができます。
小さな問題を修正するための[提案としてコメントを使用](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/commenting-on-a-pull-request#adding-line-comments-to-a-pull-request)すると、一括してコミットすることができるのでおすすめです。

レビューを送信する際には、 **approve**（承認）、 **comment**（コメント）、 **request changes**（変更リクエスト）の 3 つの オプションをつけることができます。
この章では、各オプションを使用するタイミングについて、以下の節で説明します。

#### Requesting changes

あなたが提供したフィードバックが作成者によって対処された後、プルリクエストを承認してマージする前にレビュアーが再レビューする必要がある場合、 Request changes オプションを使用してください。

#### Comment

Comment オプションは、フィードバックが重要ではなく、再レビューを必要としない場合に使用されます。
要するに、あなたは作成者や他のレビュアーが適切な判断を使用することを信頼している場合です。

#### Approve

あなたの視点から見てすべてが順調で、マージする準備ができたときに Approve オプションを使用します。
レビューを送信した後、他のレビュアーがいないか、未対応のレビューコメントがなければ、安全にプルリクエストをマージすることができます。

#### 行き詰まったときの対処法

コンテンツの変更について理解できない場合、またはそれが自分には大きすぎ、複雑すぎると感じた場合でも、慌てないでください。
始めるには、プルリクエストの作成者に情報を要求することから始めると良いでしょう。

大規模で複雑なコンテンツの変更を、何の前触れもなくレビューするよう要求されることは、めったにありません。
しかし、もしそうなった場合は、プルリクエストの説明文に、背景となる情報を説明する課題へのリンクが張られているはずです。

それでもわからない場合、あるいはコンテンツが疑わしいと思われる場合は、MDN Web Docs チームに連絡を取り、助けを求めてください。

### 作成者とレビュアーの応答時間に関するガイドライン

この節では、あなたがプルリクエストの作成者であればレビューコメントに返信する際に、あなたがレビュアーであればプルリクエストをレビューする際に、予想される応答時間の詳細を説明します。

- **レビュー時**:
  プルリクエストのレビュアーは、2 週間以内に変更点をレビューできるようにする必要があります。
  プルリクエストが開かれた後の 2 週間で、レビュアーは以下のことができます。
  - いつからそのプルリクエストのレビューを始められるかコメントを残す。
  - 技術的または資源的な支援を依頼する。
- **変更リクエストへの対応:**
  プルリクエスト作成者は、4 週間以内にコメントに対して返答または修正する必要があります。
  もしプルリクエスト作成者がその時間内にレビューコメントに返答または修正することができない場合、レビュアーは以下のいずれかを行うことができます。
  - 変更をコミットし、プルリクエストをマージする
  - プルリクエストを閉じる

### 外部レビュアー

MDN content リポジトリーでのプルリクエストの中には、ブラウザーのベンダーや組織による、作成者とレビュアーが特定された特定の作業に関連するものがあります。
このような場合、作成者はプルリクエストの説明の一番下の行にレビュアーのユーザー名を記載してください。

```md
reviewer: @jpmedley
```

あなたがレビュー要求を受け取ったとしても、上記の方法で他のレビュアーが指定されていた場合は、その変更をレビューしないでください。
説明で述べたレビュアーが変更を承認した後、`CODEOWNERS` に承認の要求を依頼することになります。

## 読み物リスト

レビュアーは、以下の記事を読んで、よくある作業に役立ててください。

- [The Art of Closing](https://blog.jessfraz.com/post/the-art-of-closing/) では、未完成または却下されたプルリクエストを閉じる方法について説明します。
- [Kindness and Code Reviews: Improving the Way We Give Feedback](https://product.voxmedia.com/2018/8/21/17549400/kindness-and-code-reviews-improving-the-way-we-give-feedback) は、フィードバックをするための有益なヒントを与えてくれます。
- [Code Review Guidelines for the Reviewer](https://phauer.com/2018/code-review-guidelines/#code-reviews-guidelines-for-the-reviewer) は、良いフィードバックと悪いフィードバックの例を提供しています。
