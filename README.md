# micropython-no-esp32

<h3>
    Sobre Micropython
</h3>
<img src="img\Micropython-logo.svg" alt="Screen" width="400" height="400">
<p>
    O <a href="https://micropython.org/">Micropython</a> é uma implementação Open Source que permite utilizar  <a href="https://python.org/">Python</a> em microcontroladores. Essa é uma exelente solução para desenvolver códigos com familiaridade ao desktop  para seus embarcados
</p>
<p>
Você ira aprender:
<ul>
    <li>Instalar os drivers do ESP32.</li>  
    <li>Instalar e configurar o Thonny.</li>
	<li>Como atualizar o ESP32 com o firmware mais recente do <a href="https://micropython.org/download/esp32/">Micropython</a>.</li>
	<li>Usar o Prompt Micropython do ESP82 no Thonny.</li>
    <li>Piscar um Led usando Micropython no ESP32.</li>
    <li>Gravar um código autoexecutavel no ESP32.</li>
    <li>Instalar uma biblioteca.</li>
</ul>
<div>
    <h3>Instalar os drivers do ESP32.</h3>
        <p> Para que seu computador possa se comunicar com o ESP32 é necessário instalar os drivers, caso você já os possua siga para <a href="#Instalar-e-configurar-o-Thonny">Instalar e configurar o Thonny</a>.</p>
        <p> O conversor USB-Serial que permite seu computador conversar com o chip ESP32 através da USB. Dependendo da versão da placa, o chip responsável por essa conversão pode ser o CP210x (placas NodeMCU V2 e ESP32) ou o CH340G (placas NodeMCU V3). Este tutorial é destinado ao ESP32 portanto é para o CP210x que iremos instalar.</p>
        <li><a href="https://www.silabs.com/documents/public/software/CP210x_VCP_Windows.zip"> Driver ESP32 e NodeMCU V2 para Windows</a></li>
        <p>Com o donwload concluido descompacte a pasta  e execute o instalador do seu SO.</p>
        <img src="img\Drivers.jpeg">
</div>
<div>
    <h3>Instalar e configurar o Thonny</h3>
      <p>Para programar e reinstalar o firmware no ESP32 utilizaremos o <a href="https://thonny.org/">Thonny</a>, se você usa um sistema Windows <a href="https://github.com/thonny/thonny/releases/download/v4.0.1/thonny-4.0.1.exe">clique aqui </a> para fazer download do instalador.</p>
      <p>Após a instalação S</p>
      <img src="README\images\Espruino_screen.png" alt="Screen" width="1000" height="300">
      <p>Um arquivo .zip será baixado, extraia esta pasta para área de trabalho, dentro dessa pasta devemos procurar pela pasta referente ao ESP32, geralmente o final dessa dela termina com <code>_esp32</code>, conforme vemos na Figura 3. 
      </p>
      <p><img src="README\images\Pasta3.png" alt="Screen" width="900" height="200"></p>
   <h3>Atualizando o Firmware</h3>
   <p>A maneira mais fácil de atualizar o firmware é usando o <a href="https://docs.espressif.com/projects/esptool/en/latest/esp32/">esptool</a>, uma ferramenta Python da <a href="https://www.espressif.com/en">Espressif</a> que nos permite atualizar o firmware no ESP32.</p>
   <p>Conforme indicado na documentação do <a href="https://github.com/espressif/esptool">repositório GitHub</a> do esptool , precisamos ter <a href="https://www.python.org/downloads/">Python 2.7</a>, <a href="https://www.python.org/downloads/">Python 3.4</a> ou uma versão superior instalada. Para instalar o esptool basta abrir o cmd ou powershell e enviar o seguinte comando na linha de comando do Windows: </p>
   <p align='center'><code>pip install esptool</code></p>
</div>
<P>Em seguida a maneira mais fácil para realizar o flashing do firmware é abrir uma linha de comando e navegar até a pasta que extraímos do arquivo .zip. Para fazer isso execute os seguintes passos:</P>
<ol>
<li>Abra o cmd ou powershell.</li>
<img src="README\images\cMD.png" alt="Screen" width="950" height="400">
<li>Copie o path da pasta <code>_esp32</code></li>
<img src="README\images\FIle.png" alt="Screen" width="751" height="268">
<li>Abra uma linha de comando no cmd e navegue até o diretório da pasta usando o comando <code>cd</code> + <code>nome da pasta</code>.</li>
</ol>
<img src="README\images\ezgif.com-gif-maker (1).gif" alt="Screen" width="950" height="400">
</p>
<p>Precisamos dar o comando abaixo, levando em consideração o seguinte, Você precisa trocar a <code>COM11</code> pela porta COM da sua placa no seu computador;</p>
<pre><code>python -m esptool --port COM11 --baud 460800 write_flash --flash_size=detect 0x1000 bootloader.bin 0x10000 espruino_esp32.bin 0x8000 partitions_espruino.bin</code></pre>

