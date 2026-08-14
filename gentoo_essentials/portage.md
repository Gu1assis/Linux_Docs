# Portage e Packages

## Sync e Atualizacao

Voce pode sincronizar sua lista de pacotes com a do servidor com:

```
emerge --sync
```

E atualizar todos os pacotes do sistema usando:

```
emerge --update --deep --newuse @world
```

## Procurar pacotes

Verificar se pacote esta instalado 

```
equery list <nome>
```

Ou todos:

```
equery list -p <nome>
```

Procurar nome do package:

```
emerge --search <name> (ou -s)
emerge --searchdesc <descricao> (ou -S)
```

## Instalacao de pacotes

```
emerge -a pacote/pacote
```

Voce pode checar as USE flags disponiveis para este pacote, usando:

```
emerge -vp <categoria>/<app>
```

### Unmasks

Alguns pacotes podem pedir que voce retirar mascaras
As mascaras sao bloqueios colocados pelo gentoo para que voce analise manutalmente se quer instalar um pacote ou nao.

Eles podem surgir por diferentes motivos:

- Pacote em Testes (~amd64, ~x86): o pacote e novo e pode apresentarinstabilidades. Geralmente nao tem problema
- Mask de Profile ou Hard: Devs explicitamente bloquearam. Por motivos de seguranca ou esta quebrado.
- Licenca: O pacote possui uma licenca que voce nao concordou explicitamente.

Para resolver, voce pode usar esta flag para add o unmask:

```
sudo emerge --ask --autounmask-write <categoria>/<app>
dispatch-conf
```

Se isso nao funcionar, voce pode add manualmente:

```
echo "<categoria>/<app> ~amd64" >> /etc/portage/package.accept_keywords/<app>
```

ou algo semelhante.

De forma mais pratica, voce pode aceitar globalmente, por exemplo pro caso de masks de testes:

```
echo 'ACCEPT_KEYWORDS="~amd64"' >> /etc/portage/make.conf
```

Mas tenha em mente que se voce rodar uma atualizacao geral, vai atualizar tudo para a mais recente com pacotes ainda em fase de testes.

### Binarios pre compilados

Para instalar o binario pre-compilado do servidor use:

```
emerge -a -g pacote/pacote
```

que da fallback para compilar qnd nao acha compativel. Para baixar apenas se achar,
use -K

Para ver quais USE flags sao necessarias para um dado pacote binario execute:

```
emerge --pretend --verbose --getbinpkg --usepkgonly --binpkg-respect-use=n <pacote>
```

Voce pode verificar o progresso de uma instalcao usando o genlop, que pode ser instalado com

```
emerge -a app-portage/genlop
```

e use com genlop -c, por exemplo.

## Despachar configuracoes de package.use

```
dispatch-conf
```
