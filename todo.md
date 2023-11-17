### todo

## 2023/11/09
* Golang ジェネリクス利用
  * https://zenn.dev/nobishii/articles/type_param_intro* 
* Git MultiAccount 切り替え
  * 下記のどれか（上から順に理想）
    * vscode上でGUIベースの切り替え
    * ディレクトリごとの.gitconfigによる切り替え → https://qiita.com/shionit/items/fb4a1a30538f8d335b35
    * コマンドによる簡易切り替え（1行程度のコピペレベルが望ましい）
    * shell実行による切り替え

## golang-package
* Connect
  * DB接続情報
  * Minioの導入
  * Mailhogの導入
* util
  * uuid
  * JST-Time
  * sql.NullString
    * Stringだけ取りたい
* Response
  * statusの再考慮
  * API側からのメッセージレスポンス
    * UI側で依存しないように
* Validation
  * カスタムバリデーションの利用
    * https://qiita.com/RunEagler/items/ad79fc860c3689797ccc
* Transaction
  * トランザクション確立
    * readOnly含むIsolationの考慮など
    * store横断によるトランザクション確立方法
