# 🏝️ Agente de Viagens para Parintins

Este repositório contém um agente de viagens para Parintins, desenvolvido em Python. O agente utiliza a API do OpenAI GPT-3.5-turbo, a Wikipédia como fonte de informações, e é capaz de fornecer preços de passagens aéreas, barcos e lanchas, além de sugestões de hospedagem e pontos turísticos.

## ✨ Funcionalidades

- 🔍 Pesquisa de eventos e preços de passagens.
- 🏨 Sugestões de hospedagem e pontos turísticos em Parintins.
- 📅 Geração de um roteiro de viagem detalhado.

## 📋 Requisitos

- 🐍 Python 3.7 ou superior
- 🌐 Conta na OpenAI para acesso à API do GPT-3.5-turbo

## 🛠️ Instalação

## Passo a Passo

1. **Clone este repositório:**
   ```bash
   git clone https://github.com/seu-usuario/agente-de-viagens-parintins.git
   cd agente-de-viagens-parintins
   ```
   ```bash
   python -m venv venv
   source venv/bin/activate  # Para Windows, use `venv\Scripts\activate`
   ```
## Instale as dependências:
 ```
pip install langchain_openai langchain_community langchain beautifulsoup4 requests
```
## Configure a variável de ambiente OPENAI_API_KEY:

## No terminal (Unix/Mac):
```
export OPENAI_API_KEY='sua-chave-aqui'
```

## No terminal (Windows):
```
set OPENAI_API_KEY='sua-chave-aqui'
```

## Ou configure diretamente no código Python:
```import os
os.environ['OPENAI_API_KEY'] = 'sua-chave-aqui'
```

## 🚀 Uso

Para testar o agente de viagens localmente, você pode usar o script agente_de_viagens.py.
Adicione o seguinte código ao final do arquivo para testar:

 ```bash
    if __name__ == "__main__":
    event = {
        'body': json.dumps({
            'question': 'Vou viajar para Parintins em agosto de 2024. Quero que faça um roteiro de viagem para mim com eventos que irão ocorrer na data da viagem e com o preço de passagem de São Paulo para Parintins.'
        })
    }
    context = {}
    response = lambda_handler(event, context)
    print(response)
```

Depois, execute o script:

 ```bash
    python agente_de_viagens.py
 ```

🗂 **Estrutura do Código:**

- researchAgent: 🔍 Pesquisa eventos e preços de passagens.
- loadData: 📚 Carrega dados da Wikipédia sobre Parintins.
- getRelevantDocs: 📄 Obtém documentos relevantes para a consulta do usuário.
- supervisorAgent: 📝 Gera o roteiro de viagem detalhado usando o contexto da pesquisa e os documentos relevantes.
- getResponse: 🔄 Coordena as funções acima para fornecer a resposta final.
- lambda_handler: 🚦 Função de entrada para integração com AWS Lambda ou outras plataformas de serverless.

### 🤝 Contribuições
Contribuições são bem-vindas! Por favor, abra uma issue ou envie um pull request para melhorias ou correções.

### 📜 Licença
Este projeto está licenciado sob a MIT License.
