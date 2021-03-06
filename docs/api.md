# API詳細

## version

WebAPIのバージョンと、提供するBCDiceのバージョンが返却されます。

### URL

`/v1/version`

### 引数

なし

### レスポンス例

```json
{
  "api" : "0.0.0",
  "bcdice" : "2.02.64"
}
```


## systems

WebAPIで利用できるダイスボットの一覧が返却されます。ここで得られる名前はダイスロールの実行時に利用します。ここで使われる名前は、各ダイスボットが `gameType()` で返す文字列です。

### URL

`/v1/systems`

### 引数

なし

### レスポンス例

```json
{
  "systems" : [
    "Amadeus",
    "Cthulhu",
    "DoubleCross",
    "DungeonsAndDoragons",
    "DiceBot",
    "Gorilla",
    "Gundog",
    "LogHorizon",
    "Nechronica",
    "SwordWorld2.0"
  ]
}
```

## diceroll

### URL

`/v1/diceroll`

### 引数

パラメータ  | 例            | 説明
--------- | ------------- | -----
`system`  | `Cthulhu`     | システム名
`command` | `1d100>=70`   | コマンドの文字列

### レスポンス例

```json
{
  "ok" : true,
  "result" : ": (1D100>=70) ＞ 87 ＞ 成功",
  "secret" : false
}
```

`secret` はシックレットダイスロールであるかを示します。
