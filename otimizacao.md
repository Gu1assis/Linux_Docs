# Otimizacao de Processos - Alem do Top

# Gerenciamento de Recursos

## Configurar prioridade para um processo

Dar prioridade maxima ao processo a partir do scheduler. O nivel de prioridade
pode variar de 19 (minima) a -20 (maxima).

***Iniciar um processo com prioridade máxima de CPU (-20 requer root)***
sudo nice -n -20 ./meu_processo

***Alterar a prioridade de um processo já em execução (PID 1234)***
sudo renice -n -10 -p 1234

## Afinidade com CPU (Memorias cache L1,L2,...)

Voce pode solicitar que o kernel evite mover os dados de um processo entre nucleos
para evitar cache miss

***Executar o processo fixado apenas nos núcleos 0 e 1***
taskset -c 0,1 ./meu_processo

***Alterar a afinidade de um processo em execução***
taskset -pc 2,3 1234

## Isolamento e Limitacao de uso de recursos com Cgroups v2

Em distros com systemd, vc tem a abstracao pra nao precisar
editar /sys/fs/cgroup diretamente:

***Limita o processo a no máximo 2 núcleos de CPU (200%) e 2GB de RAM***
systemd-run --user --scope -p CPUQuota=200% -p MemoryMax=2G ./meu_processo

Para o  openRc, voce pode usar scripts. 
Se quiser mais praticidade, use o libcgroup:

sudo emerge --ask dev-libs/libcgroup

Consulte a doc sobre cgroups para mais informacoes.

# Diagnostico e Monitoramento

## Strace para analisar uso de syscalls

Analise custos de runtime e gargalos de I/O com:

***Resumo estatístico de tempo gasto por syscall***
strace -c -p 1234

***Monitorar apenas syscalls de leitura, escrita e rede***
strace -e trace=read,write,network -p 1234

## Inspecao de Arquivos e Sockets de um processo com lsof

lsof -p 1234

## Gerar relatorio de performance com perf
***Grava eventos de CPU do processo por 10 segundos***
perf record -g -p 1234 -- sleep 10

***Analisa o relatório com a pilha de chamadas (Call Stack)***
perf report

## Algumas outras ferramentas

***pidstat:*** parte do pacote sysstat. Exibe o consumo de I/O, context switch e memoria por processo.
pidstat -d -u -r 1

***ionice:*** define o agendamento de  I/O de disco.
***Executa uma operação pesada de I/O sem travar o disco para o sistema***
ionice -c 3 ./backup_pesado.sh
