---
description: 自分のドメインがどの会社で管理されているかを調べる方法。「買った会社」と「運用している会社」が違うときの見分け方も説明します。サイト用・メール用どちらの設定でも、最初にここを確かめます。
---

# ドメインがどこで管理されているか調べる

サイトを自分のドメインで表示するときも、メールを自分のドメインから送るときも、レコードは**ドメインを「運用している」会社の画面**に貼ります。多くの方は「買った会社 = 運用している会社」ですが、**買った会社と運用している会社が違う**ことがあります（例: お名前.com で買って、エックスサーバーで使っている）。この記事で、自分がどちらなのかを確かめてください。

{% hint style="success" %}
**いちばん早い方法: ドメイン名を入れるだけで調べる**
[ドメインの管理会社チェッカー](https://opusbooster.com/domain-check)に自分のドメイン（例: `piano-school.com`）を入れると、**レコードを貼る先の会社**と、その会社の手順ページをそのまま案内します。ログイン不要で、ドメインの設定を変えることはありません。うまく判定できなかったときだけ、下の方法 1〜3 に進んでください。
{% endhint %}

## 方法 1: 買ったときのメールを探す（いちばん簡単）

メールの受信箱で、次の言葉を検索してください。

* 「**ドメイン**」「**更新**」「**登録完了**」
* 会社名: 「**お名前.com**」「**エックスサーバー**」「**ムームードメイン**」「**さくら**」「**バリュードメイン**」「**Google Domains**」「**Squarespace**」「**Cloudflare**」

毎年の「更新のお知らせ」が来ている会社が、ドメインを買った会社です。

## 方法 2: ネームサーバーで「運用している会社」を確かめる

買った会社が分かっても、**運用している会社が別**のことがあります。それを決めているのが「**ネームサーバー**」という設定です。ネームサーバーが向いている会社の画面に貼らないと、レコードは効きません。

ネームサーバーは、次の無料ページで誰でも調べられます。

* 「.com」「.net」などのドメイン: [ICANN Lookup](https://lookup.icann.org/) — ドメインを入れて検索し、「**Name Servers**」の欄を見ます
* 「.jp」のドメイン: [JPRS WHOIS](https://whois.jprs.jp/) — 「**Name Server**」の欄を見ます

<!-- 📷 スクショ: ICANN Lookup の結果画面。Name Servers の欄を赤枠で -->

表示された名前に、次の文字が入っていれば、その会社の画面に貼ります。

| ネームサーバーに入っている文字 | 運用している会社 | 手順 |
|---|---|---|
| `dnsv.jp` | お名前.com | [手順へ](onamae.md) |
| `xserver.jp` / `xdomain` | エックスサーバー / Xserverドメイン | [手順へ](xserver.md) |
| `muumuu-domain.com` | ムームードメイン | [手順へ](muumuu.md) |
| `dns.ne.jp` | さくらインターネット | [手順へ](sakura.md) |
| `value-domain.com` | バリュードメイン | [手順へ](value-domain.md) |
| `cloudflare.com` | Cloudflare | [手順へ](cloudflare.md) |
| `googledomains.com` / `squarespacedns.com` | Squarespace（旧 Google Domains） | [手順へ](squarespace.md) |
| `web-repository.com` | OpusBooster のネームサーバー | 下の注意を読んでください |

{% hint style="warning" %}
**ネームサーバーが OpusBooster（`web-repository.com`）になっている場合**
ネームサーバーごと OpusBooster に向けている状態です。この場合、レコードを貼る場所は**ドメインを買った会社ではなく、OpusBooster 側**になります。サポートにご相談ください（15分の無料相談でも対応します）。
{% endhint %}

## 方法 3: Google Workspace（Gmail のビジネス版）と一緒にドメインを買った方

Google Workspace の申し込み時に買ったドメインは、**Squarespace** で管理されていることがほとんどです（以前の Google Domains が Squarespace に移りました）。Google 管理コンソールの「**アカウント → ドメイン → ドメインを管理 → 詳細を表示**」で、登録先の会社名を確かめられます。→ [Squarespace の手順へ](squarespace.md)

## どうしても分からないとき

ドメインの会社が分からなくても、サイトは OpusBooster のアドレスのまま公開できますし、LINE連携の配信も動きます。急がず、[15分の無料相談](https://opusbooster.com/consultation)で画面を一緒に見ながら進めましょう。

---

<!-- cta:opusbooster -->
{% hint style="success" %}
**自分の場合はどう使えばいいか**

[OpusBoosterの機能全体](https://opusbooster.com/features)を見る。設計から相談したい方は[15分の無料相談](https://opusbooster.com/consultation)、まず触ってみたい方は[14日間の無料トライアル](https://opusbooster.com/register)（クレジットカード不要）から。
{% endhint %}
