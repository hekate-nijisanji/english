# 単語データの出典と加工

## 対象と件数

- `words.json`: 5,000件、異なる英語見出し語5,000件、異なるID 5,000件。小学校・中学校での学習を意識した初期40件と、一般英語の頻度順語彙からなる参考リストです。
- 初期40件は従来の学習記録互換性のため、ID・内容を保持しています。
- 追加4,764件: LexiCore-5000のrank順の語彙候補に、EJDict-handの辞書見出し・訳語を照合して組み合わせました。
- 追加196件: EJDict-handの100/850/2000 frequent-word listsから、上記および初期40語との重複を除いて補いました。
- 大文字小文字を無視して見出し語重複を除去しました。IDの重複も検査しています。EJDictの複数の語義は、主に見出し語に対応する辞書の先頭寄りの意味を短く整形し、重要語の一部は基本的な意味を編集者が補いました。すべての語義・品詞を人手で校閲した教材ではありません。
- 例文は元の40件だけです。追加4,960件は例文と訳文を空欄にしています。出典のない例文は作っていません。
- 頻度帯1～5はLexiCore rankの1,000語幅の区分で、学年・日本の学校での学習順序を表しません。補足語は「頻出補足」です。

## 出典

- **LexiCore-5000 v1.0.0**: [X-Trivle/LexiCore](https://github.com/X-Trivle/LexiCore), [NOTICE](https://github.com/X-Trivle/LexiCore/blob/main/NOTICE.md), [ライセンス](https://github.com/X-Trivle/LexiCore/blob/main/LICENSE)。CC BY 4.0。必要な帰属表示: “LexiCore-5000 (v1.0.0), https://github.com/X-Trivle/LexiCore — CC BY 4.0. Frequency evidence derived from FineWeb, FineWeb-Edu, Wikipedia (20231101.en), OPUS-OpenSubtitles 2024 and Common Crawl CC-MAIN-2026-34.” このアプリでは語彙候補をEJDict訳語と組み合わせ、項目を加工しています。LexiCore README/NOTICEが説明する頻度推定・品詞/レベル推定の制約に留意してください。
- **EJDict-hand**: [kujirahand/EJDict](https://github.com/kujirahand/EJDict), [README](https://github.com/kujirahand/EJDict/blob/master/README.md), [LICENSE](https://github.com/kujirahand/EJDict/blob/master/LICENSE)。リポジトリでPublic Domain / CC0として案内される英和辞書データです。訳語と頻度語リストの出典です。収録訳の品質・適切さは全件独立検証していません。
- **品詞の補助**: Princeton WordNet 3.0 indexファイルの品詞情報を利用し、一般的な学校文法の機能語には一部手動の品詞ラベルを設定しました。WordNet英語見出しにない語はその他または辞書の補助タグとなる場合があります。
- **学習範囲の参考**: 文部科学省『中学校学習指導要領（平成29年告示）解説 外国語編』[公式PDF](https://www.mext.go.jp/component/a_menu/education/micro_detail/__icsFiles/afieldfile/2019/03/18/1387018_010.pdf)。語数の目安を参考にしています。公式の単語一覧をデータへ転載したものではありません。

## 確認上の制約

5,000件の構造・見出し重複・ID重複・必須フィールドを自動検査しました。辞書訳、全品詞、学校学年への個別配当を人手で全5,000件校閲したものではありません。英語学習の補助リストとして提供し、教科書の完全網羅や語義の完全性は保証しません。追加・訂正する際は出典ラベルを残し、例文は利用許諾が明確な教材から追加してください。
