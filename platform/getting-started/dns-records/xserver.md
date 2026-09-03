---
description: エックスサーバー（レンタルサーバー）または Xserverドメインで管理しているドメインに、メール送信用の2つのレコード（TXT と CNAME）を追加する手順です。
---

# エックスサーバーでレコードを追加する

## この手順を使う人

ドメインの**ネームサーバーがエックスサーバーのもの**（`ns1.xserver.jp` など）になっている方です。お名前.com などで買ったドメインでも、エックスサーバーで運用していれば**この手順**です。→ [どこで管理されているか調べる](where-is-my-domain.md)

エックスサーバーには画面が2つあります。どちらか当てはまるほうに進んでください。

* **A. サーバーパネル**（レンタルサーバーを契約していて、そこでサイトを動かしている方。多くはこちら）
* **B. Xserverアカウント**（ドメインだけを Xserverドメイン で買い、サーバーは別の方）

## 用意するもの

OpusBooster の「**ドメインと送信者**」画面に表示された2つのレコード。→ [メールドメインの接続](../email-domain-connection.md)

## A. サーバーパネルで追加する

1. [サーバーパネル](https://secure.xserver.ne.jp/xapanel/login/xserver/server/) にログインします。
2. 「**ドメイン**」の中の「**DNSレコード設定**」を押します。
3. 対象のドメインの「**選択する**」を押します。
4. 「**DNSレコード設定を追加**」（古い画面では「DNSレコード追加」）のタブを開きます。
5. **1つ目（TXT）**を入れて「**確認画面へ進む**」→「**追加する**」。
   * **ホスト名**: 空欄のまま
   * **種別**: `TXT`
   * **内容**: OpusBooster に表示された長い文字列を、コピーボタンで貼る
6. **2つ目（CNAME）**を同じように入れます。
   * **ホスト名**: `def._domainkey`（あとの「.あなたのドメイン」は自動で付きます）
   * **種別**: `CNAME`
   * **内容**: `client._domainkey.app-sources.com`

<!-- 📷 スクショ: A-2 サーバーパネルの「DNSレコード設定」の位置 -->
<!-- 📷 スクショ: A-5〜6 追加タブに TXT / CNAME を入れた状態 -->

## B. Xserverアカウントで追加する

1. [Xserverアカウント](https://secure.xserver.ne.jp/xapanel/login/xserver/) にログインします。
2. ドメイン一覧で、対象ドメインの右端のメニューから「**DNSレコード設定**」を押します。
3. 「**DNSレコード設定の追加**」を押し、A の手順 5〜6 と同じ内容を入れて「**確認画面へ進む**」→「**設定を追加する**」。

<!-- 📷 スクショ: B-2 ドメイン一覧のメニュー -->

{% hint style="warning" %}
**CNAME は、同じホスト名に他のレコードがあると効きません。**
`def._domainkey` に別のレコードがすでにある場合（ほとんどありません）は、先にそれを消してから CNAME を追加してください。エックスサーバーの公式マニュアルにも「CNAMEレコードは必ず他のレコード設定とは異なるホスト名を入力してください」とあります。
{% endhint %}

## 追加したあと

OpusBooster の「ドメインと送信者」に戻り、「**ステータスを更新**」を押します。通常は 10〜15 分、長くて 48 時間で「**確認済み**」になります。→ [反映を待つ・うまくいかないとき](../email-domain-connection.md#not-verified)

## エックスサーバーの公式の説明

* [DNSレコードの編集（サーバーパネル）](https://www.xserver.ne.jp/manual/man_domain_dns_setting.php)
* [DNSレコードの編集（Xserverドメイン）](https://www.xdomain.ne.jp/manual/man_domain_dns_setting.php)

---

<!-- cta:opusbooster -->
{% hint style="success" %}
**自分の場合はどう使えばいいか**

[OpusBoosterの機能全体](https://opusbooster.com/features)を見る。設計から相談したい方は[15分の無料相談](https://opusbooster.com/consultation)、まず触ってみたい方は[14日間の無料トライアル](https://opusbooster.com/register)（クレジットカード不要）から。
{% endhint %}
