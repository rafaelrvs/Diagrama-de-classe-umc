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
```

```mermaid
sequenceDiagram
    participant User
    participant System
    participant Database

    User->>System: Solicitação para Modificar Aluguel
    System->>Database: Consulta o Aluguel Atual
    Database-->>System: Retorna Dados do Aluguel
    System->>User: Exibe Dados do Aluguel Atual

    User->>System: Fornece Novos Dados do Aluguel
    System->>Database: Atualiza Aluguel no Banco de Dados
    Database-->>System: Confirmação de Atualização
    System-->>User: Confirmação de Modificação

    User->>System: Revisa Aluguel Modificado

```


# Digrama de redes



```mermaid
graph TD;
    subgraph "Inicio (1)"
        A[Inicio]
 
    end

    subgraph "  "
        B[Designer A - 1 dia ]
        C[Backend  B - 3 dias]
    end

    subgraph " "
        D[Frontend  A 2 dias ]
     
        G[Infra 1 dia]
        H[Frontend  B 2 dias ]
        K[Backend  A - 3 dias]
    
    end



    subgraph " "
       I[Banco de dados  1 dia ]
    
    end
    subgraph "Finalização"
        J[Fim]
    
    end

    A --> B
    A --> C
    B --> D
     D --> K
    G --> I
K --> G
    C --> H
    I --> J
    H --> G
    

 

  
 


```
