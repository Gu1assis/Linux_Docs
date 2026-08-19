# Compilando manualmente

Eh boa pratica colocar os seus binarios compilados manualmente numa pasta que visivel pelo sistema todo.

Eu estou seguindo esse padrao no meu gentoo:

- **Codigo fonte:** coloco em /opt/bin e compilo o binario la
- **Symlink:** coloco o symlink em /usr/local/bin/ para o binario compilado

```
sudo ln -s /opt/bin/tealdeer /usr/local/bin/tldr
```

Pra atualizar eu preciso recompilar o codigo fonte apenas. 

Claro, voce pode colocar o binario diretamente em /usr/local/bin que ja e pensada para receber
binarios compilados manualmente. Mas, com o synlink voce nao precisa ficar movendo o binario.
