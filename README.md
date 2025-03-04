# Desafio: Utilizando AI Search para Indexação e Consulta de Dados

## 📜 Sobre o Desafio

O desafio consiste em criar um serviço de **AI Search** para a indexação e consulta de dados, utilizando **aprendizado de máquina** e **processamento de linguagem natural**. Esse serviço visa fornecer uma busca inteligente e contextual, otimizando a experiência do usuário e acelerando o processo de tomada de decisões ao transformar dados brutos em informações valiosas e facilmente acessíveis.

---

## 🚀 Passos

### 1. **Cadastro na Azure**

- Realize o login na plataforma **Azure**.

### 2. **Baixar o arquivo "zipped coffee reviews"**

- O arquivo será utilizado na etapa de criação de Storage Accounts.

---

### 3. **Criar os Recursos na Azure**

#### 3.1 **AI Search - Serviço de Busca**

1. No painel do Azure, pesquise e selecione **AI Search**.
2. Clique em **+ Create** para criar um novo recurso.
3. Preencha as informações solicitadas:
   - Escolha o **Subscription** e **Resource Group**.
   - Defina um nome para o **Search Service**.
   - Selecione a **Region** e o **Pricing Tier**.
4. Clique em **Review + Create** e depois em **Create**.

#### 3.2 **Azure AI Services**

1. No painel do Azure, pesquise e selecione **Azure AI Services**.
2. Clique em **+ Create**.
3. Preencha as informações:
   - **Project Details**: Crie ou selecione um **Resource Group**.
   - **Instance Details**: Escolha **East US** para a **Region** e defina um nome para a instância.
   - **Pricing tier**: Selecione **Standard S0**.
4. Clique em **Review + Create** e depois em **Create**.

#### 3.3 **Storage Accounts - Conta de Armazenamento**

1. No painel do Azure, pesquise e selecione **Storage Accounts**.
2. Clique em **+ Create**.
3. Preencha as informações:
   - **Resource Group**: Crie ou utilize um já existente.
   - **Storage Account Name**: Escolha um nome único.
   - **Region**: Selecione **East US**.
   - **Performance**: Selecione **Standard**.
   - **Redundancy**: Selecione **Locally redundant storage (LRS)**.
4. Clique em **Review + Create** e depois em **Create**.

⚠️ **Após a criação da Storage Account:**
- Habilite a opção **Allow Blob anonymous access** nas configurações.
- Crie um **Container** e faça o upload do arquivo **zipped coffee reviews**.

---

### 4. **Importação de Dados e Testes**

1. No **AI Search**, selecione o recurso que foi criado na Etapa 1.
2. Clique em **Import Data** para importar os dados.
3. Siga as instruções da [documentação oficial](https://learn.microsoft.com/en-us/azure/search/index-documents) para indexar os documentos.

---

### 5. **Pesquisa de Dados**

Após a importação, realize buscas utilizando os filtros. Exemplo:

- **Filtro 1**: `search=locations:'Chicago'`
- **Filtro 2**: `search=sentiment:'negative'`

---

## 🎯 **Resultados Obtidos**

### Filtro 1: `search=locations:'Chicago'`

```json
{
  "results": [
    {
      "id": 1,
      "location": "Chicago",
      "review": "Great coffee, very smooth."
    },
    {
      "id": 2,
      "location": "Chicago",
      "review": "Good flavor, would visit again."
    }
  ]
}
