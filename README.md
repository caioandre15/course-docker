# Curso de Docker

### Comandos úteis:  

``docker compose up -d --build``

O comando docker compose up -d --build é usado para construir e iniciar serviços definidos em um arquivo de configuração do Docker Compose. Aqui está o que cada parte do comando faz:

docker compose: Este é o comando principal para interagir com o Docker Compose, que é uma ferramenta para definir e executar aplicativos multi-container usando Docker.

up: Este é um subcomando que instrui o Docker Compose a iniciar e criar os serviços definidos no arquivo de configuração.

-d: Essa opção significa "detached" (desanexado). Ela faz com que os serviços sejam iniciados em segundo plano, ou seja, sem anexar o terminal ao processo. Isso permite que você continue usando o terminal para outros comandos.

--build: Essa opção instrui o Docker Compose a construir novamente as imagens dos serviços, mesmo que já existam imagens pré-construídas. Isso é útil quando você fez alterações no código-fonte ou no Dockerfile e deseja garantir que as imagens sejam atualizadas antes de iniciar os serviços.

Portanto, quando você executa docker compose up -d --build, o Docker Compose irá:

1. Construir as imagens dos serviços conforme definido no arquivo de configuração do Docker Compose, mesmo que já existam versões pré-construídas.
2. Iniciar os serviços em segundo plano, permitindo que você continue a usar o terminal para outras tarefas.
Isso é especialmente útil ao desenvolver e testar aplicativos em um ambiente local, onde você deseja que as alterações no código sejam refletidas nas imagens e serviços Docker sem ter que recriar todo o ambiente manualmente.

``docker system prune``  

O comando docker system prune é usado para limpar e remover vários recursos do Docker que não estão sendo utilizados. Ele ajuda a liberar espaço em disco removendo containers, redes e imagens que não estão mais em uso. Aqui está o que o comando faz:

1. Containers: Remove todos os containers parados. Containers que estão atualmente em execução não são removidos.

2. Redes: Remove todas as redes que não estão sendo usadas por nenhum container.

3. Imagens: Remove imagens que estão "penduradas" (não utilizadas e não referenciadas por nenhum container) e também imagens que não estão associadas a nenhuma imagem marcada com tags.

4. Volumes: Remove volumes que não estão sendo usados por nenhum container.

5. Cache de Compilação: Remove o cache de compilação que não foi usado recentemente.

Esse comando é útil para limpar recursos que acumulam ao longo do tempo e não são mais necessários. No entanto, tenha cautela ao usar esse comando, especialmente em ambientes de produção, pois ele pode remover recursos de forma irreversível. É uma boa prática revisar quais recursos serão excluídos antes de confirmar a operação. Você pode adicionar a opção --volumes ao comando (docker system prune --volumes) para incluir a remoção de volumes também.

