---
description: Cloudflare で管理しているドメインに、メール送信用の2つのレコード（TXT と CNAME）を追加する手順です。「プロキシ」をオフにするのがポイントです。
---

# Cloudflare でレコードを追加する

## この手順を使う人

ドメインの**ネームサーバーが Cloudflare のもの**（`〜.ns.cloudflare.com`）になっている方です。→ [どこで管理されているか調べる](where-is-my-domain.md)

## 用意するもの

OpusBooster の「**ドメインと送信者**」画面に表示された2つのレコード。→ [メールドメインの接続](../email-domain-connection.md)

## 手順

1. [Cloudflare ダッシュボード](https://dash.cloudflare.com/) にログインし、対象のドメインを押します。
2. 左のメニューの「**DNS**」→「**Records**（レコード）」を押します。
3. 「**Add record**（レコードを追加）」を押し、**1つ目（TXT）**を入れて「**Save**（保存）」。
   * **Type**: `TXT`
   * **Name**: `@`
   * **Content**: OpusBooster に表示された長い文字列を、コピーボタンで貼る
4. もう一度「**Add record**」を押し、**2つ目（CNAME）**を入れます。
   * **Type**: `CNAME`
   * **Name**: `def._domainkey`（あとの「.あなたのドメイン」は自動で付きます）
   * **Target**: `client._domainkey.app-sources.com`
   * **Proxy status**: **必ずオフ（灰色の雲、「DNS only」）にします**
   * 「**Save**」

<!-- 📷 スクショ: 手順3〜4 Add record のフォーム。Proxy status の雲アイコンが灰色になっている状態を赤枠で -->

{% hint style="danger" %}
**CNAME の「Proxy status」はオフ（灰色の雲 / DNS only）にしてください。**
オレンジ色の雲（Proxied）のままだと、メールの署名の確認ができず、いつまでも「確認済み」になりません。Cloudflare の公式説明にも、メール認証用（DKIM）のレコードは DNS only にするよう書かれています。TXT はもともとプロキシされないので、そのままで大丈夫です。
{% endhint %}

## 追加したあと

OpusBooster の「ドメインと送信者」に戻り、「**ステータスを更新**」を押します。Cloudflare は**5分ほど**で反映されることが多いです。長くて 48 時間で「**確認済み**」になります。→ [反映を待つ・うまくいかないとき](../email-domain-connection.md#not-verified)

## Cloudflare の公式の説明（英語）

* [Create a zone apex record](https://developers.cloudflare.com/dns/manage-dns-records/how-to/create-zone-apex/)
* [Proxy status](https://developers.cloudflare.com/dns/proxy-status/)

---

<!-- cta:opusbooster -->
{% hint style="success" %}
**自分の場合はどう使えばいいか**

[OpusBoosterの機能全体](https://opusbooster.com/features)を見る。設計から相談したい方は[15分の無料相談](https://opusbooster.com/consultation)、まず触ってみたい方は[14日間の無料トライアル](https://opusbooster.com/register)（クレジットカード不要）から。
{% endhint %}
