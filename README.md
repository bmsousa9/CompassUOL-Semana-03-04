![Static Badge](https://img.shields.io/badge/STATUS-Em_Desenvolvimento-FFC000)
># Sprint 3 e 4 - Kubernetes 
<div align="center"> <img src="https://github.com/bmsousa9/CompassUOL-Semana-02/assets/111213549/82e1324e-9b45-4ebe-8604-3f4eb29c8fe1" width="400px" /> </div>



># Desafio 1 ![Static Badge](https://img.shields.io/badge/STATUS-Resolvido-2e8b57)
Fazer o restore das VMs e instalar o minikube ou S3 para utilizar o kubernetes



### Restaurar a VM utilizada na Sprint 2


Restaurei novamente a VM01 da <a href="https://github.com/bmsousa9/CompassUOL-Semana-02#instala%C3%A7%C3%A3o-do-docker" target="_blank" rel="noopener noreferrer"> Sprint 2</a> até ao ponto seguinte ao da congiduração do ip fixo, lá no Oracle VM Virtual Box e clonei a VM01.
<div align="center"> <img src="https://github.com/bmsousa9/images/assets/111213549/6d32a090-243e-42f7-af7d-ef3d0fffa460"/> </div>


### Instalar o K3S


O primeiro passo foi atualizar o serviço DNF.
```
dnf update -y
```
<div align="center"> <img src="https://github.com/bmsousa9/CompassUOL-Semana-03-04/assets/111213549/b68b5d33-c462-4d97-be60-3f778a87c6ea"/> </div>
<div align="center"> <img src="https://github.com/bmsousa9/CompassUOL-Semana-03-04/assets/111213549/0fa04f08-6b6c-4011-be81-03bee751adf5"/> </div>

Tentei instalar o MiniKube como, porém meu equipamento não atende aos pré-requisitos. Por isso parti para instalar o `K3S`.
```
cd ~; curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
install minikube-linux-amd64 /usr/local/bin/minikube
minikube start --driver=podman
```
<div align="center"> <img src="https://github.com/bmsousa9/CompassUOL-Semana-03-04/assets/111213549/9aa2b797-ddfc-4e27-b269-fadc40bcf1f7"/> </div>

Para instalar o `K3S`, inseri o comando abaixo no terminal:
```
curl -sfL https://get.k3s.io | sh - 
```
<div align="center"> <img src="https://github.com/bmsousa9/CompassUOL-Semana-03-04/assets/111213549/13a44e33-9e8d-4bfd-9875-3e65f78fa03e"/> </div>
<div align="center"> <img src="https://github.com/bmsousa9/CompassUOL-Semana-03-04/assets/111213549/f7e5f81e-9758-4392-b8ce-dd31ccaf820c"/> </div>
<div align="center"> <img src="https://github.com/bmsousa9/CompassUOL-Semana-03-04/assets/111213549/7bdf07b8-edb8-4ae2-82d1-61465a630ffe"/> </div>

Com a instalação feita, pude verificar o status da instalação do `K3S`.
```
systemctl status k3s
```
<div align="center"> <img src="https://github.com/bmsousa9/CompassUOL-Semana-03-04/assets/111213549/b51d75f6-2149-42d8-9cb5-0ba552f21689"/> </div>

Para conseguir ver a lista dos nós que estão no cluster, inseri o comando abaixo:
```
kubectl get nodes
```
<div align="center"> <img src="https://github.com/bmsousa9/CompassUOL-Semana-03-04/assets/111213549/e07b2bf9-7206-445e-9011-feb8974af633"/> </div>

Para atualizar a linha de comando `kubectl`:
```
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
```
<div align="center"> <img src="https://github.com/bmsousa9/CompassUOL-Semana-03-04/assets/111213549/60a104f6-5552-4208-9322-8dcfbd24742a"/> </div>

Esse comando vai garantir que a versão que está sendo utilizada é compatível com cluster kubernetes.
```
kubectl version --client
```````
<div align="center"> <img src="https://github.com/bmsousa9/CompassUOL-Semana-03-04/assets/111213549/0b824480-7b63-4ee5-8e44-d7c07957257e"/> </div>

Com tudo isso finalmente funcionando, vamos ao Desafio 2.



># Desafio 2 ![Static Badge](https://img.shields.io/badge/STATUS-Em_Desenvolvimento-FFC000)
Deploy k8s cluster com 1 master e 1 node (ou 2 masters) no Oracle Linux configurando o ingress e fazendo o deploy do jenkins. Persistencia de dados é opcional para esse desafio



### Ajustar o Ingress Controller


O primeiro passo é fazer a configuração do `Ingress Controller`
```
ENTRA
```
<div align="center"> <img src=""/> </div>

># Desafio 3 ![Static Badge](https://img.shields.io/badge/STATUS-Ainda_ser%C3%A1_Iniciado-red)
Deploy k8s cluster com 2 masters usando kubespray no Oracle Linux, configurar o ingress, configurar o rancher no kubernetes, configurar postgresql com persistencia de dados
