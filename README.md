<p><H3>�T�ԃX�P�W���[�����\��RDA5807 FM DSP���W�I</H3></p>
<p>
�\�ߐݒ肵���T�ԃX�P�W���[���Ɋ�Â��Ĕԑg�𒮂����Ƃ��ł���FM���W�I�𐻍삵���̂ŏЉ��B<br>
���p����RDA5807FP�́ARDA�}�C�N������FM�Ή���DSP���W�IIC�ł���B<a href="https://www.aitendo.com/product/4797">�����i�f�[�^�V�[�g�̎Q�ƃ����N����j</a>�ɍw���ł�<br>
SOP16�s���̃p�b�P�[�W�ŁA���g�p���i�����Ȃ��čςނ̂Ŏg���Ղ��B<br>
I2C�C���^�[�t�F�[�X�ŃR���g���[�����邪�A�����ł́A�ڕW�̋@�\���������邽�߂ɁAWiFi�@�\�𓋍ڂ���<br>
<a href="https://www.switch-science.com/products/8348">Seeed Studio XIAO ESP32C3</a>�Ƒg�ݍ��킹���B<br>
XIAO ESP32C3�ł́AClock�̐ݒ��NTP�𗘗p���A������Web�T�[�o�[�@�\�ŏT�ԃX�P�W���[���̐ݒ���s���Ă���B<br>
�J����Arduino IDE 2.1�ōs�����B<br>

�g�p����RDA5807�p�̃��C�u�����́A<a href="https://github.com/pu2clr/RDA5807">������ipu2clr at GitHub�j</a>�ɂ���B<a href="https://pu2clr.github.io/RDA5807/#schematic">��H�}��</a>���f�ڂ���Ă���̂ŎQ�l�ɂ���Ɨǂ��B<br>
�Ȃ��AArduino IDE�̃��C�u�����Ǘ�������C���X�g�[���\�ł���B<br>
RDA5807FP�͓d��3.3V�œ��삵�A�K�v�ȓd����20mA���x�Ȃ̂ŁAXIAO ESP32C3�i3V3�[�q�j���狟���ł���i5V�͕s�j�B<br>
</p>

<p><strong>�@�\</strong><br>
 �E�T�ԃX�P�W���[����ݒ�ł���B�j�����ƂɁA�ԑg�̊J�n���ԁA�ԑg�̒����A���W�I�ǁA���ʁA�ԑg�I����ON/OFF��ݒ肷��B<br>
 �E�����͋N������NTP����擾���AXIAO ESP32C3�̓����N���b�N�ɐݒ肷��B<br>
 �E�T�ԃX�P�W���[���̐ݒ�́APC�A�X�}�z���̃u���E�U����XIAO ESP32C3�ɃA�N�Z�X���čs���B<br>
 �E���l�ɁA���W�I�ǂ̑I�ǁA���ʂ̕ύX�A���W�I��ON/OFF�́A�u���E�U����s�����Ƃ��ł���B<br>
 �E�T�ԃX�P�W���[���̐ݒ�ɂ��A�ڊo�܂��@�\�A�X���[�v�@�\���\�ł���B<br>
 �EOLED�\�����u�ɁA���t�A�j���A�����A���ʁA���W�I��ON/OFF�A��M���g����\������B<br>
 �EXIAO ESP32C3�̓���̃s���Ƀ^�N�g�X�C�b�`��ڑ�����΁A�I�ǁA���ʁA���W�I��ON/OFF���\�ł���B<br>
 �E��M���g���͈̔͂́A76�|108MHz�ŁA���C�hFM�Ή��ł���B<br>
 �E�o�͂̓I�[�f�B�I�W���b�N�o�R�ŏ����a�̃X�s�[�J�[�i�X�e���I�j��ڑ�����B<br>
</p>
<p><strong>H/W�\��</strong><br>
 �ESeeed Studio XIAO ESP32C3 - �R���g���[��<br>
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
</tr>
<tr>
<td>SDA</td><td>D4</td>
</tr>
</table>
</p>
<p>
<table> 
<tr>
<td>�^�N�g�X�C�b�`</td><td>XIAO</td>
</tr>
<tr>
<td>����</td><td>GPIO2</td>
</tr>
<tr>
<td>�I��</td><td>GPIO3</td>
</tr>
<tr>
<td>PON/POFF</td><td>GPIO4</td>
</tr>
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
<p><strong>�T�ԃX�P�W���[���̐ݒ���@</strong><br>
�u���E�U����A"http://192.168.aa.bb" �̂悤�Ɏw��ibb�̕�����OLED�\�����u��3�s�ڂɕ\���j����XIAO ESP32C3�ɃA�N�Z�X����ƁA�ȉ��̉�ʂ��\�������B<br>
�����̕\�ɂ́A�e�j�����Ƃ̒���\�肪�������ɕ\���i1�G���g���̍��ڂ́A�ԑg�J�n�����A���W�I�ǁA�������ԁi���j�A���ʁA�ԑg�I����ɓd��OFF�i1�̎��j�ł���j����Ă���B<br>
�e�j���̒���\���ύX����ꍇ�́A�ύX����j���̃��W�I�{�^�����N���b�N����B���݂̓��e���A��ԏ�̓��͗̈�ɕ\�������̂ŁA�����ҏW����B<br>
�ҏW��A"submit"�{�^�����N���b�N����ƁA�ύX���e���ۑ������B<br>
�ύX���e�Ɍ`����̊ԈႢ������ꍇ�́A�G���[���\������A�ۑ�����Ȃ��B�Ȃ��A�e�ԑg�̊J�n�����ƏI�������͕��P�ʂŏd�Ȃ�Ȃ��悤�Ɏw�肷�邱�ƁB<br>
��L�̐ݒ荀�ڒ��̃��W�I�ǂɂ��ẮA�X�P�b�`����stnFreq[]�z��i���g���j�̃C���f�b�N�X���w�肷��B<br>
�ȉ��̉�ʂ�"Station List"�ɂ́A�X�P�b�`����stnName[]�z�� �i�ǖ��j���\�������̂őΉ������Ă����K�v������B<br>
������"Control Functions"�ɂ́A���ʁA�I�ǁA�d��ON/OFF�̊e����{�^��������B
<p>
<img src="./weekly_schedule.jpg" width="900" height="560"><br>
</p>

</p>
<p><strong>�C���X�g�[��</strong><br>
<ol>
<li>�R�[�h���AZIP�`���Ń_�E�����[�h</li>
<li>ArduinoIDE�ɂ����āA���C�u�����}�l�[�W������ȉ����������ăC���X�g�[������</li>
 <ul>
  <li>Adafruit_BusIO</li>
  <li>Adafruit_GFX</li>
  <li>Adafruit_SSD1306</li>
  <li>RDA5807</li>
 </ul>
<li>�ǉ��̃��C�u�������AZIP�`���Ń_�E�����[�h�A���C�u�����}�l�[�W������C���X�g�[������</li>
 <ul>
  <li>TimeLib&nbsp;:&nbsp; https://github.com/PaulStoffregen/Time</li>
 </ul>
<li>ArduinoIDE����xiao_esp32c3_wifi_clock_radio_RDA5807.ino���J��</li>
<li>�u���؁E�R���p�C���v�ɐ���������A��U�A�u���O��t���ĕۑ��v���s��</li>
</ol>
</p>
<p><strong>�኱�̉��</strong><br>
�E��H�}�̓f�[�^�V�[�g���Q�Ƃ̂��ƁBLOUT�AROUT�̃R���f���T��100�|200��F���x��ڑ�����Ɖ������ǂ��Ȃ�B�Ȃ��A��H�}�ɂ���C���_�N�^���X�n�̕��i�͖����Ă����삷��B<br>
�E�w��ł���WiFi�X�e�[�V�����́A�Q�����܂łŁA�v�X�ASSID�ƃp�X���[�h��ݒ肷��B<br>
�E1���Ɏw��ł���ԑg�̐���9�܂łł���i���₷�ꍇ�͎��ȐӔC�ł��肢���܂��j�B�������W�I�ǂ̔ԑg�𑱂��Ē����ꍇ�́A�������Ԃ����Z���āA1�G���g���Ŏw�肷��΂悢�B<br>
&nbsp;&nbsp;�Ȃ��[��0�����ׂ��������́A���̗j���Ɏw�肷��B<br>
�EstnFreq[]�Ɏ�M��������ǂ̎��g�����w�肷��B�Ⴆ��80.4MHz�̏ꍇ�A8040�Ǝw�肷��B�Ȃ��AstnName[]�ɂ͑Ή���������ǖ����w�肷��B����̓u���E�U�ɕ\�������B<br>
&nbsp;&nbsp;�w��ł�������ǂ�8�܂łł���i���₷�ꍇ�͎��ȐӔC�ł��肢���܂��j�B<br>
<p>
<img src="./RDA5807_XIAO_PAD_2.jpg" width="360" height="480"><br>
</p>
</p>
<p><strong>���ӎ���</strong><br>
�E�����ۏ؂�����̂ł͂���܂���̂ŁA���p�̍ۂ́A���ȐӔC�ł��y���݂��������B<br>
</p>
