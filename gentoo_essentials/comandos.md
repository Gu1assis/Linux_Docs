## Verificar Bateria

cat /sys/class/power_supply/BAT0/capacity

## Utilidades do sistema

sensors -> ver temperatura e rpm e outras info do hardware. Vem do pacote sys-apps/lm-sensors

upower -i /org/freedesktop/UPower/devices/battery_BAT0 | grep percentage -> Meu caminho atual para ver a bateria usando upower.


