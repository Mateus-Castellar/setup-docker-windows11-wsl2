# **Setup Docker Windows 11 Com WSL2**

- Abra o terminal/powershell como administrador e rode o comando

```bash
wsl --install
```

- Reinicie seu computador

- Abra a Microsoft Store e instale a distro do ubuntu

- Quando iniciar a distro será pedido um usuario/senha que sera usado para permissoes de adm

# **Limitar Uso de Hardware do WSL2**

- Navegue atá sua pasta de usuario no C: e crie um arquivo com nome de **.wslconfig**, segue um exemplo de limitação de memoria e processamento:
```
[wsl2]
memory=2GB
processors=2
swap=2GB
```

- Salve o arquivo e reinicie o wsl para que as alterações sejam aplicadas
```
wsl --shutdown
```

# **Integrar WSL2 Com Docker**

- Instalar requisitos
```bash
sudo apt update && sudo apt upgrade
```

```bash
sudo apt remove docker docker-engine docker.io containerd runc
```

```bash
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```

- Setar repo do Docker
```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

```bash
echo \
  "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

- Docker Engine

```bash
sudo apt-get update
```

```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```

```bash
sudo usermod -aG docker $USER
```

# **Iniciar Docker**

- Reinicie o Ubuntu e digite o comando

```bash
sudo service docker start
```

esse comando sempre deverá ser usado para inicair o serviço, será pedido sua senha setada ao instalar a distro

- Para pausar o servico rode
```
sudo service docker stop
```

# **Referencias**

[Micrsoft Docs](https://learn.microsoft.com/pt-br/windows/wsl/install)
