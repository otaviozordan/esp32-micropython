# micropython-no-esp32

## Você ira aprender:

- [Sobre o Micropython](#sobre-micropython)
- [Instalar os drivers do ESP32](#instalar-os-drivers-do-esp32)
- [Instalar e configurar o Thonny](#instalar-e-configurar-o-thonny)
- [Como atualizar o ESP32 com o firmware mais recente do Micropython](#como-atualizar-o-esp32-com-o-firmware-mais-recente-do-micropython)
- [Usar o Prompt Micropython do ESP82 no Thonny](#usar-o-prompt-micropython-do-esp82-no-thonny)
- [Piscar um Led usando Micropython no ESP32](#piscar-um-led-usando-micropython-no-esp32)
- [Gravar um código no ESP32](#gravar-um-código-no-esp32)

<p align='center'>
    <img src="img\CEDEN logo.png" width="370" height="90">
</p>

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
<br>
<br>

## Usar o Prompt Micropython do ESP82 no Thonny
Veja que foi reconhecido o ESP32 e já se abriu um prompt de comando. Caso isso não acontessa prescione <code>Ctrl + F2</code> ou prescione *Stop* para reiniciar a conexão.

<p align='center'>
    <br>
    <img src="img\PromptThonny.png">
    <br>
</p>


No Promp pode executar os comandos do Micropython, teste digitar esse simples comando de Python que exibe uma mensagem:

```python
print("Hello World!")
```

Veja o resultado:

<p align='center'>
    <br>
    <img src="img\PrintTerminal.png">
    <br>
</p>
<br>
<br>

### Acendendo um led pelo terminal
Tente agora acionar uma GPIO (porta digital) do ESP32 pelo terminal. Para isso cole no terminal o seguinte código comentado:
```python
from machine import Pin #Importamos da biblioteca Machine a função Pin que permite controlarmos os pinos do embarcado (ESP32).
led = Pin(2, Pin.OUT) #Configura a porta 2 como saida e cria o objeto led para essa porta.
```
<p align='center'>
    <br>
    <img src="img\pinmode.png">
    <br>
</p>

Este código define o pino 2 como saida e cria o objeto led. No ESP32 o pino 2 fica conectado a um led na própria placa, tente aciona-lo pelo comando:
```python
led.value(1)
```
E desligar usando o comando:
```python
led.value(0)
```

## Piscar um Led usando Micropython no ESP32
No editor de código vamos escrever um blink:
```python
import time #Importamos a biblioteca de tempo.
from machine import Pin  #Importamos da biblioteca Machine a função Pin que permite controlarmos os pinos do embarcado (ESP32).

led=Pin(2, Pin.OUT) #Configura a porta 2 como saida e cria o objeto led para essa porta.
 
while True: #Cria um loop.
    led.value(1)    #Define o pino 2 como alto.
    time.sleep(1)   #Espera 1 seg.
    led.value(0)    #Define o pino 2 como baixo.
    time.sleep(1)   #Espera 1 seg.
```

<p align='center'>
    <br>
    <img src="img\Blink.png">
    <br>
</p>

Após escrever o código clique em <code>Run</code> ou prescione *F5*.

<p align='center'>
    <br>
    <img src="img\blink.gif">
</p>

Pronto! Você tem um Blik.


## Gravar um código no ESP32
Entretanto se você tirar o esp32 da alimentação e liga-lo novamente verá que ele não executará comando algum. Você deve salvar na memória do ESP o seu código como <code>main.py</code>. 
Clique em *Salvar* e selecione o *dispositivo MicroPython*.

<p align='center'>
    <br>
    <img src="img\salvar.png" width="400" height="300">
    <img src="img\Dispositivo.png" width="400" height="300">
    <br>
</p>

Outra ferramenta interessante é que você também pode abrir um código do seu computador ou do *dispositivo MicroPython*, diferente do Firmware do arquido que uma vez gravado se você não tiver uma cópio no seu computador é impossivel recuperar o código.

Na guia que se abriu na aba *Nome do arquivo* digite <code>main.py</code>. Quando Firmware MicroPython for carregado no Esp ou seja, quando o ESP32 for alimentado, ele executará o arquivo de nome <code>main.py</code>.

<p align='center'>
    <br>
    <img src="img\main.png">
</p>

Salve e reconecte o ESP32 para ver sua execução.

## Conclusão
Este é o fim deste tutorial. O ESP32 já está rodando Micropython e agora você já sabe usar o ambiente para desenvolver seus projetos. As possibilidades com o MicroPython são enormes e você pode aproveitar tudo que seu ESP32 tem a oferecer. 
Leia a [documentação do MicroPython](https://docs.micropython.org/en/latest/esp32/tutorial/intro.html) para aprender como usar todas as funções.

Esse tutorial foi desenvolvido por mim para o CEDEN na saudossima ETE FMC, onde estudo atualmente.
<p align='center'>
    <img src="img\CEDEN logo.png" width="370" height="90">
</p>

<h2 align='center'>
 💬 Entre em contato comigo!
</h2>

<p align='center'>
  <a href="https://www.linkedin.com/in/ot%C3%A1vio-zordan-alves-b88160211/">
    <img src="https://img.shields.io/badge/linkedin-%230077B5.svg?&style=for-the-badge&logo=linkedin&logoColor=white" />
  </a>&nbsp;&nbsp;
  <a href="https://github.com/otaviozordan">
    <img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white" />        
  </a>&nbsp;&nbsp;
</p>