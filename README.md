# Atividade_API_REST

Primeiro, você deve abrir o Visual Studio ou outra IDE. Depois, criar uma estrutura de pastas onde cada microserviço deve ter uma pasta com um arquivo requirements.txt (onde estão as bibliotecas para o Docker baixar na hora da execução), um main.py (onde vai estar o microserviço em si) e um Dockerfile (que vai dizer para o Docker como montar o servidor, ou seja, qual linguagem, sua versão e a porta de rede que vai ser usada, mesmo que seja localhost). E fora dessas duas pastas, tem que estar o docker-compose.yml.


![Legenda da Imagem](./prints/print1.png)

Depois de preparar o ambiente, usando o PowerShell com o Docker instalado, você usará o docker-compose para subir os dois microserviços de uma vez, criando uma rede virtual e ele também vai garantir que um sistema não vai funcionar enquanto o outro não subir, para evitar que dê um erro de conexão no início.


![Legenda da Imagem](./prints/print2.png)
![Legenda da Imagem](./prints/print3.png)


Depois de subir os dois serviços, dá para usar o navegador ou o Postman (que é melhor para testes) para a execução, usando uma ID com o identificador do voo via rota e o ID do piloto via parâmetro de busca.


![Legenda da Imagem](./prints/print4.png)

#ERROS
Se na UID digitarmos um valor de ID de pioloto que não existe o serviço de Voos recebe vai receber a requisição, ele faz uma chamada interna para o serviço de Pilotos que quando não encontra um id correspondente retorna que o recurso não existe


![Legenda da Imagem](./prints/print5.png)

Se um dos serviços quando um dos serviço tentar "chamar" (fazer uma requisição) ao outro ele não vai encontrar nada e voltar 503. Da para testar isso forçando o docker a parar um dos serviços (se parar os dois 


![Legenda da Imagem](./prints/print6.png)
![Legenda da Imagem](./prints/print7.png)

*se os dois serviços caem a porta de rede ja é desabilitada e da outro erro connect ECONNREFUSED que não tem codigo porque o protocolo HTTP nem entrou em execução

![Legenda da Imagem](./prints/print8.png)


