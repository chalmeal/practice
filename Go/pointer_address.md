### ポインタとアドレス

```
package main

import "fmt"

// Person は人間を表す構造体。
type Person struct {
    Name string
    Age  int
}

func main() {

    // 値として、pに代入
    p := Person{
        Name: "太郎",
        Age:  20,
    }

    fmt.Printf("最初のp :%+v\n", p)

    p2 := p
    p2.Name = "二郎"
    p2.Age = 21
    // pではなく
    fmt.Printf("p2で二郎に書き換えを行なったはずのp :%+v\n", p)

    // &pで*Person(Personのポインタ型)を生成する
    // p3はpのアドレスが格納されている状態になる
    p3 := &p
    p3.Name = "二郎"
    p3.Age = 21
    fmt.Printf("p3で二郎に書き換えを行なったp :%+v\n", p)

    name := "太郎"

    p4 := $name
    fmt.Printf("name :%v\n", p4)
    fmt.Printf("name :%v\n", *p4)
}
```

実行結果
```
最初のp :{Name:太郎 Age:20}
p2で二郎に書き換えを行なったはずのp :{Name:太郎 Age:20}
p3で二郎に書き換えを行なったp :{Name:二郎 Age:21}
name :0x1040c128
name :太郎
```

## デリファレンス
* p2
  * pの情報はp2が持つため、出力対象をpにするとpの情報が出力される
  * 出力対象をp2であれば書き換えた値で出力される
* p3
  * &pでデリファレンスすることでPersonへのポインタである`*Person型`の値を生み出す
  * p3で書き換えた値はpに反映されるため、出力対象pでも書き換えた値で出力される
## 16進数参照
* p4
  * 何も指定しない場合、アドレスを指している
  * *を付けることで、中身の「太郎」を取得できる
 
ref: [Goで学ぶポインタとアドレス](https://qiita.com/Sekky0905/items/447efa04a95e3fec217f)
