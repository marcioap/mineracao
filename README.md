# Etapas para implementação no DEBIAN
# Acesso com usuário específico para instalação de pacotes
marcio @ rede: ativ$ su
# Atualizar o Sistema
root@rede: ativ#  apt-get  update
# Verificar as dependências
root@rede: ativ#  sudo apt install apt-transport-https ca-certificates curl gnupg2 software-properties-common 
# Configurar o repositório
root@rede: ativ # curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add -
# Instalar o docker
root@rede: ativ#  apt-get install docker-ce docker.io docker-compose -y
# Crie o diretório ANACONDA dentro de Documentos
root@ rede :/home/marcio/ Documentos# mkdir anaconda
# Acessar o diretório Anaconda
root@ rede :/home/marcio/ Documentos# cd anaconda
# Com todos arquivos: Dockerfile, docker-compose.yml, requirements.txt dentro do Diretorio anaconda. Execute:
root@ rede :/home/marcio/Documentos/anaconda# docker-compose up
# Será gerado um link para acesso ao Anaconda / Jupyter. Ex:localhost:8888
No meu caso, como utilizei uma máquina virtual gerou: 10.0.2.15:8888
# Com o jupyter aberto, crie um arquivo: e então, só importa as bibliotecas do Python:
# Neste caso importaremos os pacotes e o dataset
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sbn
%matplotlib inline
dados = pd.read('pasta onde se encontra o dataset')
# Visualisar o dados do data set
  dataset.head()
# Tratar dados para os valores nulo / branco ficarem com valor 0
 dataset.fillna(dataset.mean(0))
# Verificar se houve a alteração
dataset.isnull() . sum()
# Informações sobre os atributos
dataset.info()
# Geração de graficos / Histograma
dataset[mensalidade].hist(bins=30)

