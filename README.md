# APIBlueprint_Tutorial

脱Excel設計書を目指したく、検索をしていたところ、「API Blueprint」に出会った。  
公式サイトにチュートリアルが記載されていたので、その内容をまとめたものを勉強用に作成したものです。  
これから勉強される方の参考になれば幸いです。

## 使ったツール
- [VSCode](https://code.visualstudio.com/)
- [API Blueprint](https://apiblueprint.org/)
    - [API Blueprint Tutorial](https://apiblueprint.org/documentation/tutorial.html)
- Aglio
- Drakov

## Drakovを使ったモックサーバに対してcURLで動作確認するコマンド例

「-i」のオプションを付与し、HTTPステータスコードも確認できるようにしています。

- 一覧取得
    ```bash
    curl -i http://localhost:3000/questions
    ```
- 新規登録
    ```bash
    curl -i -X POST -H "Content-type: application/json" -d '{"question":"好きな開発言語はなんですか？","choices":["Swift","Python"]}' http://localhost:3000/questions
    ```
- 削除
    ```bash
    curl -i -X DELETE http://localhost:3000/questions/1
    ```
