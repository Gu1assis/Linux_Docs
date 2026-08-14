## Verificar Bateria

cat /sys/class/power_supply/BAT0/capacity

## Portage e Packages

### Procurar pacotes

Verificar se pacote esta instalado 

equery list <nome>

Ou todos:

equery list -p <nome>

Procurar nome do package:

emerge --search <name> (ou -s)

emerge --searchdesc <descricao> (ou -S)

### Instalacao de pacotes

emerge -a pacote/pacote

Voce pode checar as USE flags disponiveis para este pacote, usando:

emerge -vp pac/pac

Para instalar o binario pre-compilado do servidor use:

emerge -a -g pacote/pacote

que da fallback para compilar qnd nao acha compativel. Para baixar apenas se achar,
use -K

Para ver quais USE flags sao necessarias para um dado pacote binario execute:

emerge --pretend --verbose --getbinpkg --usepkgonly --binpkg-respect-use=n <pacote>

Voce pode verificar o progresso de uma instalcao usando o genlop, que pode ser instalado com

emerge -a app-portage/genlop

e use com genlop -c, por exemplo.

### Despachar configuracoes de package.use

dispatch-conf

## Utilidades do sistema

sensors -> ver temperatura e rpm e outras info do hardware. Vem do pacote sys-apps/lm-sensors

upower -i /org/freedesktop/UPower/devices/battery_BAT0 | grep percentage -> Meu caminho atual para ver a bateria usando upower.


