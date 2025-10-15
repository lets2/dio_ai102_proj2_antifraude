# DIO - AI-102 - Projeto 2: Anti-fraude

Este projeto utiliza o **Azure Document Intelligence** para analisar imagens de cartões e determinar se o cartão é **válido ou inválido**.  
A aplicação é construída em **Python** com **Streamlit** e faz upload das imagens para o **Azure Blob Storage**, onde são processadas para extrair informações como:

- Nome do titular  
- Banco emissor  
- Data de validade  

---

## 🚀 Estrutura do Projeto

```
./
├── src/
│   ├── app.py
│   ├── services/
│   │   ├── blob_service.py
│   │   └── credit_card_service.py
├── .env.example
├── .env
├── requirements.txt
└── README.md
```

---

## ⚙️ Pré-requisitos

Antes de executar o projeto, é necessário ter os seguintes recursos configurados no **Microsoft Azure**:

- **Azure Blob Storage**
- **Azure Document Intelligence**

Além disso, é necessário possuir as seguintes credenciais e informações para autenticação:

```
ENDPOINT=
SUBSCRIPTION_KEY=
AZURE_STORAGE_CONNECTION_STRING=
CONTAINER_NAME=
```

> 💡 Um arquivo `.env.example` está disponível no repositório como modelo para criar o seu próprio `.env`.

---

## 🧩 Instalação

1. Clone o repositório:
   ```bash
   git clone https://github.com/lets2/dio_ai102_proj2_antifraude.git
   cd dio_ai102_proj2_antifraude
   ```

2. Crie e ative um ambiente virtual (opcional, mas recomendado):
   ```bash
   python -m venv venv
   source venv/bin/activate  # Linux/macOS
   venv\Scripts\activate   # Windows
   ```

3. Instale as dependências:
   ```bash
   pip install -r src/requirements.txt
   ```

4. Crie o arquivo `.env` na raiz do projeto com base no `.env.example`:
   ```bash
   cp .env.example .env
   ```

5. Preencha o `.env` com suas credenciais do Azure.

---

## ▶️ Execução

Para iniciar o aplicativo **Streamlit**, execute um dos comandos abaixo a partir da **raiz do projeto**:

```bash
streamlit run .\src\app.py
```
ou
```bash
python -m streamlit run .\src\app.py
```

---

## 🖼️ Funcionamento

1. Faça upload de uma imagem contendo um cartão de crédito (extensões: `.png`, `.jpg`, `.jpeg`).
2. A imagem será enviada automaticamente para o **Azure Blob Storage**.
3. O serviço **Document Intelligence** será chamado para extrair os dados.
4. O sistema validará se os campos principais estão presentes e exibirá:

   - ✅ **Cartão Válido** (com dados extraídos)
   - ❌ **Cartão Inválido**

---

## 🧠 Tecnologias Utilizadas

- **Python 3.10+**
- **Streamlit**
- **Azure Blob Storage**
- **Azure Document Intelligence**
- **dotenv**

