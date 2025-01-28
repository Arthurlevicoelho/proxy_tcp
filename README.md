# Ferramenta Proxy

Este projeto é uma ferramenta proxy baseada em Python, projetada para interceptar e modificar o tráfego entre um cliente local e um servidor remoto. Ela permite aos usuários analisar, manipular e encaminhar pacotes de rede para testes e depuração.

## Funcionalidades

- **Intercepção de Pacotes**: Captura o tráfego de um cliente para um servidor e vice-versa.
- **Exibição em Hexdump**: Visualiza os dados em um formato legível (hexdump) para análise fácil.
- **Modificação de Pacotes**: Adiciona lógica personalizada para manipular requisições e respostas.
- **Multi-threaded**: Lida com múltiplas conexões simultaneamente usando threads.

## Pré-requisitos

- Python 3.x

## Instalação

1. Clone o repositório:
   ```bash
   git clone https://github.com/seuusuario/proxy-tool.git
   ```
2. Navegue até o diretório do projeto:
   ```bash
   cd proxy-tool
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

## Problemas Conhecidos

- Certifique-se de que as portas que você está vinculando não estejam já em uso.
- Pode ser necessário ter permissões para vincular a determinadas portas.
- A função `hexdump` possui um erro de digitação (`translete` deve ser `translate`). Corrija isso para um funcionamento adequado.

## Contribuição

Contribuições são bem-vindas! Se você encontrar algum problema ou tiver ideias para melhorias, fique à vontade para abrir uma issue ou enviar um pull request.

## Licença

Este projeto está licenciado sob a Licença MIT. Consulte o arquivo LICENSE para mais detalhes.

## Autor

[Seu Nome](https://github.com/seuusuario)

---

Fique à vontade para personalizar as funções `request_handler` e `response_handler` conforme a sua necessidade!

