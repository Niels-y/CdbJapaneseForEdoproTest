# CdbJapaneseForEdopro
cdb for EDOPRO, added japanese name and text.

## 概要

英語版ADSである **Project Ignis (EDOPRO)** のカードデータ(cdb)をもとにして、 **一部カードに日本語のカード名・テキストを追加** したカードデータ(cdb)
* (2020年9月ごろまでに存在していたカードはほとんど翻訳済み)

#### 備考

* Project Ignis以外のADSでは導入方法が違ったり、そもそも使用不可能だったりする
* 現時点で未翻訳のカードについての翻訳は **「最新カード入りの日本語cdb」が見つからない限り行わない** 
    * 理由: 翻訳カードデータの作成には「日本語カードデータ(cdb)」を使っており、手元の日本語cdbに入っていないカードは翻訳不可能なため

## 導入手順

1. Project Ignisのフォルダ内にある `config/configs.json` をメモ帳などで開く
    * Project IgnisのフォルダはWindowsなら基本的に `C:\ProjectIgnis`
1. 13行目の直後に下記内容を追加し、上書き保存する
1. その後Project Ignisを実行する
    * すると自動的に `repositories/japanese` フォルダが作成され、日本語カードデータがダウンロードされる

config.jsonに追加する内容
  ```
		{
			"url": "https://github.com/Niels-y/CdbJapaneseForEdopro",
			"repo_name": "Japanese CardData",
			"repo_path": "./repositories/japanese",
			"has_core": false,
			"core_path": "",
			"data_path": "",
			"script_path": "",
			"should_update": true,
			"should_read": true
		},
```

#### 保存後のconfig.jsonの状態 (メモ帳などのスクリーンショット)

<img width="400" alt="edit_config_json_notepad" src="https://user-images.githubusercontent.com/72937182/96163562-01193c80-0f55-11eb-8f52-9394dadfd563.png"> <img width="400" alt="edit_config_json_terapad" src="https://user-images.githubusercontent.com/72937182/96163571-04142d00-0f55-11eb-8e54-49788f00a00c.png">

#### 元に戻す方法

* 翻訳カードデータを一時的に読み込まないようにする方法
    * 導入手順2の `config/configs.json` の追加箇所の下から2行目にある `"should_read": true` を `"should_read": false` に書き換える
* 翻訳カードデータを完全に削除する方法
    * 導入手順2の `config/configs.json` を元に戻す。そして `repositories` フォルダの中にある `japanese` フォルダを削除する

## 翻訳内容

#### 翻訳により変化したもの
* カード名: 日本語カード名と英語カード名をつなげた。英語カード名は括弧をつけた
* テキスト: 日本語テキストと英語テキストを改行してつなげた

#### 補足
* カード名・テキストに元の英語を残しているのは「一部のカードが翻訳されていない」ことを考慮したため
    * 未翻訳カードは日本語検索では引っかからないので英語検索する必要がある
    * 翻訳済みカードも英語検索で引っかかるよう、英語のカード名・テキストを残している
* もし今後EDOPRO側で「翻訳対象カードのカードデータ」が変更された場合、それが反映されるかどうかはおそらく以下のようになる
    * 攻撃力や所属カテゴリなど: 反映されない (=翻訳カードデータ生成時点のものに固定されたまま)
    * 効果処理: 反映される (=常に最新のものとなる)

#### 翻訳例

* カード名: `Ｅ・ＨＥＲＯ フレイム・ウィングマン(Elemental HERO Flame Wingman)`
* テキスト:
```
「Ｅ・ＨＥＲＯ フェザーマン」＋「Ｅ・ＨＥＲＯ バーストレディ」
このカードは融合召喚でしか特殊召喚できない。
①：このカードが戦闘でモンスターを破壊し墓地へ送った場合に発動する。
そのモンスターの元々の攻撃力分のダメージを相手に与える。
"Elemental HERO Avian" + "Elemental HERO Burstinatrix"
Must be Fusion Summoned and cannot be Special Summoned by other ways. When this card destroys a monster by battle and sends it to the Graveyard: Inflict damage to your opponent equal to the ATK of the destroyed monster in the Graveyard.
```
 
## 翻訳されていないカード

1. 翻訳に使用した日本語カードデータに、存在していなかったカード
    * 例: `Datascape Rabbit - TuTu` (`電脳堺嫦－兎々`)
1. 翻訳に使用した日本語カードデータと英語カードデータで、内部IDが異なるカード
    * 補足: イラスト違いなどで複数の内部IDがあるカードは、イラストごとに翻訳有無が異なるかもしれない
1. 翻訳に使用した日本語カードデータから、内部IDが変更されたカード
    * 補足: ADSの開発体制を知らないため、内部IDの変更基準は不明。プレリリースのカードが本リリースされた時とかかも？
1. その他の理由での翻訳漏れ

#### 翻訳に使用したカードデータ(cdbファイル)
* 日本語カードデータ: 日本語版ADS **hollow** の **サポート停止時点 or その少し前の時点** のもの
* 英語カードデータ: 英語版ADS **Project Ifnis** の **2020/10/13～2020/10/14 頃** のもの

## 備考

* もしどなたかが未翻訳カードを翻訳した「追加翻訳cdb」を提供してくれても、本リポジトリに含めることはしない。本リポジトリ内のcdbは自動生成したものであり、それ以外は入れるつもりはない
    * 追加翻訳cdbと元のcdbでファイル名が被らないようにしてくれれば「config.jsonのshould_updateをfalseにして、追加翻訳cdbをrepositories/japaneseに入れる」という手順により、追加翻訳cdbを適用できる
        * そのように利用してもらうことは歓迎する。また、もし許可をいただければそのファイルがあるURLをここに記載させていただく
