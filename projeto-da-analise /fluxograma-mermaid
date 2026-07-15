```mermaid
flowchart TD

%% ===== Estilos =====
classDef start fill:#f8d7da,stroke:#333,stroke-width:2px;
classDef process fill:#dbeafe,stroke:#333,stroke-width:1px;
classDef automation fill:#dcfce7,stroke:#333,stroke-width:1.5px,stroke-dasharray:5 5;
classDef decision fill:#fff7cc,stroke:#c99a00,stroke-width:2px;

%% ===== Fluxo =====
Start([Entrada do Pedido]) --> Form[Canal de Entrada<br/>(Google Forms ou E-mail)]

subgraph Triagem["Automação n8n - Triagem"]
    Form --> Trigger{Trigger n8n}
    Trigger --> IA[IA - Validação dos Dados]
end

IA -->|Dados OK| Design[Design]
IA -->|Dados incompletos| Revisao[Solicitar Correção]
Revisao --> Form

subgraph Operacao["Operação"]
    Design --> DesignOK{Design concluído?}
    DesignOK -->|Sim| Producao[Produção]

    Producao --> ProducaoOK{Produção concluída?}
    ProducaoOK -->|Sim| Logistica[Logística]
end

subgraph Comunicacao["Automações n8n"]
    DesignOK -.-> NotProd[Notificação para Produção]
    ProducaoOK -.-> NotLog[Notificação para Logística]
    Logistica -.-> NotCliente[Notificação para Cliente]
end

Logistica --> End([Entrega Realizada])

%% ===== Aplicação dos estilos =====
class Start,End start;
class Design,Producao,Logistica process;
class Trigger,IA,NotProd,NotLog,NotCliente automation;
class DesignOK,ProducaoOK decision;
```
