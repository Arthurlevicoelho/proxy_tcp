# Ferramenta Proxy

Este projeto é uma ferramenta proxy baseada em Python, projetada para interceptar e modificar o tráfego entre um cliente local e um servidor remoto. Ela permite aos usuários analisar, manipular e encaminhar pacotes de rede para testes e depuração.

## O que é um Proxy?

Um **proxy** é um intermediário entre um cliente e um servidor que redireciona e gerencia o tráfego entre os dois. Ele atua como um ponto de acesso para enviar e receber informações, podendo interceptar, inspecionar, modificar e registrar o tráfego de rede. 

### Serventia de um Proxy:

- **Segurança**: Proxies podem ser usados para proteger redes privadas, mascarar endereços IP e prevenir acesso não autorizado.
- **Testes e Depuração**: Auxiliam desenvolvedores e analistas a monitorar e manipular tráfego de rede para identificar problemas ou comportamentos inesperados.
- **Controle de Acesso**: Podem bloquear ou permitir determinados tipos de tráfego com base em regras pré-configuradas.
- **Cache**: Melhoram a performance ao armazenar em cache respostas frequentes do servidor para uso futuro.
- **Análise de Dados**: Facilitam a coleta e inspeção de informações para diagnósticos ou auditorias.

## Funcionalidades

## Funcionalidades

- **Intercepção de Pacotes**: Captura o tráfego de um cliente para um servidor e vice-versa.
- **Exibição em Hexdump**: Visualiza os dados em um formato legível (hexdump) para análise fácil.
- **Modificação de Pacotes**: Adiciona lógica personalizada para manipular requisições e respostas.
- **Multi-threaded**: Lida com múltiplas conexões simultaneamente usando threads.

## Pré-requisitos

- Python 3.x

## Instalação

1. Clone o repositório por ssh:
   ```bash
   git clone git@github.com:Arthurlevicoelho/proxy_tcp.git
   ```
2. Navegue até o diretório do projeto:
   ```bash
   cd proxy_tcp
   ```
3. Torne o script executável:
   ```bash
   chmod +x proxy.py
   ```

## Uso

Execute a ferramenta proxy com o seguinte comando:

```bash
./proxy.py [localhost] [localport] [remotehost] [remoteport] [receive_first]
```

### Exemplo

```bash
./proxy.py 127.0.0.1 9000 10.12.132.1 9000 True
```

### Argumentos

- `localhost`: O endereço IP para escutar localmente.
- `localport`: A porta para escutar localmente.
- `remotehost`: O endereço IP do servidor remoto.
- `remoteport`: A porta do servidor remoto.
- `receive_first`: Define se os dados do servidor remoto devem ser recebidos antes de serem enviados ao cliente local (use `True` ou `False`).

## Visão Geral das Funções

### Hexdump

Exibe a comunicação entre as máquinas local e remota em formato hexadecimal:
```python
def hexdump(src, length=16, show=True):
    # Detalhes da implementação...
```

### Recebimento de Dados

Recebe dados de uma conexão:
```python
def receive_from(connection):
    # Detalhes da implementação...
```

### Manipuladores de Pacotes

Adicione lógica personalizada para manipular requisições e respostas:
```python
def request_handler(buffer):
    return buffer

def response_handler(buffer):
    return buffer
```

### Manipulador Proxy

Gerencia a comunicação entre o cliente e o servidor:
```python
def proxy_handler(client_socket, remote_host, remote_port, receive_first):
    # Detalhes da implementação...
```

### Loop do Servidor

Escuta conexões de entrada e cria threads:
```python
def server_loop(local_host, local_port, remote_host, remote_port, receive_first):
    # Detalhes da implementação...
```

## Licença

Este projeto está licenciado sob a Licença MIT. Consulte o arquivo LICENSE para mais detalhes.
