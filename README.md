# micropython-no-esp32

<p align='center'>
    <img src="img\CEDEN logo.png">
</p>

## Você ira aprender:

- [Sobre o Micropython](#sobre-micropython)
- [Instalar os drivers do ESP32](#instalar-os-drivers-do-esp32)
- [Instalar e configurar o Thonny](#instalar-e-configurar-o-thonny)
- [Como atualizar o ESP32 com o firmware mais recente do Micropython](#como-atualizar-o-esp32-com-o-firmware-mais-recente-do-micropython)
- [Usar o Prompt Micropython do ESP82 no Thonny](#usar-o-prompt-micropython-do-esp82-no-thonny)
- [Piscar um Led usando Micropython no ESP32](#piscar-um-led-usando-micropython-no-esp32)
- [Gravar um código autoexecutavel no ESP32](#gravar-um-código-autoexecutavel-no-esp32)
- [Instalar uma biblioteca](#instalar-uma-biblioteca)

## Sobre Micropython
<p align='center'>
    <img src="img\Micropython-logo.svg" alt="Screen" width="300" height="300">
</p>
<p>
    O <a href="https://micropython.org/">Micropython</a> é uma implementação Open Source que permite utilizar  <a href="https://python.org/">Python</a> em microcontroladores. Essa é uma exelente solução para desenvolver códigos com familiaridade ao desktop  para seus embarcados
<br><br>
</p>

## Instalar os drivers do ESP32.
<div>
        <p> Para que seu computador possa se comunicar com o ESP32 é necessário instalar os drivers, caso você já os possua siga para <a href="#Instalar-e-configurar-o-Thonny">Instalar e configurar o Thonny</a>.</p>
        <p> O conversor USB-Serial que permite seu computador conversar com o chip ESP32 através da USB. Dependendo da versão da placa, o chip responsável por essa conversão pode ser o CP210x (placas NodeMCU V2 e ESP32) ou o CH340G (placas NodeMCU V3). Este tutorial é destinado ao ESP32 portanto é para o CP210x que iremos instalar.</p>
        <li><a href="https://www.silabs.com/documents/public/software/CP210x_VCP_Windows.zip"> Driver ESP32 e NodeMCU V2 para Windows</a></li>
        <p><br>Com o donwload concluido descompacte a pasta  e execute o instalador do seu SO.<br><br></p>
        <img src="img\Drivers.jpeg">
        <br><br>
</div>


## Instalar e configurar o Thonny 
Para programar e reinstalar o firmware no ESP32 utilizaremos o [Thonny](https://thonny.org), se você usa um sistema Windows [clique aqui](https://github.com/thonny/thonny/releases/download/v4.0.1/thonny-4.0.1.exe) para fazer download do instalador.

<p align='center'>
    <br>
    <img src="img\Thonny Download.png">
    <br>
</p>

Após a instalação clique sobre o executavel e esperar abrir a pagina de instalação. Prescione "next" até concluir.

<div align='center'>
    <br>
    <img src="img\Instalação Thonny.png" width="400" height="300">
    <img src="img\Finish Thonny.png" width="400" height="300">
    <br>
</p>
</div>

## Como atualizar o ESP32 com o firmware mais recente do Micropython
Para instalaro firmware do Micropython no ESP32 precisamos da imagem mais rescente do Firmware. Instale [nesse site](https://micropython.org/download/esp32/) descendo até Firmware e clicando sobre o mais rescente, no meu caso é a [v1.19.1 (2022-06-18)](https://micropython.org/resources/firmware/esp32-20220618-v1.19.1.bin).

<p align='center'>
    <br>
    <img src="img\Firmware.png">
    <br>
</p>

Com o Firmawe instalado vamos ao Thonny fazer sua gravação no ESP32. Conecte o ESP32 a porta USB do seu computador. Com o Thonny aberto clique em 
<code>Executar --> COnfigurar Interpretador...</code>

<p align='center'>
    <br>
    <img src="img\Executar-Interpretador.png" width="550" height="450">
    <br>
</p>

Abrirá a janela de <code>Opções do Thonny</code>. Selecione o tipo do interpretador que o Thonny usará para executar o código, procure a opção <code>MicroPython (ESP32)</code>.

<p align='center'>
    <br>
    <img src="img\Configurarcoes Intrpretador.png" width="550" height="450">
    <br>
</p>

Agora observe se foi indentificado o ESP32 na porta COM, se o seu ESP não aparecer na listagem como abaixo reinstale os drivers como [nesse trecho](#instalar-os-drivers-do-esp32).

<p align='center'>
    <br>
    <img src="img\Porta.png" width="550" height="450">
    <br>
</p>

Você pode selecionar a porta clicando sobre o seu Esp (no meu caso <code>Silicon Labs CP210x</code>) ou deixe a opção <code><Tente detectar a porta automaticamnte></code>, assim quando você conectar o Esp ao computador ele tentará se conectar independente da porta.

Agora clique em <code>Install or update MicroPython</code> e selecione o esp32. Agora clique em <code>Browse</code> para procurar o Firmware que instalamos.

<p align='center'>
    <br>
    <img src="img\FirmwarePort.png" width="400" height="300">
    <img src="img\FirmwareBrowse.png" width="400" height="300">
    <br>
</p>

Agora selecione o arquivo .bin que instalamos e clique em <code>Instalar</code>.

<p align='center'>
    <br>
    <img src="img\FirmwareSelect.png" width="400" height="300">
    <img src="img\FirmwareInstall.png" width="400" height="300">
    <br>
</p>

Agora o processo de regravação do Firmware foi iniciado, espere ser concluido e clique em <code>Fechar</code>.

<p align='center'>
    <br>
    <img src="img\UploadFirmware.png" width="400" height="300">
    <img src="img\FinishFirmware.png" width="400" height="300">
    <br>
</p>

## Usar o Prompt Micropython do ESP82 no Thonny
Veja que foi reconhecido o ESP32 e já se abriu um prompt de comando. Caso isso não acontessa prescione <code>Ctrl + F2</code> ou prescione *Stop* para reiniciar a conexão.

<p align='center'>
    <br>
    <img src="img\PromptThonny.png" width="550" height="450">
    <br>
</p>

No Promp pode executar os comandos do Micropython, teste digitar:
´´´
print("Hello World!")
´´´

Veja o resultado:

<p align='center'>
    <br>
    <img src="img\PrintTerminal.png" width="550" height="450">
    <br>
</p>

## Piscar um Led usando Micropython no ESP32

## Gravar um código autoexecutavel no ESP32

## Instalar uma biblioteca