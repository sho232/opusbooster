---
description: Cloudflare で管理しているドメインに、OpusBooster 用のレコード（サイト用 / メール用）を追加する手順です。「プロキシ」をオフにするのがポイントです。
---

# Cloudflare でレコードを追加する

## この手順を使う人

ドメインの**ネームサーバーが Cloudflare のもの**（`〜.ns.cloudflare.com`）になっている方です。→ [どこで管理されているか調べる](where-is-my-domain.md)

## 追加する行を決める

やりたいことに合わせて、A・B のどちらか、または両方の行を用意します。同じ画面で足せるので、両方やるなら一度で済みます。

**A. サイトを自分のドメインで表示する（2行）** — 値は OpusBooster の「**ウェブサイト/ファネルの設定 → ドメイン**」画面のもの。→ [カスタムドメインの接続](../custom-domain.md)

| Type | Name | Content / Target | Proxy status |
|---|---|---|---|
| **A** | `@` | 画面に表示された数字（IPアドレス） | **DNS only（灰色）** |
| **CNAME** | `www` | 画面に表示された値 | **DNS only（灰色）** |

**B. メールを自分のドメインから送る（2行）** — 値は「**メール & オートメーション → 設定 → ドメインと送信者**」画面のもの。→ [メールドメインの接続](../../email-and-automation/email-domain-connection.md)

| Type | Name | Content / Target | Proxy status |
|---|---|---|---|
| **TXT** | `@` | 画面に表示された長い文字列 | （TXT は元からプロキシされません） |
| **CNAME** | `def._domainkey` | `client._domainkey.app-sources.com` | **DNS only（灰色）** |

{% hint style="warning" %}
**A（サイト用）を入れると、サイトの表示先が OpusBooster に切り替わります。** 元からある `@` の A や `www` の行がある場合は、足すのではなく**値を書き換え**ます（A が2つあると繋がりません）。B（メール用）は足すだけで、今あるものは変わりません。
{% endhint %}

## 手順

1. [Cloudflare ダッシュボード](https://dash.cloudflare.com/) にログインし、対象のドメインを押します。
2. 左のメニューの「**DNS**」→「**Records**（レコード）」を押します。
3. 「**Add record**（レコードを追加）」を押し、上で決めた行を **1行ずつ**入れて「**Save**（保存）」。
   * **Name**: 表のとおり（`www` や `def._domainkey` のあとの「.あなたのドメイン」は自動で付きます）
   * **Content / Target**: OpusBooster の画面からコピーボタンで貼る
   * **Proxy status**: 雲のマークを**灰色（DNS only）**にする

<!-- 📷 スクショ: 手順3 Add record のフォーム。Proxy status の雲アイコンが灰色になっている状態を赤枠で -->

{% hint style="danger" %}
**「Proxy status」は灰色の雲（DNS only）にしてください。**
オレンジ色の雲（Proxied）のままだと、メールの署名の確認ができず、いつまでも「確認済み」になりません。サイト用の行も、OpusBooster が SSL（鍵マーク）を発行する妨げにならないよう、灰色にしておくのが確実です。Cloudflare の公式説明にも、メール認証用（DKIM）のレコードは DNS only にするよう書かれています。
{% endhint %}

## 追加したあと

* **サイト用**: OpusBooster の「ドメイン」画面で接続の状態を確認します。Cloudflare は 5 分ほどで反映されることが多く、最長 48 時間。→ [カスタムドメインの接続](../custom-domain.md)
* **メール用**: 「ドメインと送信者」で「**ステータスを更新**」を押します。5 分ほど、長くて 48 時間で「確認済み」。→ [反映を待つ・うまくいかないとき](../../email-and-automation/email-domain-connection.md#not-verified)

## Cloudflare の公式の説明（英語）

* [Create a zone apex record](https://developers.cloudflare.com/dns/manage-dns-records/how-to/create-zone-apex/)
* [Proxy status](https://developers.cloudflare.com/dns/proxy-status/)

---

<!-- cta:opusbooster -->
{% hint style="success" %}
**自分の場合はどう使えばいいか**

[OpusBoosterの機能全体](https://opusbooster.com/features)を見る。設計から相談したい方は[15分の無料相談](https://opusbooster.com/consultation)、まず触ってみたい方は[14日間の無料トライアル](https://opusbooster.com/register)（クレジットカード不要）から。
{% endhint %}
