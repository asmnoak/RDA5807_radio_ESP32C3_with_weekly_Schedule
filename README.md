<p><H3>週間スケジュールが可能なRDA5807 FM DSPラジオ</H3></p>
<p>
予め設定した週間スケジュールに基づいて番組を聴くことができるFMラジオを製作したので紹介する。<br>
利用したRDA5807FPは、RDAマイクロ製のFM対応のDSPラジオICである。<a href="https://www.aitendo.com/product/4797">安価（データシートの参照リンクあり）</a>に購入でき<br>
SOP16ピンのパッケージで、かつ使用部品が少なくて済むので使い易い。<br>
I2Cインターフェースでコントロールするが、ここでは、目標の機能を実現するために、WiFi機能を搭載した<br>
<a href="https://www.switch-science.com/products/8348">Seeed Studio XIAO ESP32C3</a>と組み合わせた。<br>
XIAO ESP32C3では、Clockの設定にNTPを利用し、内蔵のWebサーバー機能で週間スケジュールの設定を行っている。<br>
開発はArduino IDE 2.1で行った。<br>

使用したRDA5807用のライブラリは、<a href="https://github.com/pu2clr/RDA5807">こちら（pu2clr at GitHub）</a>にある。<a href="https://pu2clr.github.io/RDA5807/#schematic">回路図等</a>も掲載されているので参考にすると良い。<br>
なお、Arduino IDEのライブラリ管理からもインストール可能である。<br>
RDA5807FPは電圧3.3Vで動作し、必要な電流は20mA程度なので、XIAO ESP32C3（3V3端子）から供給できる（5Vは不可）。<br>
</p>

<p><strong>機能</strong><br>
 ・週間スケジュールを設定できる。曜日ごとに、番組の開始時間、番組の長さ、ラジオ局、音量、番組終了後ON/OFFを設定する。<br>
 ・時刻は起動時にNTPから取得し、XIAO ESP32C3の内部クロックに設定する。<br>
 ・週間スケジュールの設定は、PC、スマホ等のブラウザからXIAO ESP32C3にアクセスして行う。<br>
 ・同様に、ラジオ局の選局、音量の変更、ラジオのON/OFFは、ブラウザから行うことができる。<br>
 ・週間スケジュールの設定により、目覚まし機能、スリープ機能が可能である。<br>
 ・OLED表示装置に、日付、曜日、時刻、音量、ラジオのON/OFF、受信周波数を表示する。<br>
 ・XIAO ESP32C3の特定のピンにタクトスイッチを接続すれば、選局、音量、ラジオのON/OFFが可能である。<br>
 ・受信周波数の範囲は、76－108MHzで、ワイドFM対応である。<br>
 ・出力はオーディオジャック経由で小口径のスピーカー（ステレオ）を接続する。<br>
</p>
<p><strong>H/W構成</strong><br>
 ・Seeed Studio XIAO ESP32C3 - コントローラ<br>
 ・I2C接続&nbsp; RDA5807FP<br>
 ・I2C接続&nbsp; SSD1306 64x32 OLED表示装置<br>
 ・Xtal発振器（32768Hz）、コンデンサ類、オーディオジャック、配線類<br>
</p>
<p>
<img src="https://github.com/asmnoak/RDA5807_radio_ESP32C3_with_weekly_Schedule/blob/main/RDA5807_XIAO_ESP32C3_1.JPG" width="360" height="440"><br>
汎用基板に実装。手前がXIAO ESP32C、奥がRDA5807FP。
</p>
<p><strong>接続</strong><br>
各コンポーネントの接続は以下の通り。<br>
<p>
<table> 
<tr>
<td>I2C&nbsp;</td><td>XIAO</td>
</tr>
<tr>
<td>SCK</td><td>D5</td>
</tr>
<tr>
<td>SDA</td><td>D4</td>
</tr>
</table>
</p>
<p>
<table> 
<tr>
<td>タクトスイッチ</td><td>XIAO</td>
</tr>
<tr>
<td>音量</td><td>GPIO2</td>
</tr>
<tr>
<td>選局</td><td>GPIO3</td>
</tr>
<tr>
<td>PON/POFF</td><td>GPIO4</td>
</tr>
</table>
</p>
</p>
<p>
I2Cのアドレス
<table> 
<tr>
<td>RDA5807FP</td><td>0x10&nbsp;or&nbsp;0x11&nbsp;ライブラリで既定</td>
</tr>
<tr>
<td>OLED</td><td>0x3C&nbsp;既定</td>
</tr>
</table>
</p>
<p><strong>週間スケジュールの設定方法</strong><br>
ブラウザから、"http://192.168.aa.bb" のように指定（bbの部分は起動時にOLED表示装置の3行目に表示）してXIAO ESP32C3にアクセスすると、以下の画面が表示される。<br>
中央の表には、各曜日ごとの聴取予定が時刻順に表示（1エントリの項目は、番組開始時刻、ラジオ局、放送時間（分）、音量、番組終了後に電源OFF（1の時）である）されている。<br>
各曜日の聴取予定を変更する場合は、変更する曜日のラジオボタンをクリックする。現在の内容が、一番上の入力領域に表示されるので、それを編集する。<br>
編集後、"submit"ボタンをクリックすると、変更内容が保存される。<br>
変更内容に形式上の間違いがある場合は、エラーが表示され、保存されない。なお、各番組の開始時刻と終了時刻は分単位で重ならないように指定すること。<br>
上記の設定項目中のラジオ局については、スケッチ中のstnFreq[]配列（周波数）のインデックスを指定する。<br>
以下の画面の"Station List"には、スケッチ中のstnName[]配列 （局名）が表示されるので対応させておく必要がある。<br>
下部の"Control Functions"には、音量、選局、電源ON/OFFの各操作ボタンがある。
<p>
<img src="https://github.com/asmnoak/RDA5807_radio_ESP32C3_with_weekly_Schedule/blob/main/weekly_schedule.jpg" width="890" height="560"><br>
</p>

</p>
<p><strong>インストール</strong><br>
<ol>
<li>コードを、ZIP形式でダウンロード</li>
<li>ArduinoIDEにおいて、ライブラリマネージャから以下を検索してインストールする</li>
 <ul>
  <li>Adafruit_BusIO</li>
  <li>Adafruit_GFX</li>
  <li>Adafruit_SSD1306</li>
  <li>RDA5807</li>
 </ul>
<li>追加のライブラリを、ZIP形式でダウンロード、ライブラリマネージャからインストールする</li>
 <ul>
  <li>TimeLib&nbsp;:&nbsp; https://github.com/PaulStoffregen/Time</li>
 </ul>
<li>ArduinoIDEからxiao_esp32c3_wifi_clock_radio_RDA5807.inoを開く</li>
<li>「検証・コンパイル」に成功したら、一旦、「名前を付けて保存」を行う</li>
</ol>
</p>
<p><strong>若干の解説</strong><br>
・回路図はデータシートを参照のこと。LOUT、ROUTのコンデンサは100－200μF程度を接続すると音質が良くなる。なお、回路図にあるインダクタンス系の部品は無くても動作する。<br>
・指定できるWiFiステーションは、２ヶ所までで、夫々、SSIDとパスワードを設定する。<br>
・1日に指定できる番組の数は9までである（増やす場合は自己責任でお願いします）。同じラジオ局の番組を続けて聴く場合は、放送時間を合算して、1エントリで指定すればよい。<br>
&nbsp;&nbsp;なお深夜0時を跨いだ部分は、次の曜日に指定する。<br>
・stnFreq[]に受信する放送局の周波数を指定する。例えば80.4MHzの場合、8040と指定する。なお、stnName[]には対応する放送局名を指定する。これはブラウザに表示される。<br>
&nbsp;&nbsp;指定できる放送局は8までである（増やす場合は自己責任でお願いします）。<br>
<p>
<img src="https://github.com/asmnoak/RDA5807_radio_ESP32C3_with_weekly_Schedule/blob/main/RDA5807_XIAO_ESP32C3_2.JPG" width="280" height="200"><br>
</p>
</p>
<p><strong>注意事項</strong><br>
・動作を保証するものではありませんので、利用の際は、自己責任でお楽しみください。<br>
</p>
