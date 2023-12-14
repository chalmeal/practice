### v1.0.0

v1.0.0リリースノート

## todo
* Context
  * CSV出力、入力の確立方法
  * 監査ログ処理
  * Pagination処理
* Validation
  * カスタムバリデーションの利用
    * https://qiita.com/RunEagler/items/ad79fc860c3689797ccc
* Transaction
  * トランザクション確立
    * readOnly含むIsolationの考慮など
* Service
  * 監査ログ
    * serviceが動作した際に監査ログを残す処理を導入
  * Handler→Service→Store構成の見直し
    * 例）userHandler→userService→Store
* Security
  * ログイン処理の実装
    * ログインセッションの考慮（タイムアウト処理）
    * JWTの利用
    * gorilla/csrfの利用
