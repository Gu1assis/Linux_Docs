# Screenshots

## Instalacao

```
sudo emerge --ask gui-apps/grim gui-apps/slurp
```

Se quiser para area de transferencia:

```
sudo emerge --ask gui-apps/wl-clipboard
```

## Uso

Usando slurp e grim, voce pode salvar com:

```
grim image.png
```

ou se preferir uma parte da tela apenas:

```
grim -g "$(slurp)" image.png
```

Ou direto para a area de transferencia:

```
grim -g "$(slurp)" - | wl-copy
```

Eu gosto de criar um alias:

```
alias printscreen='grim -g "$(slurp)" ~/screenshots/print_$(date +%F_%T).png'
```
