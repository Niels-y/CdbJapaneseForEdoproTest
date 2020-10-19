# CdbJapaneseForEdopro

Card data based on the English card data of YGOPro `Project Ignis`, with Japanese card names and text added to some cards.  
YGOPro `Project Ignis` の英語カードデータをベースに、一部のカードに **日本語の名前とテキストを追加** したカードデータ。
* Most of the cards that existed by about 2020/09 have been translated.  
  2020/09くらいまでに存在していたカードはほとんど翻訳されている。

#### note / 備考

* YGOPro other than `Project Ignis` may be used differently or may not be available.  
  `Project Ignis` 以外のYGOProでは使用方法が異なる場合や、使用できない場合がある。
 
#### Untranslated cards / 翻訳されていないカード

1. Missing cards in the Japanese card data  
   日本語のカードデータに欠落しているカード
   * e.g.《Datascape Rabbit - TuTu》《電脳堺嫦－兎々》
1. Cards with different internal-ID for Japanese card data and English card data  
   日本語のカードデータと英語のカードデータの内部IDが異なるカード
   * e.g. ID change with the release of pre-release cards  
     例. プレリリースカードのリリースに伴うID変更
   * e.g. Cards with an internal ID for each of the multiple illustrations  
     例. 複数のイラストのそれぞれに内部IDが付与されたカード
1. Other Reasons  
   その他の理由

#### Card data used for translation / 翻訳に使用したカードデータ

* Japanese card data: YGOPro `hollow`, on **Before and after support was discontinued** / **サポート停止前後**
* English card data: YGOPro `Project Ignis`, on **2020/10/19**

#### Examples of Translations / 翻訳の例

* card name / カード名: `Ｅ・ＨＥＲＯ フレイム・ウィングマン(Elemental HERO Flame Wingman)`
* card text / テキスト:
```
「Ｅ・ＨＥＲＯ フェザーマン」＋「Ｅ・ＨＥＲＯ バーストレディ」
このカードは融合召喚でしか特殊召喚できない。
①：このカードが戦闘でモンスターを破壊し墓地へ送った場合に発動する。
そのモンスターの元々の攻撃力分のダメージを相手に与える。
"Elemental HERO Avian" + "Elemental HERO Burstinatrix"
Must be Fusion Summoned and cannot be Special Summoned by other ways. When this card destroys a monster by battle and sends it to the Graveyard: Inflict damage to your opponent equal to the ATK of the destroyed monster in the Graveyard.
```

## Usage / 使い方

1. Open `C:\ProjectIgnis/config/configs.json` with a text editor.  
   `C:\ProjectIgnis/config/configs.json` をテキストエディタで開く。
1. Add the following content after line 13, and save.  
   13行目の後に以下の内容を追加して保存する。
1. Run `Project Ignis`. Then the `repositories/Japanese` folder is created automatically and the Japanese card data is downloaded.  
   `Project Ignis` を実行する。すると自動的に `repositories/japanese` フォルダが作成され日本語のカードデータがダウンロードされる

Content to be added / 追加する内容
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

#### screenshot / スクリーンショット

<img width="564" alt="edit_config_json_notepad_mini" src="https://user-images.githubusercontent.com/72937182/96492130-21f7cf80-127e-11eb-8334-12a9de35da60.png">

#### How to stop / 停止方法

How to avoid loading translation card data temporarily  
翻訳カードデータを一時的に読み込まない方法
* Change `"should_read": true` in the second line from the bottom of the added content to `"should_read": false`.  
  追加した内容の下から2行目の `"should_read": true` を `"should_read": false` に変更する。

How to delete translation card data
翻訳カードデータを削除する方法
* Restore the `config/configs.json`. And delete the `repositories/Japanese` folder.  
  `config/configs.json` を元に戻す。そして `repositoriesjapanese` フォルダを削除する。

## Data changed by translation / 翻訳により変更されたデータ

* card name
* card text

## supplement / 補足
* Card names and text are in both Japanese and English for the following reasons.  
  カード名とテキストは、以下の理由で日本語と英語の両方がある。
  * Some cards have not been translated. Untranslated cards cannot be searched in Japanese, but can be searched in English. Therefore, the English card names and text are left behind.  
    翻訳されていないカードもある。未翻訳のカードは日本語では検索できないが、英語では検索できる。そのため、英語のカード名とテキストは残している。
* If the English YGOPro has been changed from the translation card data, it will probably be reflected in the following way.  
  翻訳カードのデータから英語のYGOProが変更されている場合、おそらく以下のように反映される。
  * atk, category: not reflected. They remain fixed to those of the translation card data.  
    攻撃力、カテゴリ: 反映されない。翻訳カードデータに固定されたまま。
  * effect: reflected. The latest behavior of `Project Ignis`.  
    効果: 反映される。 `Project Ignis` の最新の挙動。
