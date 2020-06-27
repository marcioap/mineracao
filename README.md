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
root@ rede :/home/marcio/ Documentos# docker-compose up
