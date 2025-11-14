graph TD;
    A[Google スライドのフローチャート] --> B{Mermaid コードへ変換？};
    B -- はい --> C[手動でコードを記述];
    B -- いいえ --> D[画像として保存];
    C --> E[GitHubに貼り付け];
    D --> E;
