### 🔍 Grounding with Bing Search vs. Bing Custom Search

| 項目 | Grounding with Bing Search | Grounding with Bing Custom Search |
|------|-----------------------------|-----------------------------------|
| **検索対象** | Bing全体のパブリックWeb | 指定したドメイン・サブドメインのみ |
| **柔軟性** | 一般的なWeb情報を広く取得 | 検索対象を厳密に制限可能（企業サイトなど） |
| **設定方法** | Azure portalでBing Searchリソースを作成 | Azure portalでCustom Searchリソース＋構成インスタンスを作成 |
| **コンプライアンス** | Azureのコンプライアンス境界外で処理される | 同様にAzure境界外で処理されるが、**Bing Custom Search TOU**に準拠 |
| **利用コスト** | Bing Search APIの利用に応じて課金 | Bing Custom Search APIの利用に応じて課金（構成次第で変動） |
| **応答の精度** | 幅広い情報を取得できるがノイズも含まれる | 限定された情報源から取得するため精度が高い可能性あり |
| **ユースケース例** | 「今日の天気は？」「最新のニュースは？」など一般的な質問 | 「Contoso製品の仕様は？」「社内FAQの検索」など限定的な情報取得 |
| **検索クエリの制御** | クエリはBingに直接送信される | クエリは構成インスタンスに基づき制限される |
| **引用情報の扱い** | Bing検索結果のURLが引用される | 指定ドメイン内のページURLが引用される |

#### 選択のポイント
- 広範な情報が必要な場合 → Bing Search が適している。
- 特定の情報源に限定したい場合 → Bing Custom Search が有効。
- 社内ポータルや製品サイトなど、信頼できる情報に絞りたい → Bing Custom Search を推奨。