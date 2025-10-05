# 🐧 Comandos Básicos do Linux

Guia rápido de comandos Linux para estudo e referência.

---

## 📂 1. Arquivos e Diretórios

```bash
# listar conteúdo do diretório
ls
ls -l         # detalhes
ls -lh        # detalhes com tamanhos humanos

# ver onde estou
pwd

# mudar de diretório
cd /caminho/para/diretorio
cd ..         # volta um nível
cd -          # volta para o diretório anterior

# criar diretório
mkdir pasta
mkdir -p pasta1/pasta2  # cria estrutura

# remover diretório
rmdir pasta             # vazio
rm -rf pasta            # forçado (cuidado)

# copiar arquivo/diretório
cp arquivo destino
cp -r pasta destino

# mover/renomear
mv arquivo destino
mv arquivo novo_nome

# criar arquivo vazio
touch arquivo.txt
> arquivo.txt           # cria/zera

# criar arquivo e escrever conteúdo
cat > arquivo.txt       # digite conteúdo, depois CTRL+D
echo "linha" > arquivo.txt   # sobrescreve
echo "linha" >> arquivo.txt  # acrescenta

# editar arquivo
nano arquivo.txt
vim arquivo.txt         # editor avançado

# ver detalhes do arquivo
stat arquivo.txt
file arquivo.txt


# mostrar todo conteúdo
cat arquivo.txt

# navegar em arquivos grandes
less arquivo.txt    # setas para navegar, q para sair
more arquivo.txt

# ver primeiras linhas
head arquivo.txt
head -n 20 arquivo.txt   # primeiras 20 linhas

# ver últimas linhas
tail arquivo.txt
tail -n 15 arquivo.txt   # últimas 15 linhas
tail -f arquivo.txt      # acompanhar em tempo real (logs)


# ver permissões
ls -l

# mudar permissões
chmod 644 arquivo.txt    # dono rw, grupo r, outros r
chmod 600 arquivo.txt    # dono rw, mais ninguém

# mudar dono
chown usuario:grupo arquivo.txt

# exemplos de permissões
chmod u+x script.sh      # dar execução para o dono
chmod g-w arquivo.txt    # tirar escrita do grupo


# ver IPs, interfaces, rotas
ip addr
ip link
ip route

# pingar host
ping 8.8.8.8

# rastrear rota
traceroute google.com


# netstat - Linux
sudo netstat -tuln        # TCP/UDP ouvindo (LISTEN)
sudo netstat -tulpn       # + mostra PID/programa (Linux)

# ss (substituto moderno do netstat)
ss -tuln                  # TCP/UDP ouvindo (LISTEN)
sudo ss -tulpn            # + mostra PID/programa

# detalhes
-t  = TCP
-u  = UDP
-l  = apenas escutando (LISTEN)
-n  = números em vez de nomes
-p  = mostra PID/programa


# conexões e portas no Windows CMD
netstat -ano          # mostra conexões e PID
netstat -b            # mostra executável associado
netstat -abno         # mostra tudo: executável + PID + portas

# PowerShell (mais moderno)
Get-NetTCPConnection



# contar bytes e linhas
wc -c arquivo.txt     # bytes
wc -l arquivo.txt     # linhas

# mostrar caracteres não imprimíveis
cat -A arquivo.txt

# hexdump
hexdump -C arquivo.txt | head

# strings imprimíveis
strings arquivo.txt




# listar processos
ps aux           # todos os processos com detalhes
top              # monitoramento em tempo real
htop             # top mais avançado (se instalado)

# matar processo
kill PID         # envia SIGTERM
kill -9 PID      # força matar (SIGKILL)



# usuário atual
whoami

# informações detalhadas
id
groups

# listar todos usuários
cat /etc/passwd

# listar todos grupos
cat /etc/group



# criar tar.gz
tar -czvf arquivo.tar.gz pasta/

# extrair tar.gz
tar -xzvf arquivo.tar.gz

# compactar zip
zip arquivo.zip arquivo.txt

# descompactar zip
unzip arquivo.zip



| Flag | Significado                   |
| ---- | ----------------------------- |
| -t   | TCP                           |
| -u   | UDP                           |
| -l   | LISTEN (somente escutando)    |
| -n   | Mostra IPs e portas numéricas |
| -p   | Mostra PID/Programa associado |

