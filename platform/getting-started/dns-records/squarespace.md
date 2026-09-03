---
description: Google Domains や Google Workspace で取得したドメイン（現在は Squarespace が管理）に、OpusBooster 用のレコード（サイト用 / メール用）を追加する手順です。
---

# Squarespace（旧 Google Domains）でレコードを追加する

## この手順を使う人

* 以前 **Google Domains** でドメインを買った方（2024 年に Squarespace へ移りました）
* **Google Workspace**（Gmail のビジネス版）の申し込みと一緒にドメインを買った方（多くは Squarespace が管理しています）

→ 自分がどれか分からないときは [どこで管理されているか調べる](where-is-my-domain.md)

## 追加する行を決める

やりたいことに合わせて、A・B のどちらか、または両方の行を用意します。同じ画面で足せるので、両方やるなら一度で済みます。

**A. サイトを自分のドメインで表示する（2行）** — 値は OpusBooster の「**ウェブサイト/ファネルの設定 → ドメイン**」画面のもの。→ [カスタムドメインの接続](../custom-domain.md)

| Type | Host | Data |
|---|---|---|
| **A** | `@` | 画面に表示された数字（IPアドレス） |
| **CNAME** | `www` | 画面に表示された値 |

**B. メールを自分のドメインから送る（2行）** — 値は「**メール & オートメーション → 設定 → ドメインと送信者**」画面のもの。→ [メールドメインの接続](../../email-and-automation/email-domain-connection.md)

| Type | Host | Data / Text |
|---|---|---|
| **TXT** | `@` | 画面に表示された長い文字列 |
| **CNAME** | `def._domainkey` | `client._domainkey.app-sources.com` |

{% hint style="warning" %}
**A（サイト用）を入れると、サイトの表示先が OpusBooster に切り替わります。** Squarespace のサイトや Google サイトに向いている `@` の A や `www` の行がある場合は、足すのではなく**値を書き換え**ます（A が2つあると繋がりません）。B（メール用）は足すだけで、今あるものは変わりません。**Gmail（Google Workspace）を使っている方は、MX の行は絶対に消さないでください**（メールが届かなくなります）。
{% endhint %}

## ログインする場所

[account.squarespace.com/domains](https://account.squarespace.com/domains) を開き、「**Continue with Google**」を押して、**Google Domains や Workspace で使っていた Google アカウント**でログインします。Squarespace のアカウントは自動で作られているので、新しく登録する必要はありません。

## 手順

1. ドメインの一覧で、対象のドメインを押します。
2. 「**DNS**」→「**DNS Settings**」を開き、「**Custom Records**（カスタムレコード）」の「**Add record**」を押します。
3. 上で決めた行を **1行ずつ**入れて保存します。
   * **Host**: 表のとおり（`www` や `def._domainkey` のあとの「.あなたのドメイン」は自動で付きます）
   * **Data / Text**: OpusBooster の画面からコピーボタンで貼る

<!-- 📷 スクショ: 手順2 DNS Settings の Custom Records -->
<!-- 📷 スクショ: 手順3 行を入れた状態 -->

## 追加したあと

* **サイト用**: OpusBooster の「ドメイン」画面で接続の状態を確認します。Squarespace の反映は 24〜48 時間かかることがあります。→ [カスタムドメインの接続](../custom-domain.md)
* **メール用**: 「ドメインと送信者」で「**ステータスを更新**」を押します。24〜48 時間で「確認済み」。→ [反映を待つ・うまくいかないとき](../../email-and-automation/email-domain-connection.md#not-verified)

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
