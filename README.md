<p><H3>週間スケジュールが可能なRDA5807 FM DSPラジオ</H3></p>
<p>
予め設定した週間スケジュールに基づいて番組を聴くことができるFMラジオを製作したので紹介する。<br>
利用したRDA5807FPは、RDAマイクロ製のFM対応のDSPラジオICである。SOP16ピンのパッケージで、<br><a href="https://www.aitendo.com/product/4797">安価（データシートの参照リンクあり）</a>に購入でき、使用部品が少なくて済むので使い易い。<br>
I2Cインターフェースでコントロールするが、ここでは、目標の機能を実現するために、WiFi機能を搭載した<br>Seeed Studio XIAO ESP32C3と組み合わせた。<br>
XIAO ESP32C3では、Clockの設定にNTPを利用し、内蔵のWebサーバー機能で週間スケジュールの設定を行っている。<br>
開発はArduino IDE 2.1で行った。<br>

使用したRDA5807用のライブラリは、<a href="https://github.com/pu2clr/RDA5807">こちら（pu2clr at GitHub）</a>にある。回路図等も掲載されているので参考にすると良い。<br>なお、Arduino IDEのライブラリ管理からもインストール可能である。<br>
RDA5807FPは電圧3.3Vで動作し、必要な電流は20mA程度なので、XIAO ESP32C3（3V3端子）から供給できる（5Vは不可）。<br>
</p>

<p><strong>機能</strong><br>
 ・週間スケジュールを設定できる。曜日ごとに、番組の開始時間、番組の長さ、ラジオ局、音量、番組終了後ON/OFFを設定する。
 ・時刻は起動時にNTPから取得後、XIAO ESP32C3の内部クロックに設定する。
 ・週間スケジュールの設定は、PC、スマホ等のブラウザからXIAO ESP32C3にアクセスして行う。
 ・同様に、ラジオ局の選局、音量の変更、ラジオのON/OFFは、ブラウザから行うことができる。
 ・週間スケジュールの設定により、目覚まし機能、スリープ機能が可能である。
 ・OLED表示装置に、日付、曜日、時刻、音量、ラジオのON/OFF、受信周波数を表示する。
 ・XIAO ESP32C3の特定のピンにタクトスイッチを接続すれば、選局、音量、ラジオのON/OFFが可能である。
 ・受信周波数の範囲は、76－108MHzで、ワイドFM対応である。
 ・出力はオーディオジャック経由で小口径のスピーカー（ステレオ）を接続する。
</p>
<p><strong>H/W構成</strong><br>
 ・Seeeduino XIAO ESP32C3 - コントローラ<br>
 ・I2C接続&nbsp; RDA5807FP<br>
 ・I2C接続&nbsp; SSD1306 64x32 OLED表示装置<br>
 ・Xtal発振器（32768Hz）、コンデンサ類、オーディオジャック、配線類<br>
</p>
<p>
<img src="./RDA5807_XIAO_PAD_1.jpg" width="360" height="440"><br>
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
<tr>
<tr>
<td>SDA</td><td>D4</td>
<tr>
</table>
</p>
<p>
<table> 
<tr>
<td>タクトスイッチ</td><td>XIAO</td>
</tr>
<tr>
<td>音量</td><td>GPIO2</td>
<tr>
<tr>
<td>選局</td><td>GPIO3</td>
<tr>
<tr>
<td>PON/POFF</td><td>GPIO4</td>
<tr>
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
<p><strong>インストール</strong><br>
<ol>
<li>コードを、ZIP形式でダウンロード</li>
<li>ArduinoIDEにおいて、ライブラリマネージャから以下を検索してインストールする</li>
 <ul>
  <li>Adafruit_BusIO</li>
  <li>Adafruit_GFX</li>
  <li>Adafruit_SSD1306</li>
 </ul>
<li>追加のライブラリを、ZIP形式でダウンロード、ライブラリマネージャからインストールする</li>
 <ul>
  <li>RDA5807</li>
  <li>TimeLib&nbsp;:&nbsp; https://github.com/PaulStoffregen/Time</li>
 </ul>
<li>ArduinoIDEからxiao_esp32c3_wifi_clock_radio_RDA5807.inoを開く</li>
<li>「検証・コンパイル」に成功したら、一旦、「名前を付けて保存」を行う</li>
</ol>
</p>
<p><strong>週間スケジュールの設定方法（ブラウザ画面）</strong><br>
<p>Select a day of the week, change it, then submit.</p><form action="" method="post"><p><input type="text" id="daysced" name="daysced" size="120" value=""></p>
<p><input type="submit" value="submit" class="btn"></p></form>
<p>OK! Done.</p><p>Arguments of enrty: Start time(hour:min),Station(See below),Duration(min),Volume,Pweroff</p>
<p>Station List: 0=AirG,1=NW,2=NHK,3=STV,4=HBC,5=sanka,6=karos,7=nosut</p>
<script>let entity = [[['6:31',1,59,2,1],['9:00',6,59,1,0],['10:00',0,59,1,0],['11:00',3,119,1,0],['13:00',1,59,1,0],['14:00',0,59,1,0],['15:00',1,59,1,0],['19:00',3,119,1,0],['22:00',0,79,1,1]],[['6:29',4,59,1,1],['8:01',3,119,1,0],['10:04',6,59,1,0],['12:00',2,119,1,0],['14:00',1,119,1,0],['17:00',1,119,1,0],['19:00',1,29,2,0],['19:30',0,89,1,0],['23:30',0,29,1,1]],[['6:30',4,59,1,1],['8:00',3,119,1,0],['12:00',2,89,1,0],['14:00',1,119,1,0],['0:00',0,0,0,0],['0:00',0,0,0,0],['17:00',1,119,1,0],['19:00',3,179,1,0],['23:30',0,29,1,1]],[['6:30',4,59,1,1],['8:00',3,119,1,0],['12:00',2,89,1,0],['14:00',1,119,1,0],['0:00',0,0,0,0],['0:00',0,0,0,0],['17:00',1,119,1,0],['19:00',3,119,1,0],['23:30',0,29,1,1]],[['6:30',4,59,1,1],['8:00',3,119,1,0],['10:04',6,59,1,0],['12:00',2,119,1,0],['14:00',1,119,1,0],['16:00',1,59,1,0],['18:00',1,119,1,0],['19:00',3,119,1,0],['22:00',3,59,1,1]],[['6:30',4,59,1,1],['8:00',3,119,1,0],['11:00',0,59,1,0],['12:00',2,119,1,0],['14:00',6,119,1,0],['16:00',1,59,1,0],['18:00',1,59,1,0],['19:00',3,119,1,0],['22:00',3,59,1,1]],[['6:30',0,29,1,0],['7:00',2,119,1,0],['9:00',2,110,1,0],['12:00',2,119,1,0],['14:00',2,119,1,0],['16:00',2,119,1,0],['18:00',4,59,1,0],['19:00',3,119,1,0],['21:00',1,179,1,1]]];let week = ["Sun","Mon","Tue","Wed","Thu","Fri","Sat"];document.write('<table id="tbl" border="1" style="border-collapse: collapse">');for (let i = 0; i < 7; i++){let wstr ='';wstr ='<tr>' + '<td>' + '<input type="radio" name="week" value="" onclick="setinput(' + i + ')">' + '</td>' + '<td>' + week[i] + '</td>';document.write(wstr);for (let j = 0; j < 9; j++){document.write('<td>');document.write(entity[i][j]);document.write('</td>');}document.write('</tr>');}document.write('</table>');function setinput(trnum) {var input = document.getElementById("daysced");var table = document.getElementById("tbl");var cells = table.rows[trnum].cells;let istr = '';for (let j = 1; j <= 10; j++){istr = istr + cells[j].innerText + ';';}input.value = istr;}</script>
<style>.lay_i input:first-of-type{margin-right: 20px;}</style><style>.btn {width: 300px; padding: 10px; box-sizing: border-box; border: 1px solid #68779a; background: #cbe8fa; cursor: pointer;}</style>
<p><form action="" method="post"><p>Control Functions</p>
<p><div class="lay_i"><input type="submit" name="vup"  value="volume up" class="btn"><input type="submit" name="vdown" value="volume down" class="btn"></div></p>
<p><div class="lay_i"><input type="submit" name="stnup"  value="station up" class="btn"><input type="submit" name="stndown" value="station down" class="btn"></div></p>
<p><div class="lay_i"><input type="submit" name="pwonoff"  value="pwr_on_off" class="btn"></div></p></form></p>
</p>
<p><strong>若干の解説</strong><br>
・回路図はデータシートを参照のこと。LOUT、ROUTのコンデンサは100－200μF程度を接続すると音質が良くなる。なお、回路図にあるインダクタンス系の部品は無くても動作する。<br>
・stnFreq[]に受信する放送局の周波数を指定する。例えば80.4MHzの場合、8040と指定する。なお、stnName[]はコメントであり、表示には使っていない。<br>
・MCP23107の基板とKeypad間は8本の線で接続する必要がある。MCP23107は電圧レベルを合わせるため、3.3Vで動作させている。<br>
<p>
<img src="./RDA5807_XIAO_PAD_2.jpg" width="360" height="480"><br>
</p>
</p>
<p><strong>注意事項</strong><br>
・利用の際は、自己責任でお楽しみください。<br>
</p>
