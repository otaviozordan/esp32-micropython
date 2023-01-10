# micropython-no-esp32

## Sobre Micropython
<img src="img\Micropython-logo.svg" alt="Screen" width="400" height="400">
<p>
    O <a href="https://micropython.org/">Micropython</a> é uma implementação Open Source que permite utilizar  <a href="https://python.org/">Python</a> em microcontroladores. Essa é uma exelente solução para desenvolver códigos com familiaridade ao desktop  para seus embarcados
</p>
Você ira aprender:

- [Instalar os drivers do ESP32](#instalar-os-drivers-do-esp32)
- [Instalar e configurar o Thonny](#instalar-e-configurar-o-thonny)
- [Como atualizar o ESP32 com o firmware mais recente do Micropython](#como-atualizar-o-esp32-com-o-firmware-mais-recente-do-micropython)
- [Usar o Prompt Micropython do ESP82 no Thonny](#usar-o-prompt-micropython-do-esp82-no-thonny)
- [Piscar um Led usando Micropython no ESP32](#piscar-um-led-usando-micropython-no-esp32)
- [Gravar um código autoexecutavel no ESP32](#gravar-um-código-autoexecutavel-no-esp32)
- [Instalar uma biblioteca](#instalar-uma-biblioteca)

<br>

## Instalar os drivers do ESP32.
<div>
        <p> Para que seu computador possa se comunicar com o ESP32 é necessário instalar os drivers, caso você já os possua siga para <a href="#Instalar-e-configurar-o-Thonny">Instalar e configurar o Thonny</a>.</p>
        <p> O conversor USB-Serial que permite seu computador conversar com o chip ESP32 através da USB. Dependendo da versão da placa, o chip responsável por essa conversão pode ser o CP210x (placas NodeMCU V2 e ESP32) ou o CH340G (placas NodeMCU V3). Este tutorial é destinado ao ESP32 portanto é para o CP210x que iremos instalar.</p>
        <li><a href="https://www.silabs.com/documents/public/software/CP210x_VCP_Windows.zip"> Driver ESP32 e NodeMCU V2 para Windows</a></li>
        <p><br>Com o donwload concluido descompacte a pasta  e execute o instalador do seu SO.<br></p>
        <img src="img\Drivers.jpeg">
        <br>
</div>


## Instalar e configurar o Thonny 
Para programar e reinstalar o firmware no ESP32 utilizaremos o [Thonny](https://thonny.org), se você usa um sistema Windows [clique aqui](https://github.com/thonny/thonny/releases/download/v4.0.1/thonny-4.0.1.exe) para fazer download do instalador.
Após a instalação clique sobre o executavel e esperar abrir a pagina de instalação.
<br>

<img src="img\Micropython-logo.svg">

## Como atualizar o ESP32 com o firmware mais recente do Micropython

## Usar o Prompt Micropython do ESP82 no Thonny

## Piscar um Led usando Micropython no ESP32

## Gravar um código autoexecutavel no ESP32

## Instalar uma biblioteca