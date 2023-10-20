# Diagrama-de-classe-umc


```mermaid
classDiagram
  class Cliente {
    - nome: String
    - usuario: String
    - rg: String
    - cpf: String
    - endereco: String
    - profissao: String
    - empresa: String
    - salario: Double
    + cadastrar(): void
    + alugar(): void
    + modificarAluguel(): void
    + cancelarAluguel(): void
    + selecionarContrato(): void
  }

  class Sistema {
    - pedidosDeContrato: List<Contrato>
    + cadastrar(cliente: Cliente): void
    + remover(cliente: Cliente): void
    + adicionar(cliente: Cliente): void
    + selecionarPedido(): void
    + coletaDados(): void
    + gestaoDePedidosDeContrato(): void
  }

  class Contrato {
    - dataDeAluguel: Date
    - automovel: Automovel
  }

  class Automovel {
    - placa: String
    - matricula: String
    - ano: Int
    - marca: String
    - modelo: String
  }

  class Agente {
    + gerenciarContrato(contrato: Contrato): void
    + aprovarContrato(contrato: Contrato): void
    + reprovarContrato(contrato: Contrato): void
    + modificarContrato(contrato: Contrato): void
    + avaliarContrato(contrato: Contrato): void
  }

  Cliente -- Sistema: possui 1
  Sistema -- Contrato: possui n
  Agente -- Contrato: gerencia n
  Contrato -- Automovel: possui 1
