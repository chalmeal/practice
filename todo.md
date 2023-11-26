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
### v1.0.0定義
* Support
  * Minioの導入
  * Mailhogの導入
* Context
  * CSV出力、入力の確立方法
  * 監査ログ処理
* Validation
  * カスタムバリデーションの利用
    * https://qiita.com/RunEagler/items/ad79fc860c3689797ccc
* Transaction
  * トランザクション確立
    * readOnly含むIsolationの考慮など
    * store横断によるトランザクション確立方法
* Service
  * service層の導入
    * トランザクションをservice層で立てることで、複数のstore処理横断のトランザクション確立を実現
  * 監査ログ
    * serviceが動作した際に監査ログを残す処理を導入
* Security
  * ログイン処理の実装
    * ログインセッションの考慮（タイムアウト処理）
    * gorilla/csrfの利用
