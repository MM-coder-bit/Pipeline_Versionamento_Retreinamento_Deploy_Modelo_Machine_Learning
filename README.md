# Desenvolvimento e Deploy de Modelos de Machine Learning

## Pipeline de Versionamento, Retreinamento e Deploy de Modelo de Machine Learning

![Python](https://img.shields.io/badge/Python-3.12-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)

## 🎯 Sobre o Projeto

Este projeto demonstra a construção de um pipeline de Machine Learning de ponta a ponta, cobrindo as etapas essenciais de MLOps (Machine Learning Operations). O objetivo é criar um fluxo de trabalho onde um modelo de classificação pode ser treinado, avaliado, versionado e disponibilizado para consumo através de uma API REST, com a capacidade de ser retreinado de forma automatizada.

---

## ✨ Principais Conceitos Abordados

* **Pipeline Automatizado:** Execução de cada etapa do ciclo de vida do modelo (pré-processamento, treino, avaliação, deploy) através de scripts independentes.
* **Versionamento:** Controle explícito da versão do modelo preparado para o deploy.
* **Retreinamento:** Capacidade de atualizar o modelo com novos dados de forma estruturada.
* **Deploy via API:** Disponibilização do modelo em um servidor Flask para consumo por outras aplicações.

---

## 📂 Estrutura do Projeto

```.
├── data/
│   └── raw\_data.csv            \# Dados brutos
├── models/
│   └── model.joblib            \# Modelo treinado e pronto para deploy
├── src/
│   ├── preprocessa\_dados.py
│   ├── treina\_modelo.py
│   ├── avalia\_modelo.py
│   ├── versiona\_modelo.py
│   ├── retreina\_modelo.py
│   ├── deploy\_modelo.py        \# Aplicação Flask (API)
│   └── cliente.py              \# Cliente para testar a API
├── requirements.txt
└── README.md
````

---

## 🛠️ Tecnologias Utilizadas

* **Linguagem:** Python 3.12
* **Bibliotecas de Machine Learning:** Scikit-learn, Pandas, NumPy
* **Servidor da API:** Flask
* **Serialização do Modelo:** Joblib

---

## 🚀 Como Executar o Projeto

Siga os passos abaixo para configurar e rodar o pipeline completo em sua máquina local.

### Pré-requisitos

* [Python 3.10+](https://www.python.org/downloads/)
* [Git](https://git-scm.com/downloads/)
* (Opcional, mas recomendado) [Conda](https://docs.conda.io/en/latest/miniconda.html)

### 1. Clonar o Repositório

```bash
git clone [https://github.com/MM-coder-bit/Pipeline_Versionamento_Retreinamento_Deploy_Modelo_Machine_Learning.git]

cd Pipeline_Versionamento_Retreinamento_Deploy_Modelo_Machine_Learning
````

### 2\. Criar e Ativar o Ambiente Virtual

```bash
# Criar o ambiente com Conda
conda create -n pipeline_ml python=3.12 -y

# Ativar o ambiente
conda activate pipeline_ml
```

### 3\. Executando o Pipeline Passo a Passo

Com o ambiente ativado, execute os scripts na ordem correta para completar o ciclo de vida do modelo.

**1. Instalar as Dependências**

```bash
pip install -r requirements.txt
```

**2. Pré-Processar os Dados**
Este script prepara os dados brutos para o treinamento.

```bash
python src/preprocessa_dados.py
```

**3. Treinar o Modelo Inicial**
Cria a primeira versão do modelo usando os dados processados.

```bash
python src/treina_modelo.py
```

**4. Avaliar o Modelo**
Verifica a performance do modelo treinado com métricas de avaliação.

```bash
python src/avalia_modelo.py
```

**5. Versionar o Modelo**
Prepara e salva a versão final do modelo para o deploy.

```bash
python src/versiona_modelo.py
```

**6. Retreinar o Modelo**
Simula o processo de retreinamento, que pode ser usado quando novos dados estiverem disponíveis.

```bash
python src/retreina_modelo.py
```

**7. Iniciar a API (Deploy)**
Este comando inicia o servidor Flask e expõe o modelo treinado em um endpoint.

```bash
python src/deploy_modelo.py
```

O servidor estará rodando em `http://127.0.0.1:5000`. **Mantenha este terminal aberto.**

**8. Testar a API com o Cliente**
Abra um **novo terminal**, ative o ambiente Conda novamente (`conda activate pipeline_ml`) e execute o cliente para fazer uma chamada de teste ao modelo.

```bash
python src/cliente.py
```

Você deverá ver a predição do modelo no console.

-----

## 💡 Próximos Passos e Melhorias

  * [ ] **Conteinerização:** Criar um `Dockerfile` para rodar a aplicação em um contêiner Docker.
  * [ ] **CI/CD:** Implementar um workflow com GitHub Actions para automatizar a execução do pipeline a cada commit.
  * [ ] **Versionamento de Dados:** Integrar [DVC (Data Version Control)](https://dvc.org/) para um controle mais robusto dos dados e modelos.
  * [ ] **Testes Automatizados:** Adicionar testes unitários para garantir a qualidade do código.

-----

## 👨‍💻 Autor

**Mateus Marques**

  * **GitHub:** [MM-coder-bit](https://github.com/MM-coder-bit)
  * **LinkedIn:** [mateus-j-marques](https://www.linkedin.com/in/mateus-j-marques)

<!-- end list -->