---
description: LINE公式アカウントを接続するために、7つの手順を順番に進める方法です。
---

# 初期設定 — LINE接続ウィザード

## これは何のための機能？

「**LINE接続セットアップ**」は、案内に沿ってLINE公式アカウントとの接続を設定する画面です。途中で止まった場合も「**セットアップの続きから再開する**」から続けられます。画面の「**セットアップの進み具合**」では、各手順が「**済み**」「**いまここ**」「**これから**」のどれかで表示されます。

<figure><img src="../../.gitbook/assets/line-setup-wizard-progress.png" alt=""><figcaption>いま進めている手順と、次の手順を確認します</figcaption></figure>

## 7つの手順を進める

### 1. LINE公式アカウントの確認

「**LINE公式アカウントの確認**」で「**持っている**」または「**持っていない**」を選びます。持っていない場合は「**LINE公式アカウントの開設手順を見る**」を開きます。新しいアカウントは、LINE Developers ConsoleではなくLINE公式アカウントマネージャーから作成してください。

### 2. Messaging APIの有効化

LINE公式アカウントマネージャーで「**Messaging APIを利用する**」を有効にします。画面の「**LINE公式アカウントマネージャーを開く（別タブ）**」から移動し、完了したら「**次へ**」を押します。

<figure><img src="../../.gitbook/assets/line-setup-messaging-api.png" alt=""><figcaption>LINE公式アカウントマネージャーでの操作を見ながら進めます</figcaption></figure>

### 3. 認証情報の入力

LINE Developers Consoleから認証情報を取得して入力し、「**保存して接続確認へ**」を押します。保存したシークレットは再表示できません。入力を保存せずに離れると、シークレットとトークンは後から見返せないため、入れ直しになります。

<figure><img src="../../.gitbook/assets/line-setup-credentials.png" alt=""><figcaption>LINE Developers Consoleで確認した情報を入力します</figcaption></figure>

{% hint style="warning" %}
**接続を入れ替えるとき:** 「**いまの接続を置き換えます**」と表示されたら、入力したチャネルで動くようになります。別のチャネルの情報を入れると、いまの接続は使われなくなります。友だちへの送信はこの操作では起きません。
{% endhint %}

### 5. Webhook設定

「**Webhook設定**」で「**Webhook を登録して疎通を確認**」を押します。LINE Developers Consoleの「**Webhookの利用**」をONにしてから、必要に応じて「**Webhook 疎通を確認**」を押してください。設定が済むまでは次へ進めません。

<figure><img src="../../.gitbook/assets/line-setup-webhook.png" alt=""><figcaption>Webhookの登録と疎通確認を完了してから次へ進みます</figcaption></figure>

### 6. テスト送受信

「**テスト送受信**」では、自分のスマホで友だち追加し、メッセージの受信を確認します。「**友だち追加URL**」を保存し、QRコードで友だち追加します。スマホから短いメッセージを1通送り、「**トーク受信箱を開く**」で届いたかを見て、「**テスト完了（受信を確認した）**」を押します。

<figure><img src="../../.gitbook/assets/line-setup-test-message.png" alt=""><figcaption>自分のスマホから送ったメッセージが受信箱に届くか確認します</figcaption></figure>

### 7. セットアップ結果

最後に「**セットアップ結果**」で「**セットアップ完了**」を確認します。「**LINEチャネル設定へ移動**」や、次に進む場所を開けます。

<figure><img src="../../.gitbook/assets/line-setup-complete.png" alt=""><figcaption>接続後にできることを確認します</figcaption></figure>

## よくある質問・つまずき

### 保存した認証情報を確認したいです

保存したシークレットは再表示できません。入力内容を手元で安全に管理してください。

### Webhookの手順で次へ進めません

先に「**Webhook を登録して疎通を確認**」を押し、LINE Developers Consoleで「**Webhookの利用**」をONにしてください。
