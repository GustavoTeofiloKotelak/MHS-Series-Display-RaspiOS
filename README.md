# MHS-Series-Display-RaspiOS

### Etapas para utilizar display MHS Series 3.5 Inch

Documentação de instalação do display MHS Series na Raspberry Pi 4B.

Ocorreram muitos erros no processo, até se descobrir que o problema era a versão mais recente do Raspibian OS.

Link do display utilizado: https://www.aliexpress.us/item/4000317771217.html?aff_fcid=ad713118f45a449aad89d2ae3c071ecf-1699635711124-06261-_DBn3upd&tt=CPS_NORMAL&aff_fsk=_DBn3upd&aff_platform=shareComponent-detail&sk=_DBn3upd&aff_trace_key=ad713118f45a449aad89d2ae3c071ecf-1699635711124-06261-_DBn3upd&terminal_id=7911f8c5739242aa97f626e9e359b3fe&afSmartRedirect=y&gatewayAdapt=4itemAdapt

Está especificado no link de venda do Display:
Due to the architectural changes in the new version of the official Raspberry Pi system（Raspberry Pi OS） released in October 2023, this version of the system is not compatible with GPIO screens. Please use the official system released before October 2023. If later official systems can support GPIO screens, we will update this notice.

Link do suporte: http://www.lcdwiki.com/MHS-3.5inch_RPi_Display#Download_Resources

Para que fosse possível utilizar o display, foi necessário usa uma OS com uma versão anterior a de outubro de 2023 da Raspbian OS.
Essas versões podem ser encontradas em : https://downloads.raspberrypi.com/raspios_arm64/images/

Para realizar o boot do sistema foi utilizado o próprio Rapberry Pi Imager.


Ao dar boot pela primeira vez no sistema, antes de tudo foi utilizado os seguntes comandos:

```
sudo apt-get update
sudo apt-get install libraspberrypi-dev
```
Estes comandos instalam o pacote de desenvolvimento na raspi, sem ele ocorre o erro:
```
fatal error: bcm_host.h: Arquivo ou diretório inexistente
    9 | #include <bcm_host.h>
```

Depois de instalado o pacote de desenvolvimento é possível rodar normalmente os comandos de instalação do display:

```
sudo rm -rf LCD-show
git clone https://github.com/goodtft/LCD-show.git
chmod -R 755 LCD-show
cd LCD-show/
sudo ./MHS35-show

```

Funcionou Corretamente.

Depois disso foi utilizado os comandos de update do sistema:
```
sudo apt-get update
sudo apt-get upgrade
```




