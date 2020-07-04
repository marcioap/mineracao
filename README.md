# PROJETO PPGCA / TÉCNICAS DE PROGRAMAÇÃO
O projeto é um análise exploratória no dataset do PROUNI, disponível no sítio dadosabertos.gov.br.
Ao final da análise exploratório o dataset estará pronto para ser usado com diversos algoritmos de machine learnig para verificar a melhor acurácia / eficiência.
# Etapas para implementação no DEBIAN
# Acesso com usuário específico para instalação de pacotes
marcio @ rede: ativ$ su
![tela_user2](https://user-images.githubusercontent.com/17771257/86511789-b1ae6680-bdd2-11ea-989f-b3f1657f597d.JPG)
# Atualizar o Sistema
root@rede: ativ#  apt-get  update
![tela_update](https://user-images.githubusercontent.com/17771257/86512114-8da05480-bdd5-11ea-930e-ac9d308ed476.JPG)
# Verificar as dependências
root@rede: ativ#  sudo apt install apt-transport-https ca-certificates curl gnupg2 software-properties-common 
![tela_dependencias](https://user-images.githubusercontent.com/17771257/86512125-a6106f00-bdd5-11ea-8528-59237f3a818a.JPG)
# Configurar o repositório
root@rede: ativ # curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add -
![tela_repositorio_docker](https://user-images.githubusercontent.com/17771257/86512120-9db83400-bdd5-11ea-8b82-f02e6f56576b.JPG)
# Instalar o docker
root@rede: ativ#  apt-get install docker-ce docker.io docker-compose -y
![tela_docker](https://user-images.githubusercontent.com/17771257/86512253-d9073280-bdd6-11ea-8ce4-2b9df2489090.JPG)
# Crie o diretório ANACONDA dentro de Documentos
root@ rede :/home/marcio/ Documentos# mkdir anaconda
![tela_anaconda](https://user-images.githubusercontent.com/17771257/86512262-dc9ab980-bdd6-11ea-9798-fbe287a4fb8b.JPG)
# Acessar o diretório Anaconda
root@ rede :/home/marcio/ Documentos# cd anaconda
![tela_ace_anaconda](https://user-images.githubusercontent.com/17771257/86512263-df95aa00-bdd6-11ea-95dd-af059ef91e01.JPG)
# Criar o arquivo Dockerfile - Estrutura / Configuração do arquivo:
![dockerfile](https://user-images.githubusercontent.com/17771257/86512271-f5a36a80-bdd6-11ea-8062-1df589c6d50a.JPG)
# Criar o arquivo docker-compose.yml - Estrutura / Configuração do arquivo:
![docker_compose](https://user-images.githubusercontent.com/17771257/86512268-f3411080-bdd6-11ea-8746-345501ec84f0.JPG)
# Criar o arquivo requirements - Estrutura / Configuração do arquivo:
![requirements](https://user-images.githubusercontent.com/17771257/86512272-f76d2e00-bdd6-11ea-9f0c-08af83db6223.JPG)
# Com todos arquivos: Dockerfile, docker-compose.yml, requirements.txt dentro do Diretorio anaconda. Execute:
root@ rede :/home/marcio/Documentos/anaconda# docker-compose up
![docker_compose_up](https://user-images.githubusercontent.com/17771257/86512528-6ba8d100-bdd9-11ea-9227-17e985cc0e70.JPG)
# Será gerado um link para acesso ao Anaconda / Jupyter. Ex:localhost:8888
No meu caso, como utilizei uma máquina virtual gerou: 10.0.2.15:8888
![tela_jupyter](https://user-images.githubusercontent.com/17771257/86512537-7ebba100-bdd9-11ea-8591-1685f9d3b7a6.JPG)
# Com o jupyter aberto, crie um arquivo: e então, só importa as bibliotecas do Python:
# Neste caso importaremos os pacotes e o dataset
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sbn
%matplotlib inline
dados = pd.read('pasta onde se encontra o dataset')
___________________________________________________________________________________________________________________
![bibliotecas](https://user-images.githubusercontent.com/17771257/86512829-cd6a3a80-bddb-11ea-88d6-60282098d115.JPG)
# Visualisar o dados do data set
  dataset.head()
  ![dados_head](https://user-images.githubusercontent.com/17771257/86512828-cc390d80-bddb-11ea-8e5f-cb249d11a9aa.JPG)
# Tratar dados para os valores nulo / branco ficarem com valor 0
 dataset.fillna(dataset.mean(0))
 ![tela2 - tratamento de dados](https://user-images.githubusercontent.com/17771257/86512543-8c712680-bdd9-11ea-9a17-eac738742bc5.JPG)
# Verificar se houve a alteração
dataset.isnull() . sum()
![tela3 - tratamento](https://user-images.githubusercontent.com/17771257/86512838-da872980-bddb-11ea-922f-b421cf74982f.JPG)
# Informações sobre os atributos
dataset.info()
![tela4](https://user-images.githubusercontent.com/17771257/86512549-998e1580-bdd9-11ea-845f-8529dab7655f.JPG)
# Geração de graficos / Histograma
dataset[mensalidade].hist(bins=30)
![tela5](https://user-images.githubusercontent.com/17771257/86512545-91ce7100-bdd9-11ea-9da7-2ba659b62562.JPG)

