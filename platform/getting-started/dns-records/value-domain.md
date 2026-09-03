---
description: バリュードメインで管理しているドメインに、メール送信用の2つのレコード（TXT と CNAME）を追加する手順です。バリュードメインは1行ずつ文字で書く方式です。
---

# バリュードメインでレコードを追加する

## この手順を使う人

ドメインの**ネームサーバーがバリュードメインのもの**（`ns1.value-domain.com` 〜 `ns5.value-domain.com`）になっている方です。コアサーバーや XREA など別のサーバーで運用している場合は、そちらの手順になります。→ [どこで管理されているか調べる](where-is-my-domain.md)

## 用意するもの

OpusBooster の「**ドメインと送信者**」画面に表示された2つのレコード。→ [メールドメインの接続](../email-domain-connection.md)

## 手順

バリュードメインは、他社のような入力欄ではなく、**1行に1レコードを文字で書く**方式です。落ち着いてやれば難しくありません。

1. [バリュードメインのコントロールパネル](https://www.value-domain.com/) にログインします。
2. 左のメニューの「**ドメイン**」→「**ドメインの設定操作（登録済みドメイン一覧）**」を押します。
3. 対象ドメインの「**DNS/URL**」を押します。
4. 大きな文字の欄が出ます。**すでに書いてある行は消さず**、いちばん下に次の2行を追加します（`@` はドメイン自体を表します）。

```
txt @ ここにOpusBoosterに表示された長い文字列
cname def._domainkey client._domainkey.app-sources.com.
```

   * 1行目: `txt`、半角スペース、`@`、半角スペース、OpusBooster の値（コピーボタンで貼る）
   * 2行目: そのまま写してください。**最後の「.」（ドット）も含めます**
5. 「**保存**」を押します。

<!-- 📷 スクショ: 手順3 一覧の「DNS/URL」 -->
<!-- 📷 スクショ: 手順4 文字欄の最後に2行を足した状態 -->

{% hint style="danger" %}
**元からある行を消さないでください。**
この欄には、サイトやメールを動かしている大事な行も入っています。行を消すとサイトやメールが止まります。**足すだけ**にしてください。
{% endhint %}

## 追加したあと

OpusBooster の「ドメインと送信者」に戻り、「**ステータスを更新**」を押します。バリュードメインの反映は **5〜30 分**ほどです。長くて 48 時間で「**確認済み**」になります。→ [反映を待つ・うまくいかないとき](../email-domain-connection.md#not-verified)

## バリュードメインの公式の説明

* [DNS情報・URL転送の設定](https://www.value-domain.com/userguide/manual/moddns)
* [ネームサーバーの変更](https://www.value-domain.com/userguide/manual/modns)

---

<!-- cta:opusbooster -->
{% hint style="success" %}
**自分の場合はどう使えばいいか**

[OpusBoosterの機能全体](https://opusbooster.com/features)を見る。設計から相談したい方は[15分の無料相談](https://opusbooster.com/consultation)、まず触ってみたい方は[14日間の無料トライアル](https://opusbooster.com/register)（クレジットカード不要）から。
{% endhint %}
