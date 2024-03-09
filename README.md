# Inteligência de Documentos

<div class="image">
  <img src="https://cdn.hashnode.com/res/hashnode/image/upload/v1684125403394/7344ad9e-9552-43c2-af05-d8916d5be076.jpeg" width="1000" height="500">
</div>

## Descrição do Projeto 📚

Este projeto utiliza o Azure AI Services juntamente com a Azure Search Service e uma Sorage Account da plataforma para executar um projeto de inteligência de documentos.

## Conjunto de Dados 💾

O conjunto de dados utilizado neste projeto são documentos no formato .docx providos pela própria Microsoft no [Link para os documentos](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/11-ai-search.html).

## Metodologia 📘

A primeira etapa do processo se trata de basicamente criar um novo **Resource** dentro do Microsoft Azure. Para isso, na página inicial do Azure, basta clicar em **"Create a Resource"**:

<div class="image">
  <img src="./Imagens_readme/pag_inicial.png"  width="700" height="300">
</div>

Na próxima etapa, basta clicar na barra de *search* e então pesquisar por **"Azure AI Search"**.

<div class="image">
  <img src="./Imagens_readme/img2.png" width="700" height="300">
</div>

Selecionar a **"Azure AI Search"** e clicar em *create*.

<div class="image">
  <img src="./Imagens_readme/img3.png" width="700" height="300">
</div>

Então basta dar um nome para sua **Research Group**, juntamente com um nome para o serviço, uma localização do servidor e definir o **Pricing Tier** para **Standard**.

<div class="image">
  <img src="./Imagens_readme/img4.png" width="700" height="300">
</div>

Na tela que aparece após a validação, basta clicar em **Create** para finalizar a criação da *Resource Group*.

<div class="image">
  <img src="./Imagens_readme/img5.png" width="700" height="300">
</div>

Caso tenha sido criada com sucesso, a mensagem **"Your deployment is complete"** irá aparecer, assim como da imagem abaixo.

<div class="image">
  <img src="./Imagens_readme/img6.png" width="700" height="300">
</div>

 A segunda coisa a se fazer, é criar uma **Azure AI services** assim como feito na aplicação de NLP. Para isso, na tela *home* do Azure, clique em *Create a resource*, e então na próxima tela marcar na parte esquerda da tela **"AI + Machine Learning"** e clicar em **Azure AI services**.

<div class="image">
  <img src="./Imagens_readme/img7.png" width="700" height="300">
</div>

O próximo passo é criar um **AI Service** usando a **Resource Group** criada anteriormente, dar um nome para a instancia a ser criada, selecionar um **Pricing Tier**, selecionar a **Checkbox** e então clicar em **Review + Create**.

<div class="image">
  <img src="./Imagens_readme/img8.png" width="700" height="300">
</div>

Após esperar um tempo, clicar em **Create** para finalizar a criação da **AI Service**.

<div class="image">
  <img src="./Imagens_readme/img9.png" width="700" height="300">
</div>

A imagem abaixo mostra o processo de criação bem sucessido.

<div class="image">
  <img src="./Imagens_readme/img10.png" width="700" height="300">
</div>

Para a última etapa, volte para a **home** do Azure, vá até a barra de pesquisa na parte superior central e digite por **Storage Account** para conseguir criar um local de armazenamento de dados no próprio Azure.

<div class="image">
  <img src="./Imagens_readme/img11.png" width="700" height="300">
</div>

Na próxima tela, clique em **Create storage account**.

<div class="image">
  <img src="./Imagens_readme/img12.png" width="700" height="300">
</div>

Então, forneça os campos marcados com, respectivamente, o nome de sua **Resource Group** criada na etapa 1 do processo, um nome para sua **Storage account**, a região em que os dados serão armazenados, para *performance* selecione **Standard**, e na parte de **Redundancy** selecione **Locally-redundant storage (LRS)** e clique em **Review + create**.

<div class="image">
  <img src="./Imagens_readme/img13.png" width="700" height="300">
</div>

Na próxima tela, basta clicar em **Create**.

<div class="image">
  <img src="./Imagens_readme/img14.png" width="700" height="300">
</div>

Caso a criação de sua **Storage account** tenha sido sucedida, a mensage de **"Your deployment is complete"** será mostrada.

<div class="image">
  <img src="./Imagens_readme/img15.png" width="700" height="300">
</div>

Nas configurações finais da **Storage account**, volte até a *home* do Azure e clique nela.

<div class="image">
  <img src="./Imagens_readme/img16.png" width="700" height="300">
</div>

Vá até a aba **Configurações** na parte esquerda da tela e desca até a parte de **settings** e marque como **enabled** a parte de **Allow blob anonymous access**.

<div class="image">
  <img src="./Imagens_readme/img17.png" width="700" height="300">
</div>

Suba a rolagem da tela até a parte de **Data Storage** e selecione **Containers**, e então clique no ícone **+ Container** para criar um novo *Container*.

<div class="image">
  <img src="./Imagens_readme/img18.png" width="700" height="300">
</div>

Na aba que irá abrir, dê o nome de **"coffeereviews"** para o *container*, na opção **"Anonymous access level"** selecione **"Container (anonymous read access for containers and blobs)"** e então clique em **Create**.

<div class="image">
  <img src="./Imagens_readme/img19.png" width="700" height="300">
</div>

Com isso, basta fazer o *download* dos documentos do link citado na parte de **Conjunto de Dados**, clicar m sua **Storage account** criada, e então clicar em **upload**, arrastar os documentos ou selecioná-los manualmente em seu computador, conforme mostram as duas próximas imagens.

<div class="image">
  <img src="./Imagens_readme/img20.png" width="700" height="300">
</div>

<div class="image">
  <img src="./Imagens_readme/img21.png" width="700" height="300">
</div>

Para utilizar, finalmente, a função de inteligência de documentos, basta voltar para a *home* do Azure e selecionar novamente sua **Azure AI services**

<div class="image">
  <img src="./Imagens_readme/img22.png" width="700" height="300">
</div>

Então clique em **Import data**.

<div class="image">
  <img src="./Imagens_readme/img23.png" width="700" height="300">
</div>

E então selecione a opção **"Azure blob storage"** que a **Storage account** criada anteriormente aparecerá para ser selecionada.

<div class="image">
  <img src="./Imagens_readme/img24.png" width="700" height="300">
</div>

Agora, basta voltar até sua **Azure AI services** e clicar na aba **Search explorer** para realizar a pesquisa de inteligência de documentos.

<div class="image">
  <img src="./Imagens_readme/img25.png" width="700" height="300">
</div>

Por fim, uma tela assim como a mostrada na imagem abaixo aparecerá e a busca poderá ser efetuada, usando, por exemplo, um filtro como marcado no primeiro retangulo vermelho para identificar alguma coisa dentro de seu documento.

<div class="image">
  <img src="./Imagens_readme/img26.png" width="700" height="300">
</div>

## Repositório do Projeto

[![Repo Card](https://github-readme-stats.vercel.app/api/pin/?username=Gauss99&repo=dio_inteligencia_de_documentos&bg_color=000&border_color=30A3DC&show_icons=true&icon_color=30A3DC&title_color=E94D5F&text_color=FFF)](https://github.com/Gauss99/dio_inteligencia_de_documentos)

## Conclusão

Com esse projeto, foi possível explorar outras ferramentas dentro do Ecossistema Azure, empregando a inteligência de documentos para encontrar palavras e textos chaves em um documento, além de aprender a criar sua própria "base de armazenamento" dentro do Microsoft Azure.
