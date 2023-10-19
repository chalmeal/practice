### フロントサイドにおける認証認可(Authentication/Authorization)について

## SPAやSSGにおける認証情報の保持
### ユースケース
* ReactのuseContextでログイン情報を管理していた際にページのリロードによりログイン可否判定が否になる事象
  * ページリロード時にログイン情報を保持していたファイルが再リロードされる。
  * 再リロードされた際に初期値isLoginがfalseのため、毎回ログイン状態がfalseで返されていた。
```
const [isLogin, setIsLogin] = useState(false);  // ログイン判定を初期値でfalse

setIsLogin(true);  // useStateにおけるisLoginがtrue
```
> ページをリロードした際に、useStateのisLoginは初期値になる

```
window.localStorage.setItem("isLogin", String(true));  // localStorageにおけるisLoginがtrue
```
> localStorageの情報は維持されるため、ページをリロードしてもfalseにはならない