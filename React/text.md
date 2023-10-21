### text base

* npm install時のエラー回避

`npm install --save --legacy-peer-deps {パッケージ}`

## React.createContext
* propsによるバケツリレー方式のデータ渡しを回避することができる

**利用しない場合**
```
■ Parent
const data = useState("テストデータ");
<Child data={data} />
↓
■ Child
function Child(props: Props){
  <Child2 data={props.data} />  // Childでは利用せず、Child2に値を渡すだけ
}
↓
■ Child2
function Child2(props: Props){
  <Component>{props.data}</Component>  // ここで初めて利用
}
```
**利用する場合**
```
■ Parent
const DataContext = React.createContext("テストデータ");
<Child />
↓
■ Child
function Child(props: Props){
  <Child2 />
}
↓
■ Child2
function Child2(){
  <DataContext.Consumer>
    { (context) => {
        <Component>{context.data}</Component>
      }
    }
  </DataContext.Consumer>
}
```


## Hook

### useContext
* 
