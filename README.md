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
