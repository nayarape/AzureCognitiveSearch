# Desafio: Utilizando Azura AI Search para  Consulta de Dados

## 📜 Projeto

O desafio consiste em criar um serviço de **AI Search** para a indexação e consulta de dados, utilizando **aprendizado de máquina** e **processamento de linguagem natural**. Esse serviço visa fornecer uma busca inteligente e contextual, otimizando a experiência do usuário e acelerando o processo de tomada de decisões ao transformar dados brutos em informações valiosas e facilmente acessíveis.

---

## 🚀 Passo a Passo

### 1. **Cadastro na Azure**

- Realize o login na plataforma **Azure**.

### 2. **Baixar o arquivo "zipped coffee reviews"**

![zip](https://github.com/nayarape/AzureCognitiveSearch/blob/main/imagemsearch/documentozip.png)


---

### 3. **Criando os Recursos na Azure**

#### 3.1 **AI Search - Serviço de Busca**

1. Entre no AI Services, pesquise e selecione **AI Search**.
2. Clique em **+ Criar** para criar um novo recurso.
3. Preencha as informações solicitadas:
   - Escolha a **Assinatura** e o **Grupo de Recursos** que você já fez anteriormente.
   - Preencha o  **Nome do Serviço**.
   - Selecione o **Local** e coloque o básico na seção de  **Camada de preços**.
4. Clique em **Revisar + Criar** e depois em **Criar**.

   ![img1](https://github.com/nayarape/AzureCognitiveSearch/blob/main/imagemsearch/1.png)

   ![img2](https://github.com/nayarape/AzureCognitiveSearch/blob/main/imagemsearch/2.png)

#### 3.2 **Azure AI Serviços**

1. No painel do Azure, pesquise e selecione **Azure AI Serviços**.
2. Clique em **+ Criar**.
3. Preencha as informações:
   - Selecione um **Grupo de Recursos**.
   - Em **Detalhes da Instância**: escolha **East US** para a **Local** e defina um nome para a instância.
   - Selecione **Standard S0** em tarifa de preço .
4. Clique em **Revisar + Criar** e depois em **Criar**.

   ![img3](https://github.com/nayarape/AzureCognitiveSearch/blob/main/imagemsearch/3.png)

#### 3.3 **Conta de Armazenamento**

1. No painel do Azure, pesquise e selecione **Contas de Armazenamento**.
2. Clique em **+ Criar**.
3. Preencha as informações:
   - Utilize um já existenteno **Grupo de Recursos** e assinale sua assinatura.
   - Escolha um nome único no **Nome da conta de armazenamento**
   - Em **Região**: Selecione **East US**.
   - Em **Desempenho**: Selecione **Standard**.
   - Em **Redundancy**: Selecione **Locally redundant storage (LRS)**.
4. Clique em **Revisar + Criar** e depois em **Criar**.

   ![img4](https://github.com/nayarape/AzureCognitiveSearch/blob/main/imagemsearch/4.png)
   ![img5](https://github.com/nayarape/AzureCognitiveSearch/blob/main/imagemsearch/5.png)

 **Depois de criar a Conta de Armazenamento:**
- Vá nas configurações e habilite a opção **Permitir acesso anônimo ao Blob** 
- Crie um **Container** e faça o upload do arquivo **zipped coffee reviews** baixado anteriormente

  ![img6](https://github.com/nayarape/AzureCognitiveSearch/blob/main/imagemsearch/anonimo.png)
  ![img7](https://github.com/nayarape/AzureCognitiveSearch/blob/main/imagemsearch/7.png)

---

### 4. **Importação de Dados e Testes**

1. No **AI Search**, selecione o recurso que já foi criado
2. Vá em **Importar Dados** 
3. Siga as instruções da [documentação oficial](https://learn.microsoft.com/en-us/azure/search/index-documents) para indexar os documentos.

![img8](https://github.com/nayarape/AzureCognitiveSearch/blob/main/imagemsearch/8.png)
---

### 5. **Pesquisa de Dados**

Após a importação, clique em **Explorador de Pesquisas** e faça suas pesquisas. 

- **Filtro 1**: `search=locations:'Chicago'`

  ![img9](https://github.com/nayarape/AzureCognitiveSearch/blob/main/imagemsearch/9.png)


---

## 🎯 **Resultados da busca**

### Filtro 1: `search=locations:'Chicago'`

{
  "@odata.context": "https://pesquisa1.search.windows.net/indexes('azureblob-index')/$metadata#docs(*)",
  "@odata.count": 9,
  "value": [
    {
      "@search.score": 0.6888268,
      "content": "Review: Today I was truly disappointed with how long I had to wait for the pastries I ordered ahead of time. When I got my box, some of the pastries seemed stale. Terrible experience!  \nDate: October 23, 2018\nLocation: Chicago, Illinois \n\n",
      "metadata_storage_path": "aHR0cHM6Ly9wZXNxdWlzYTAwMS5ibG9iLmNvcmUud2luZG93cy5uZXQvY29mZmVlcmV2aWV3cy9yZXZpZXctOC5kb2N40"
    },
    {
      "@search.score": 0.51101947,
      "content": "\nReview: I often make Fourth Coffee my meeting spot for my client meetings weekday mornings. I own a small business and the folks who work at Fourth Coffee are always very friendly. It leaves a good impression on my clients. There are also plenty of drink selections, good wi-fi, and seating. Some of my favorite coffees are the lavender honey latte and, in the winter, the apple-chai latte. There are delicious baked goods offered as well. \nDate: October 21, 2018\nLocation: Chicago, Illinois \n\nimage1.png\n\n",
      "metadata_storage_path": "aHR0cHM6Ly9wZXNxdWlzYTAwMS5ibG9iLmNvcmUud2luZG93cy5uZXQvY29mZmVlcmV2aWV3cy9yZXZpZXctNS5kb2N40"
    },
    {
      "@search.score": 0.5053692,
      "content": "\n\nReview: The coffee tastings every Wednesday afternoon are so fun. Each month there is a new drink theme. You do need to book a spot in advance to attend. It is very worth it! I also love their local music. Fourth Coffee brings in rising artists every weekend. I like to head over there mid-afternoon on weekdays when it’s not too busy and get a slice of pie or their seasonal baked goods.  \nDate: August 13, 2018\nLocation: Chicago, Illinois  \n\nimage1.png\n\nimage2.png\n\n",
      "metadata_storage_path": "aHR0cHM6Ly9wZXNxdWlzYTAwMS5ibG9iLmNvcmUud2luZG93cy5uZXQvY29mZmVlcmV2aWV3cy9yZXZpZXctNC5kb2N40"
    },
    {
      "@search.score": 0.3847533,
      "content": "\n\nReview: The great thing about this Fourth Coffee location is that there’s an event space for talks. I went to one the other day that focused on giving students a place to present their latest research. The event room is also perfect for larger groups or clubs to meet up. Just be aware that weekends it can get really crowded, which I don’t like. \nDate: October 11, 2018\nLocation: Los Angeles, California\t\nimage1.png\n\nimage2.png\n\n",
      "metadata_storage_path": "aHR0cHM6Ly9wZXNxdWlzYTAwMS5ibG9iLmNvcmUud2luZG93cy5uZXQvY29mZmVlcmV2aWV3cy9yZXZpZXctNy5kb2N40"
    },
    {
      "@search.score": 0.27587286,
      "content": "\n\n\nReview: My favorite part about going to Fourth Coffee is the atmosphere. I love the warm lights and plants. It’s a great place to go get a cup of coffee while working on your next business idea or with friends at school. It’s also right next to the University hub, which makes it so easy to access for students. It just gets so busy on the weekends! I wish it was not so crowded. Since they started offering amazing breakfast sandwiches, I wouldn’t try to go get a coffee Saturday morning.  \nDate: September 1, 2018\nLocation: Los Angeles, California \nimage1.png\n\nimage2.png\n\n",
      "metadata_storage_path": "aHR0cHM6Ly9wZXNxdWlzYTAwMS5ibG9iLmNvcmUud2luZG93cy5uZXQvY29mZmVlcmV2aWV3cy9yZXZpZXctMi5kb2N40"
    },
    {
      "@search.score": 0.25962192,
      "content": "\n\n\nReview: Fourth Coffee has super options for food on the go. There is a big variety of boxed lunches that can be ordered in bulk as conference meals or purchased individually. My Mondays are always busy, and I like being able to get my meals to-go with them. I usually call ahead instead of trying to order online. The only issue is they run out of the most popular menu items quickly, so be sure to call ahead! \nDate: October 8, 2018  \nLocation: Seattle, Washington\nimage1.png\n\nimage2.png\n\n",
      "metadata_storage_path": "aHR0cHM6Ly9wZXNxdWlzYTAwMS5ibG9iLmNvcmUud2luZG93cy5uZXQvY29mZmVlcmV2aWV3cy9yZXZpZXctMy5kb2N40"
    },
    {
      "@search.score": 0.24187452,
      "content": "\nReview: What I really like about this location is that there are also art classes offered for children! My family loves to come to Fourth Coffee on weekends for the live music and paint events! Some of the best events my kids have been to are at Fourth Coffee on a rainy Saturday. Hopefully they will bring back the Melodies & Collage Memories event, that was a great time for our whole family. \nDate: October 14, 2018\nLocation: Seattle, Washington  \nimage1.png\n\nimage2.png\n\n",
      "metadata_storage_path": "aHR0cHM6Ly9wZXNxdWlzYTAwMS5ibG9iLmNvcmUud2luZG93cy5uZXQvY29mZmVlcmV2aWV3cy9yZXZpZXctNi5kb2N40"
    },
    {
      "@search.score": 0.1776772,
      "content": "Review: I heard that Fourth Coffee had the best seasonal donuts, so I ordered a dozen for my team for an event. Everyone loved them, I’ll definitely order again! \nDate: October 25, 2018\nLocation: Seattle, Washington \n\n",
      "metadata_storage_path": "aHR0cHM6Ly9wZXNxdWlzYTAwMS5ibG9iLmNvcmUud2luZG93cy5uZXQvY29mZmVlcmV2aWV3cy9yZXZpZXctOS5kb2N40"
    },
    {
      "@search.score": 0.17314059,
      "content": "\n\nReview: I love the coffee drinks here, but my favorite part is the local art they sell. There are many kinds of paintings and watercolors they showcase each week. I love checking out the new prints that they have and buying cards for friends. Also did I mention that the wi-fi is excellent? \nDate: September 3, 2018\nLocation: Seattle, Washington  \nimage1.png\n\nimage2.png\n\n",
      "metadata_storage_path": "aHR0cHM6Ly9wZXNxdWlzYTAwMS5ibG9iLmNvcmUud2luZG93cy5uZXQvY29mZmVlcmV2aWV3cy9yZXZpZXctMS5kb2N40"
    }
  ]
}
