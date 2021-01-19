![Windows](https://upload.wikimedia.org/wikipedia/pt/e/e0/Windows_logo.png)
# Procedimento de instalação Windows
### Configuração

Antes de iniciar a instalação e configuração do cluster de Kubernetes aplique ajustes no arquivo do Vagrantfile e no sistema operacional. Segue abaixo os ajustes necessários:

- bridge: Adicionar o nome da interface de rede do Windows = Acesse o powershell/prompt e digite o comando abaixo para obter o nome da interface:

```
ipconfig
```
*Obs.: O nome da interface deve ser o que está com o IP do seu computador (rede local)*


- chaves SSH: Crie um diretório ".ssh" no home do usuário do Windows e adicione as chaves neste diretório (id_rsa / id_rsa.pub);


### Iniciando a instalação e configuração
Para iniciar a instalação e configuração do cluster de Kubernetes, acesse o diretório onde está o arquivo Vagrantfile e execute o comando abaixo:

```
vagrant up
```

Aguarde alguns minutos para o término da criação do cluster. Ao final do processo, acesse o servidor "Master" e copie o comando que estará presente no arquivo "kubeadm_join.sh". Acesse os servidores nós e execute o comando utilizando o "sudo".

Aguarde alguns segundos para que os nós sejam adicionados ao cluster. Para validar se os nós estão prontos para serem utilizados execute o comando abaixo no servidor "Master":

```
kubectl get nodes -o wide
```

*Obs.: O status dos servidores devem estar como "Ready"*
