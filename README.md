<p><H3>�T�ԃX�P�W���[�����\��RDA5807 FM DSP���W�I</H3></p>
<p>
�\�ߐݒ肵���T�ԃX�P�W���[���Ɋ�Â��Ĕԑg�𒮂����Ƃ��ł���FM���W�I�𐻍삵���̂ŏЉ��B<br>
���p����RDA5807FP�́ARDA�}�C�N������FM�Ή���DSP���W�IIC�ł���BSOP16�s���̃p�b�P�[�W�ŁA<br><a href="https://www.aitendo.com/product/4797">�����i�f�[�^�V�[�g�̎Q�ƃ����N����j</a>�ɍw���ł��A�g�p���i�����Ȃ��čςނ̂Ŏg���Ղ��B<br>
I2C�C���^�[�t�F�[�X�ŃR���g���[�����邪�A�����ł́A�ڕW�̋@�\���������邽�߂ɁAWiFi�@�\�𓋍ڂ���<br>Seeed Studio XIAO ESP32C3�Ƒg�ݍ��킹���B<br>
XIAO ESP32C3�ł́AClock�̐ݒ��NTP�𗘗p���A������Web�T�[�o�[�@�\�ŏT�ԃX�P�W���[���̐ݒ���s���Ă���B<br>
�J����Arduino IDE 2.1�ōs�����B<br>

�g�p����RDA5807�p�̃��C�u�����́A<a href="https://github.com/pu2clr/RDA5807">������ipu2clr at GitHub�j</a>�ɂ���B��H�}�����f�ڂ���Ă���̂ŎQ�l�ɂ���Ɨǂ��B<br>�Ȃ��AArduino IDE�̃��C�u�����Ǘ�������C���X�g�[���\�ł���B<br>
RDA5807FP�͓d��3.3V�œ��삵�A�K�v�ȓd����20mA���x�Ȃ̂ŁAXIAO ESP32C3�i3V3�[�q�j���狟���ł���i5V�͕s�j�B<br>
</p>

<p><strong>�@�\</strong><br>
 �E�T�ԃX�P�W���[����ݒ�ł���B�j�����ƂɁA�ԑg�̊J�n���ԁA�ԑg�̒����A���W�I�ǁA���ʁA�ԑg�I����ON/OFF��ݒ肷��B
 �E�����͋N������NTP����擾��AXIAO ESP32C3�̓����N���b�N�ɐݒ肷��B
 �E�T�ԃX�P�W���[���̐ݒ�́APC�A�X�}�z���̃u���E�U����XIAO ESP32C3�ɃA�N�Z�X���čs���B
 �E���l�ɁA���W�I�ǂ̑I�ǁA���ʂ̕ύX�A���W�I��ON/OFF�́A�u���E�U����s�����Ƃ��ł���B
 �E�T�ԃX�P�W���[���̐ݒ�ɂ��A�ڊo�܂��@�\�A�X���[�v�@�\���\�ł���B
 �EOLED�\�����u�ɁA���t�A�j���A�����A���ʁA���W�I��ON/OFF�A��M���g����\������B
 �EXIAO ESP32C3�̓���̃s���Ƀ^�N�g�X�C�b�`��ڑ�����΁A�I�ǁA���ʁA���W�I��ON/OFF���\�ł���B
 �E��M���g���͈̔͂́A76�|108MHz�ŁA���C�hFM�Ή��ł���B
 �E�o�͂̓I�[�f�B�I�W���b�N�o�R�ŏ����a�̃X�s�[�J�[�i�X�e���I�j��ڑ�����B
</p>
<p><strong>H/W�\��</strong><br>
 �ESeeeduino XIAO ESP32C3 - �R���g���[��<br>
 �EI2C�ڑ�&nbsp; RDA5807FP<br>
 �EI2C�ڑ�&nbsp; SSD1306 64x32 OLED�\�����u<br>
 �EXtal���U��i32768Hz�j�A�R���f���T�ށA�I�[�f�B�I�W���b�N�A�z����<br>
</p>
<p>
<img src="./RDA5807_XIAO_PAD_1.jpg" width="360" height="440"><br>
�ėp��Ɏ����B��O��XIAO ESP32C�A����RDA5807FP�B
</p>
<p><strong>�ڑ�</strong><br>
�e�R���|�[�l���g�̐ڑ��͈ȉ��̒ʂ�B<br>
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
<td>�^�N�g�X�C�b�`</td><td>XIAO</td>
</tr>
<tr>
<td>����</td><td>GPIO2</td>
<tr>
<tr>
<td>�I��</td><td>GPIO3</td>
<tr>
<tr>
<td>PON/POFF</td><td>GPIO4</td>
<tr>
</table>
</p>
</p>
<p>
I2C�̃A�h���X
<table> 
<tr>
<td>RDA5807FP</td><td>0x10&nbsp;or&nbsp;0x11&nbsp;���C�u�����Ŋ���</td>
</tr>
<tr>
<td>OLED</td><td>0x3C&nbsp;����</td>
</tr>
</table>
</p>
<p><strong>�C���X�g�[��</strong><br>
<ol>
<li>�R�[�h���AZIP�`���Ń_�E�����[�h</li>
<li>ArduinoIDE�ɂ����āA���C�u�����}�l�[�W������ȉ����������ăC���X�g�[������</li>
 <ul>
  <li>Adafruit_BusIO</li>
  <li>Adafruit_GFX</li>
  <li>Adafruit_SSD1306</li>
 </ul>
<li>�ǉ��̃��C�u�������AZIP�`���Ń_�E�����[�h�A���C�u�����}�l�[�W������C���X�g�[������</li>
 <ul>
  <li>RDA5807</li>
  <li>TimeLib&nbsp;:&nbsp; https://github.com/PaulStoffregen/Time</li>
 </ul>
<li>ArduinoIDE����xiao_esp32c3_wifi_clock_radio_RDA5807.ino���J��</li>
<li>�u���؁E�R���p�C���v�ɐ���������A��U�A�u���O��t���ĕۑ��v���s��</li>
</ol>
</p>
<p><strong>�T�ԃX�P�W���[���̐ݒ���@�i�u���E�U��ʁj</strong><br>
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
<p><strong>�኱�̉��</strong><br>
�E��H�}�̓f�[�^�V�[�g���Q�Ƃ̂��ƁBLOUT�AROUT�̃R���f���T��100�|200��F���x��ڑ�����Ɖ������ǂ��Ȃ�B�Ȃ��A��H�}�ɂ���C���_�N�^���X�n�̕��i�͖����Ă����삷��B<br>
�EstnFreq[]�Ɏ�M��������ǂ̎��g�����w�肷��B�Ⴆ��80.4MHz�̏ꍇ�A8040�Ǝw�肷��B�Ȃ��AstnName[]�̓R�����g�ł���A�\���ɂ͎g���Ă��Ȃ��B<br>
�EMCP23107�̊��Keypad�Ԃ�8�{�̐��Őڑ�����K�v������BMCP23107�͓d�����x�������킹�邽�߁A3.3V�œ��삳���Ă���B<br>
<p>
<img src="./RDA5807_XIAO_PAD_2.jpg" width="360" height="480"><br>
</p>
</p>
<p><strong>���ӎ���</strong><br>
�E���p�̍ۂ́A���ȐӔC�ł��y���݂��������B<br>
</p>
