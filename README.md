## Trabalho para disciplina Dev. Web do 4º período de Sistemas de Informação - API de fluxo de oficina
### Projeto de API Rest com CRUD de memória

Proposta: Uma oficina está precisando melhorar o processo de fluxo de veículos dentro da oficina. Para isso, ela precisa de uma API REST para as seguintes operações: CRUD (Create, Retrieve, Update e Delete) do registro de manutenção, contendo os dados do veículo, nome do cliente, nome do mecânico e data e hora de chegada do veículo. Deve ter uma operação para atualizar o horário de finalização da manutenção. Deve listar todos os veículos que estão em manutenção na oficina no momento. Por fim deve permitir excluir uma manutenção que foi incluída mas ainda não foi finalizada. Os dados devem ser gravados em memória e vão existir enquanto a aplicação existir.

#### Criar um novo registro
Regra de negócio: Não deixar cadastrar mais de um registro por placa de veículo

POST /registros 
body:
```json
{
    "nome_motorista": "João",
    "placa_veiculo": "ABC123",
    "nome_mecanico": "José",
}
```
#### Listar todos os veículos no pátio
GET /registros 
body: vazio

#### Atualizar o registro com a data e hora de saída
PATCH /registros/:placa/finalizar

body: vazio

#### Excluir registros não finalizados
Só pode excluir um registro se ele não foi atualizado com data e hora de saída

DELETE /registros/:placa/excluir

body: vazio

#### Listar registros não finalizados
GET/registros/nao_finalizados

body: vazio
