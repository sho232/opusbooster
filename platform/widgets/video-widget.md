# 動画ウィジェット

動画をページに追加するのはとても簡単で、追加する方法は複数あります。まず、ビデオウィジェットアイコンに移動します。

![](https://1369750374-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FWQDl1MvGQxbiNyVOzW8v%2Fuploads%2FkA1GJqO0ngUpxAQQxp2W%2Fvideo%20widget.PNG?alt=media\&token=ac4cac1d-f1fd-4af0-acaf-af9efec321d5)

![](https://1369750374-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FWQDl1MvGQxbiNyVOzW8v%2Fuploads%2FY5vIkXogqqZw54BeFLbW%2Fvideo%20placeholder.PNG?alt=media\&token=3065ad7d-3d9a-48b3-86ac-a4d1cff1ed60)

埋め込み用のURLまたはカスタムコードを入力します。（例：youtubeから→共有→埋め込みコードをコピー）

動画を配置したら、スタイリングエレメントを編集することができます。

* ファイルマネージャー領域からサムネイル画像を追加する
* 動画の周囲に影をつける

また、動画のサイズを好みのコンテナ/カラムに変更することも可能です。

![](https://1369750374-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FWQDl1MvGQxbiNyVOzW8v%2Fuploads%2FXYiuiugoDCAFTcQ7vmTy%2Fvideo%20thumbnail.PNG?alt=media\&token=b48c9722-a380-4c1b-a473-b8d60de663c5)

### 動画を自動再生する方法

以下のコードを動画ウィジェットに埋め込むことによって、動画を自動再生させることが可能です。

#### 動画ファイルを直接指定する場合

```html
<video id="evergreen" width="100%" height="100%" oncontextmenu="return false;" webkit-playsinline="true" playsinline="true" autoplay muted>
    
    <source src="動画ファイルURL“ type="video/mp4">
               
</video>
	
	<div align="center">
	 	ボタンをクリックして音声のオンオフを切り替えてください:
     	<button class="btn-view-more"  onclick="disbleMute()" type="button">ON</button> 
     	<button class="btn-view-more" onclick="enableMute()" type="button">OFF</button>  
	</div>

    <script>
          var vid = document.getElementById("evergreen");
          function enableMute() {

              vid.muted = true;
          }
          function disbleMute() {

              vid.muted = false;
          }
    </script>

```

上記コード内の「動画ファイルURL」をご自身のものに置き換えてください。

#### &#x20;Vimeoにアップロードした動画を埋め込む場合

<pre class="language-html"><code class="lang-html">&#x3C;!-- Vimeoの動画を埋め込むiframe -->
&#x3C;iframe src="https://player.vimeo.com/video/<a data-footnote-ref href="#user-content-fn-1">VIDEO_ID</a>?background=1&#x26;autoplay=1&#x26;muted=1" width="640" height="360" frameborder="0" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen id="vimeoPlayer">&#x3C;/iframe>

&#x3C;!-- 音を出すボタン -->
&#x3C;button id="unmuteButton">音を出す&#x3C;/button>
&#x3C;!-- 音をミュートにするボタン -->
&#x3C;button id="muteButton">音をミュートにする&#x3C;/button>

&#x3C;script src="https://player.vimeo.com/api/player.js">&#x3C;/script>
&#x3C;script>
    var iframe = document.querySelector('#vimeoPlayer');
    var player = new Vimeo.Player(iframe);
    var muteButton = document.querySelector('#muteButton');
    var unmuteButton = document.querySelector('#unmuteButton');

    muteButton.addEventListener('click', function() {
        player.setVolume(0);
    });

    unmuteButton.addEventListener('click', function() {
        player.setVolume(1);
    });
&#x3C;/script>
</code></pre>

上記のコードの、VIDEO\_IDを、埋め込みたいVimeoの動画ID（共有ボタンで「リンクをカスタマイズ」する前のURLに含まれている数字の羅列です。）に置き換えてください。

{% hint style="info" %}
ブラウザで動画を自動再生するためには、音声をミュートにしておく必要があります。そのため、上記コードでは音声がミュートの状態で再生が始まる設定にしています。また、オートウェビナーとしての利用を考慮して、再生バーを非表示にした場合のために、音声のオンオフボタンを埋め込んでいます。（Vimeoでは、再生バーを非表示にすると音声コントロールも非表示になってしまうため。）
{% endhint %}

[^1]: ご自身のVImeo動画IDに置き換え
