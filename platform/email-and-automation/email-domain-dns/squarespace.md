---
description: Google Domains や Google Workspace で取得したドメイン（現在は Squarespace が管理）に、メール送信用の2つのレコード（TXT と CNAME）を追加する手順です。
---

# Squarespace（旧 Google Domains）でレコードを追加する

## この手順を使う人

* 以前 **Google Domains** でドメインを買った方（2024 年に Squarespace へ移りました）
* **Google Workspace**（Gmail のビジネス版）の申し込みと一緒にドメインを買った方（多くは Squarespace が管理しています）

→ 自分がどれか分からないときは [どこで管理されているか調べる](where-is-my-domain.md)

## 用意するもの

OpusBooster の「**ドメインと送信者**」画面に表示された2つのレコード。→ [メールドメインの接続](../email-domain-connection.md)

## ログインする場所

[account.squarespace.com/domains](https://account.squarespace.com/domains) を開き、「**Continue with Google**」を押して、**Google Domains や Workspace で使っていた Google アカウント**でログインします。Squarespace のアカウントは自動で作られているので、新しく登録する必要はありません。

## 手順

1. ドメインの一覧で、対象のドメインを押します。
2. 「**DNS**」→「**DNS Settings**」を開き、「**Custom Records**（カスタムレコード）」の「**Add record**」を押します。
3. **1つ目（TXT）**を入れて保存します。
   * **Host**: `@`
   * **Type**: `TXT`
   * **Text**: OpusBooster に表示された長い文字列を、コピーボタンで貼る
4. もう一度「**Add record**」を押し、**2つ目（CNAME）**を入れて保存します。
   * **Host**: `def._domainkey`（あとの「.あなたのドメイン」は自動で付きます）
   * **Type**: `CNAME`
   * **Data**: `client._domainkey.app-sources.com`

<!-- 📷 スクショ: 手順2 DNS Settings の Custom Records -->
<!-- 📷 スクショ: 手順3〜4 TXT / CNAME を入れた状態 -->

{% hint style="warning" %}
**すでにある行（MX や TXT など）は消さないでください。**
Gmail（Google Workspace）を使っている方は、メールを受け取るための行が最初から入っています。消すとメールが届かなくなります。今回は**2行を足すだけ**です。
{% endhint %}

## 追加したあと

OpusBooster の「ドメインと送信者」に戻り、「**ステータスを更新**」を押します。Squarespace の反映は **24〜48 時間**かかることがあります。→ [反映を待つ・うまくいかないとき](../email-domain-connection.md#not-verified)

## 公式の説明（英語）

* [Google Domains から Squarespace への移行について](https://support.squarespace.com/hc/en-us/articles/17131164996365)
* [ドメインの DNS レコードを編集する](https://support.squarespace.com/hc/en-us/articles/360002101888)
* [Google Workspace 経由で登録したドメインの管理](https://support.squarespace.com/hc/en-us/articles/24615057474061)

---

<!-- cta:opusbooster -->
{% hint style="success" %}
**自分の場合はどう使えばいいか**

[OpusBoosterの機能全体](https://opusbooster.com/features)を見る。設計から相談したい方は[15分の無料相談](https://opusbooster.com/consultation)、まず触ってみたい方は[14日間の無料トライアル](https://opusbooster.com/register)（クレジットカード不要）から。
{% endhint %}
