FORMAT: 1A

# Polls
サンプルAPIの名前を「Polls」にします。

# Group 質問
「質問」に関するAPIのリソースを集約する。

## 質問一覧 [/questions]
### 一覧取得 [GET]
+ Response 200 (application/json)
    ```json
    [
        {
            "question": "好きな開発言語はなんですか？",
            "published_at": "2014-11-11T08:40:51.620Z",
            "url": "/questions/1",
            "choices": [
                {
                    "choice": "Swift",
                    "url": "/questions/1/choices/1",
                    "votes": 2048
                },{
                    "choice": "Python",
                    "url": "/questions/1/choices/2",
                    "votes": 1024
                }
            ]
        }
    ]
    ```

### 新規投稿 [POST]
質問の新規投稿用のアクションです。

+ question (string) - 質問文
+ choises (array[string]) - 選択肢の配列

+ Request (application/json)
    ```json
    {
        "question": "好きな開発言語はなんですか？",
        "choices": [
            "Swift",
            "Python"
        ]
    }
    ```
+ Response 201 (application/json)

    + Headers

            Location: /questions/1

    + Body
        ```json
        {
            "question": "好きな開発言語はなんですか？",
            "published_at": "2014-11-11T08:40:51.620Z",
            "url": "/questions/1",
            "choises": [
                {
                    "choise": "Swift",
                    "url": "/questions/1/choises/1",
                    "votes": 0
                },{
                    "choise": "Python",
                    "url": "/questions/1/choises/2",
                    "votes": 0
                }
            ]
        }
        ```

## 単体質問 [/questions/{question_id}]

### 質問詳細取得 [GET]
+ Parameters

    + question_id (number) - 質問のIDで整数のみ。

+ Response 200 (application/json)
    ```json
    {
        "question": "好きな開発言語はなんですか？",
        "published_at": "2014-11-11T08:40:51.620Z",
        "url": "/questions/1",
        "choises": [
            {
                "choise": "Swift",
                "url": "/questions/1/choises/1",
                "votes": 0
            },{
                "choise": "Python",
                "url": "/questions/1/choises/2",
                "votes": 0
            }
        ]
    }
    ```

### 削除 [DELETE]

+ Response 204
