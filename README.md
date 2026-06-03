# 🚚 JavaLog Express — Sistema de Controle de Frota e Logística

O **JavaLog Express** é um sistema central de controle e gerenciamento de frota desenvolvido para otimizar o cálculo de fretes e o registro de veículos de uma empresa de logística. O projeto foi construído como critério de avaliação final para consolidar os aprendizados do semestre na disciplina de **Programação Orientada a Objetos (POO)**.

O grande diferencial deste sistema é a aplicação rigorosa do paradigma de POO com **Tipagem Estrita em Java**, garantindo que as regras de negócio de cada categoria de veículo sejam processadas de forma isolada, segura e escalável, sem brechas para dados corrompidos.

---

## 🚀 Funcionalidades Principais

* ✅ **Especialização de Frota Inteligente**
Separação estrutural entre veículos de portes diferentes (Vans para entregas urbanas leves e Caminhões para transportes pesados de longa distância).
* 💸 **Cálculo de Frete Polimórfico**
O sistema calcula o custo do frete de forma dinâmica. O menu principal delega o cálculo para o próprio objeto, que responde conforme suas regras fiscais e operacionais específicas.
* 🛡️ **Garantia de Integridade de Carga**
Mecanismo de defesa no encapsulamento que impede o cadastro de veículos com capacidade de carga negativa ou zerada. Caso ocorra, o sistema redefine o valor automaticamente para um patamar seguro de 100 kg.
* 📊 **Relatório de Frota e Simulação em Tempo Real**
Listagem completa de todos os veículos operacionais da empresa com uma simulação automática de custos baseada em uma rota padrão de 100 km.
* ⌨️ **Interface Interativa via Terminal**
Menu interativo construído em console com tratamento de buffer de entrada, garantindo uma navegação fluida para o usuário.

---

## 🛠️ Pilares de POO Aplicados (Requisitos Técnicos)

### 🔹 Abstração & Herança

Criação da classe abstrata `Veiculo`, que serve de contrato e molde genérico para a frota, compartilhando os atributos privados (`placa`, `modelo`) e protegidos (`capacidadeCargaKg`) com as subclasses `Van` e `Caminhao` via palavra-chave `extends`.

### 🔹 Encapsulamento Rigoroso

Todos os atributos de estado são estritamente privados (`private`), blindando o acesso direto externo. A leitura e modificação segura ocorrem por meio de métodos seletores (*Getters*), enquanto as regras de consistência interna rodam em métodos utilitários privados (`capacityValida`).

### 🔹 Polimorfismo & Sobre-escrita (`@Override`)

O método abstrato `calcularCustoFrete(double distanciaKm)` é implementado de forma única nas classes filhas, respeitando as seguintes diretrizes:

* **Na classe Van:** Taxa base de R$ 2,50 por km. Caso a capacidade passe de 1000 kg, aplica-se uma taxa fixa extra de risco de R$ 30,00.
* **Na classe Caminhao:** Taxa base de R$ 4,50 por km, multiplicada de forma obrigatória pelo número de eixos do veículo para cobrir custos de pedágio.

### 🔹 Construtores com Cadeia de Inicialização

Uso obrigatório da instrução `super(...)` nas subclasses para garantir que os dados essenciais da plataforma mãe nasçam validados no momento da instanciação do objeto.

### 🔹 Coleções Dinâmicas (ArrayList)

Gerenciamento volátil de memória utilizando a estrutura genérica `List<Veiculo>`. Isso permite que a frota cresça indefinidamente em tempo de execução sem as limitações de tamanho fixo de um vetor comum.

---

## 📂 Estrutura de Arquivos

O projeto foi estruturado em um arquivo unificado de execução para facilitar a distribuição e avaliação acadêmica:

```text
/javalog-express
└── JavaLogExpressApp.java   # Contém a classe Abstrata Veiculo, as Subclasses e o Menu Principal

```

---

## ⚙️ Tecnologias Utilizadas

* **Java JDK**
* Paradigma de Orientação a Objetos Puro
* Classes Abstratas e Métodos Abstratos
* Sobrescrevibilidade com `@Override`
* Coleta de dados com `java.util.Scanner`
* Estrutura de dados com `java.util.ArrayList`



---

## 💻 Como Rodar o Projeto

### 1️⃣ Pré-requisitos

Certifique-se de ter o Java Development Kit (JDK) instalado em sua máquina.

### 2️⃣ Compilar o arquivo

Abra o terminal na pasta onde o arquivo `JavaLogExpressApp.java` está localizado e execute o comando:

```bash
javac JavaLogExpressApp.java

```

### 3️⃣ Executar o sistema

Após compilar sem erros, inicie a aplicação pelo terminal:

```bash
java JavaLogExpressApp

```

---

## 📸 Preview do Relatório (Case 3)

```text
--- RELATÓRIO DA FROTA E SIMULAÇÃO DE FRETE (Para 100km) ---
Veículo: Van | Placa: ABC-1234 | Modelo: Fiorino | Frete Simulado: R$ 250.0
Veículo: Caminhão | Placa: XYZ-9999 | Modelo: Volvo FH | Eixos: 3 | Frete Simulado: R$ 1350.0

```

---

## 📚 Objetivo Acadêmico

Projeto desenvolvido para consolidação dos critérios de avaliação do bimestre, focando em:

* Arquitetura de Software Orientada a Objetos
* Reutilização de código através de Herança
* Tratamento de regras de negócios mutáveis com Polimorfismo
* Segurança no fluxo de dados através de Encapsulamento
* Manipulação de coleções dinâmicas na memória RAM

---

## 👩‍💻 Desenvolvido por

**Samira Carvalho Toledo** Projeto Acadêmico — ETEC Zona Leste

Apostilas - Prof. Salomão
