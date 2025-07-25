# Isaac — Voz, Dados e Inteligência Artificial com OpenAI

**Isaac** é um projeto que integra linguagem natural, análise de dados e interface de voz em um sistema inteligente e interativo. Utilizando a poderosa API da OpenAI, o sistema é capaz de interpretar comandos falados em português, consultar um conjunto de dados em tempo real via Pandas, e responder com fala sintetizada — criando uma experiência verdadeiramente conversacional com dados.

## O que este projeto faz

- **Escuta sua voz**: Ao pressionar `Ctrl+L`, o sistema inicia a gravação de voz. Solte para finalizar.
- **Transcreve seu áudio** usando o modelo **Whisper** da OpenAI.
- **Interpreta comandos** sobre um DataFrame real com um agente Langchain treinado em cima dos dados.
- **Responde com voz**: A resposta é gerada por uma LLM e sintetizada usando o TTS da OpenAI, transformando o texto em fala com voz natural.

## Tecnologias Utilizadas

- **LangChain**: Criação de agentes inteligentes baseados em dados com `create_pandas_dataframe_agent`.
- **OpenAI Whisper**: Transcrição de áudio em português com alta precisão.
- **ChatGPT (GPT-4o)**: Modelo responsável por interpretar os comandos sobre os dados.
- **TTS da OpenAI**: Conversão da resposta da LLM em áudio falado.
- **Pandas**: Manipulação e consulta de dados em DataFrames.
- **SoundDevice + SoundFile**: Gravação e reprodução de áudio.
- **Pynput**: Detecção de atalhos de teclado para controle por voz.

## Exemplo de uso

Imagine que você tenha um arquivo CSV com dados de aluguel (`df_rent.csv`) e deseja interagir com ele por voz. Basta dizer, por exemplo:

> "Qual é o valor médio do aluguel para apartamentos de dois quartos no Itaim Bibi?"

E ouvir a resposta falada pela IA, como:

> "O valor médio do aluguel para apartamentos com dois quartos no Itaim Bibi é de R$ 1.850,00."

## 📁 Estrutura do Projeto

| Arquivo           | Função principal |
|------------------|------------------|
| `talkingllm.py`  | Arquivo principal do sistema de interação por voz. Integra gravação, transcrição, agente de dados e TTS. |
| `df_agent.py`    | Demonstração de uso direto do agente Langchain sobre o DataFrame. |
| `df_rent.csv`    | Dataset de exemplo com dados de aluguel (não incluso por padrão). |
| `requirements.txt`| Dependências do projeto para instalação rápida via pip. |

## Instalação

Clone o repositório e instale as dependências com:

```bash
pip install -r requirements.txt
```

Crie um arquivo `.env` com sua chave da OpenAI:

```env
OPENAI_API_KEY=your_api_key_here
```

## Como rodar

```bash
python talkingllm.py
```

Pressione **Ctrl + L** para iniciar/parar a gravação. Aguarde a resposta falada.

## Diferenciais

- Suporte a **interação 100% em português**
- Integração completa com modelos de **voz, linguagem e dados**
- Pode ser facilmente adaptado para outros datasets e idiomas
- Arquitetura modular e extensível
