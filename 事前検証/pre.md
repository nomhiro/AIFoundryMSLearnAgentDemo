プロジェクトを作成
![alt text](image.png)

プロジェクト名：copilot-for-everything
![alt text](image-1.png)

Agentsページへ。
まずLLMモデルをデプロイ。ここではgpt-4.1
![alt text](image-2.png)

![alt text](image-3.png)

Agent名
![alt text](image-4.png)

Knowledgeに追加
![alt text](image-5.png)


Grounding with Bing Custom Search connection を選ぶ
※[Grounding with Bing Searchとの違い](../BingSearch_vs_BingSearchCustomSearch.md)

![alt text](image-6.png)

Bing Search リソースとのConnectionを作成。
![alt text](image-7.png)

まずはBing Searchリソースを作成
![alt text](image-9.png)

Azure Portalに遷移してCustom Bing Searchを作成
![alt text](image-8.png)

![alt text](image-10.png)

作成完了
![alt text](image-11.png)

configurationを作成する。ドメインを指定した検索にする
![alt text](image-15.png)

Webアドレスにlearnを追加
![alt text](image-16.png)

Rank adjusted
- Rank Adjustedはそのページを優先的に検索をかけるブースト機能。おそらく検索スコアが何倍かされる仕様だと思われる。
  - Boost, Super Boost は優先度を上げる。
  - Demote は優先度を下げる

作成完了
![alt text](image-17.png)


AI Foundry に戻って、一つ前のcreate connectionをやり直し。
![alt text](image-12.png)

作成したbing custom searchが選ばれる
右上のAdd connection で追加
![alt text](image-13.png)

configurationがないといわれる。
![alt text](image-14.png)


作成したBing Custom SearchのConnectionをKnowledgeに指定
![alt text](image-18.png)

設定はデフォルトのままで。
- Count：
- Set Language：
- Market：
- Freshness：
![alt text](image-19.png)

Configurationは作成したMSLearnを指定



最後にInstructionを設定
```
BingCustomSearchを使って質問に答えてください。
```

![alt text](image-20.png)

### 動作確認
通常のChatPlaygroundと比較
```text
Azure AI Foundry エージェントがMCPサーバのツールを使うことはできる？
```

```text
AI Foundry で、MS Learnのサイトを検索するエージェントを作成したいです。もっとも簡単なやり方を教えて！
```

```text
Azure AI Foundry のAI Red Teaming Agent とはなに？
```



### 注意事項
開発者とエンド ユーザーは、Bing Custom Search を使用して Grounding から返された生コンテンツにアクセスできません。 ただし、モデルの応答には、応答の生成に使用される Web サイトへのリンクを含む引用が含まれており、Agents Service によって提供されるメカニズムを使用して保存できます。    