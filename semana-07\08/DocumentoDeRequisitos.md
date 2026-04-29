# Documento de Requisitos de Software (SRS)  
---
## Informações do Projeto  

| Campo            |	Descrição  |  
|------------------|-------------|
| Nome do Projeto: |	Sistema Hotel Bela Vista  |  
| Dono do Projeto: |  Hotel Bela Vista  |  
| Versão	      |   1.0      |  
| Data             |	16/04/2026  |  

---

# 1. Introdução  
O objetivo deste documento é descrever os requisitos para o desenvolvimento do Software Sistema Hotel Bela Vista. O sistema visa substituir a atual gestão analógica, este documento servirá como guia para a equipe de desenvolvimento, garantindo que todas as características e funcionalidades necessárias sejam implementadas conforme as expectativas dos stakeholders.  

# 2. Escopo
O escopo do Sistema Hotel Bela Vista inclui, mas não se limita às seguintes funcionalidades:  


    • Controle de reservas e ocupação de quartos em tempo real.
    • Gestão de consumo de frigobar e serviços adicionais para evitar perdas financeiras.
    • Monitoramento do status de limpeza dos quartos para otimização do trabalho da governança.
    • Geração de relatórios financeiros mensais de faturamento e despesas.

    
## 3. Requisitos Funcionais  
## 3.1 Funcionalidade 1  
| ID	| Gestão de Hóspedes e Reservas |
|-----|------------------------|
| RF 1.1 |	Cadastro e Validação: Realizar o registro de hóspedes coletando nome, CPF e telefone, com validação automática dos dados para evitar erros de digitação. |  
| RF 1.2	| Controle de Ocupação: Efetuar check-in e check-out de forma automática, além de gerenciar o calendário de reservas para impedir que dois hóspedes ocupem o mesmo quarto simultaneamente |  
| RF 1.3	| Flexibilidade de Estadia: Permitir a alteração de datas das reservas para atender hóspedes que desejam estender sua permanência. |  

## 3.2 Funcionalidade 2  
| ID |	Operações e Governança  |
|-----|------------------------|
| RF 2.1 |	Monitoramento de Status: Informar visualmente se cada quarto está livre, ocupado ou se necessita de limpeza. |  
| RF 2.2 |	Identificação de Acomodações: Diferenciar facilmente os tipos de quartos (Simples, Suíte Luxo e Família) no mapa do sistema para evitar erros de alocação. |  
| RF 2.3 |	Gestão de Consumo: Registrar os produtos contidos no frigobar para que a equipe possa verificar o consumo antes da saída do cliente. |  
| RF 2.4 |	Automação de Cálculos: Realizar o cálculo automático do valor total da estadia somado ao consumo do hóspede, eliminando o uso de calculadoras manuais. |  
| RF 2.5 |	Relatórios Financeiros: Registrar todas as entradas (faturamento) e saídas (despesas) do hotel para facilitar o fechamento do lucro ao final do mês. |  


## 4. Requisitos Não Funcionais
    • RNF 4.1: Garantia de persistência de dados em servidor para evitar perdas por queda de energia ou falhas locais.
    • RNF 4.2: Validação rigorosa de dados de entrada para evitar erros de digitação.
    • RNF 4.3: Interface intuitiva com "mapa de quartos" visual, utilizando cores para status.
    • RNF 4.4: Disponibilidade do sistema 24/7 com manutenções em horários de baixo movimento.

## 5. Design da Interface do Usuário (UI)  
A interface será focada em um "Painel de Controle" ou mapa visual dos quartos. Cada quarto será representado por um bloco colorido indicando seu status (Livre: Verde, Ocupado: Vermelho, Sujo: Amarelo) e seu tipo . O fluxo de navegação permitirá realizar o cadastro de hóspedes e o check-out com poucos cliques, priorizando a agilidade no balcão. 

graph LR
    subgraph "Fronteira do Sistema de Logística"
        UC1((Gerenciar Despacho))
        UC2((Consultar Estoque))
        UC3((Verificar Status Transportadora))
        UC4((Solicitar Emissão de NF))
    end

    UC1 --> UC2
    UC1 --> UC3
    UC1 --> UC4

    Transportadora((Transportadora)) --- UC3
    ReceitaFederal((Receita Federal)) --- UC4

 
