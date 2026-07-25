# Manipulando texto no vim

== -> auto identação

# Operações

d -> deletar, mas salva o texto no clipboard.
Ex: dw deleta uma palavra, dd apaga a linha toda.

y -> yank, copiar, yy copia a linha toda.

p, P -> colar antes ou depois do cursor.

c -> change,

. -> repete a operação anterior completa.

# Operadores internos

i -> in. usado com um operador antes e um objeto depois.
Ex: diw apaga a palavra, yip copia o paragrafo, ci( apaga e começa a editar o que estiver entre parenteses.

a -> around. faz entre dois objetos.
Ex: daW apaga tudo entre um espaço e outro 

# Modos

NORMAL -> Pressione ESC ou Ctrl C. Modo de navegação de texto.

VISUAL -> Basta pressionar v. Usado para selecionar texto para realizar alguma operação

REPLACE -> R. Usado para escrever por cima daquela linha, apagando tudo por posição. 

VISUAL BLOCK -> Ctrl + v. Permite marcar visualização baseada na posição absoluta.
