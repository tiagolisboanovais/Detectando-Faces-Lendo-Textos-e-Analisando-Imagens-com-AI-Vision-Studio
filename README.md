# Detectando Faces, Lendo Textos e Analisando Imagens com AI Vision Studio

A proposta deste repositório é trazer um tutorial passo a passo para exemplificar a utilização do Azure AI Services, onde iremos detectar faces, ler textos e analisar imagens.

A iniciativa da criação deste repositório foi para registrar a resolução do exercício 'Trabalhando com Visão Computacional' que é parte do curso [Microsoft Azure AI Fundamentals](https://web.dio.me/track/microsoft-azure-ai-fundamentals) fornecido pela Digital Innovation One - [DIO](https://www.dio.me/), este em preparação para a certificação AI-900: Microsoft Azure AI Fundamentals.

Espero poder ajudar todos aqueles que por ventura vierem a este repositório.


## Apresentação dos Problemas

Iremos trabalhar com os seguintes problemas:

1. Detectando faces com o Visual Studio
2. Lendo textos com o Visual Studio
3. Analisando imagens com o Visual Studio

Todos os problemas são apresentandos pela Microsoft Learn com os respectivos títulos ['Detect faces in Vision Studio'](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/04-face.html), ['Read text in Vision Studio'](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/05-ocr.html) e ['Analyze images in Vision Studio'](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/03-image-analysis.html).

1. Detectando faces com o Visual Studio

> "As soluções de visão geralmente exigem que a IA seja capaz de detectar rostos humanos. Suponha que a empresa varejista fictícia Northwind Traders queira localizar onde os clientes estão em uma loja para melhor atendê-los. Uma maneira de fazer isso é determinar se há algum rosto nas imagens e, em caso afirmativo, retornar as coordenadas da caixa delimitadora que mostram sua localização.

> Para testar as capacidades de deteção facial do serviço Azure AI Face, utilizará o Azure Vision Studio. Esta é uma plataforma baseada em UI que permite explorar os recursos do Azure AI Vision sem a necessidade de escrever nenhum código."

2. Lendo textos com o Visual Studio

> Neste exercício, você usará o serviço Azure AI para explorar os recursos de reconhecimento óptico de caracteres do Azure AI Vision. Você usará o Vision Studio para experimentar extrair texto de imagens, sem precisar escrever nenhum código.

> Um desafio comum da visão computacional é detectar e interpretar texto incorporado em uma imagem. Isso é conhecido como reconhecimento óptico de caracteres (OCR). Neste exercício, você usará um recurso de serviços de IA do Azure, que inclui serviços do Azure AI Vision. Em seguida, você usará o Vision Studio para testar o OCR com diferentes tipos de imagens.

3. Analisando imagens com o Visual Studio

> Neste exercício, você usará o Vision Studio para analisar imagens usando as experiências de teste integradas. Suponhamos que o retalhista fictício Northwind Traders tenha decidido implementar uma “loja inteligente”, na qual os serviços de IA monitorizam a loja para identificar os clientes que necessitam de assistência e direcionam os funcionários para os ajudar. Ao utilizar o Azure AI Vision, as imagens captadas por câmaras em toda a loja podem ser analisadas para fornecer descrições significativas do que representam.


## Pré-requisitos para resolução do problema

* Ter uma conta do Microsoft Azure. (Caso você não tenha um conta será necessário criar, para isto siga os passos que serão apresentados abaixo)

* Ter muita vontade e disposição para aprender.


#### Passo a Passo para criar a conta no Microsoft Azure

* Acesse o site da [Microsoft Azure](https://azure.microsoft.com/pt-br/free/search/?ef_id=_k_CjwKCAiA_aGuBhACEiwAly57MQIxpbuFTl1YFmHB1o36Rq5fAlKA8JO9CdOLPuyq_oV_3JBza8E_-hoC4OAQAvD_BwE_k_&OCID=AIDcmmzmnb0182_SEM__k_CjwKCAiA_aGuBhACEiwAly57MQIxpbuFTl1YFmHB1o36Rq5fAlKA8JO9CdOLPuyq_oV_3JBza8E_-hoC4OAQAvD_BwE_k_&gad_source=1&gclid=CjwKCAiA_aGuBhACEiwAly57MQIxpbuFTl1YFmHB1o36Rq5fAlKA8JO9CdOLPuyq_oV_3JBza8E_-hoC4OAQAvD_BwE)
* Clique em Experimente gratuitamente ou no botão Início gratuito.
* Será necessário colocar os dados de sua conta da Microsoft, que em geral é de um e-mail da hotmail ou outlook.
* Siga os passos conforme solicitado.

**OBS**: Será necessário cadastrar um cartão de crédito para aderir ao plano gratuito, inicialmente você terá $200 dólares de crédito ou 30 dias para testar os serviços, prevalecendo o que acabar primeiro.

## Passo a Passo para resolver o problema

Agora que você já tem uma conta da Microsoft Azure, vamos começar:

### Resolvendo o problema número 1

1. Acesse o [Portal da Azure](https://portal.azure.com/) para começar a resolver o problema.

2. Na aba Azure Services procure por 'Create a Resource'.

![Create a Resource](https://i.ibb.co/XXZsckw/Create-a-Resource.png)

3. Em seguida pesquise por Azure AI Services. 

![Azure AI Services](https://i.ibb.co/HrJq3PZ/Azure-AI-Services.png)

4. Clicaremos em create

![Create Azure AI Services](https://i.ibb.co/Y2V8Rrb/Create-Azure-AI-Services.png)

5. Então colocaremos as seguintes informações e clique em Review + create: 

> **Subscription:** Aqui é a sua inscrição do Microsoft Azure, se você estiver com uma conta gratuita, provavelmente apareça ela como padrão.

> **esource group:** Criar ou selecionar um Grupo de Recursos. (Como provavelmente você não terá um Grupo de Recursos para selecionar, deverá criar um clicando no botão create new, então deverá colocar um nome para o mesmo e clicar em ok. Experimente colocar **LABTesteNomeRG**, onde LAB é Laboratorio e RG é Resource Group)

> **Region:** Sugiro você colocar a região East US. Que é a mais próximo com custo mais baixo.

> **Name:** Entrar com um nome único para seu Workspace. Neste caso aqui sugiro colocar **labvisionstudio**, mas pode ser qualquer nome a sua escolha.

> **Pricing tier:** Selecionar Standard S0

> Marcar a caixa 'By checking this box I acknowledge that I have read and understood all the terms below' 

![Informações Azure AI Services](https://i.ibb.co/4Yn7Mpv/Informa-es-Azure-AI-Services.png)

6. Clique em create e espere terminar o deployment.

![Create AI Services](https://i.ibb.co/rmBmWXk/Create-AI-Services.png)

7. Após a conclusão o deployment estará completo.

![Deployment completo](https://i.ibb.co/ss64v5s/Deployment-completo.png)

8. Agora iremos acessar o Portal Azure AI Vision Studio, para isso [clique aqui](https://portal.vision.cognitive.azure.com/). Após o acesso clicaremos em View all resources.

![View all resources](https://i.ibb.co/L68rrDy/View-all-resources.png)

9. Selecionaremos o recurso **labvisionstudio** criado anteriormente e definiremos como default clicando no botão 'Select as default resource'. Você irá perceber que aparentemente não acontecerá nada, pois continuará na mesma tela, mas é assim mesmo.

![labvisionstudio](https://i.ibb.co/mc5hy59/select-as-default-resource.png)

10. Voltaremos ao portal inicial do AI Vision Studio. Abaixo clicaremos na aba Face e então em Detect faces in an image.

![Detect faces](https://i.ibb.co/smP0qRV/Detect-Faces.png)

11. Em try out, marcaremos a caixa 'I acknowledge ...'. Então poderemos selecionar a imagem para que a aplicação identifique a quantidade de faces/rostos que estão na imagem, para isso clique em 'Browse for a file'. As imagens que iremos selecionar esta na pasta input aqui neste repositório do github, baixe para seu computador para poder realizar o upload.

![Browse for a file](https://i.ibb.co/C8szr7P/Browse-for-a-file.png)

12. Neste primeiro exemplo iremos selecionar a imagem 'Homem Loiro.jpg'. Observe a quantidade de faces/rostos que foi identificado.

![Resultado homem loiro](https://i.ibb.co/n6kYYpH/Resultado-homem-loiro.png)

12. Neste segundo exemplo iremos selecionar a imagem 'Jovens.jpg'. Observe a quantidade de faces/rostos que foi identificado.

![Resultado jovens](https://i.ibb.co/MS2Vv4p/Resultado-jovens.png)

Aqui terminamos a resolução do primeiro problema, verificamos o poder do serviços AI Vision Studio de identificar faces nas imagens, através de uma API o desenvolvedor pode implementar isso em uma aplicação.

### Resolvendo o problema número 2

Como já estamos dentro do portal da Azure AI Vision Studio, iremos seguir a partir do passo 10 da resolução do problema número 1.

1. No portal inicial do AI Vision Studio. Clicaremos na aba Optical character recognition e então em Extract text from images.

2. Em try out, marcaremos a caixa 'I acknowledge ...'. Então poderemos selecionar a imagem para que a aplicação identifique a quantidade de faces/rostos que estão na imagem, para isso clique em 'Browse for a file'. As imagens que iremos selecionar esta na pasta input aqui neste repositório do github, baixe para seu computador para poder realizar o upload.

![Browse for a file 2](https://i.ibb.co/JjJx08W/Browse-for-a-file-2.png)

3. Neste primeiro exemplo iremos selecionar a imagem 'Escrito mao.jpg'. Observe a quantidade o texto que foi extraido da imagem.

![Resultado Escrito a mao](https://i.ibb.co/3Rjg68f/Resultado-escrito-a-mao.png)

4. Neste segundo exemplo iremos selecionar a imagem 'texto.jpg'. Observe a quantidade o texto que foi extraido da imagem.

![Resultado texto](https://i.ibb.co/DCC12V1/Resultado-texto.png)

Aqui terminamos a resolução do segundo problema, verificamos o poder do serviços AI Vision Studio de extrair textos de imagens, através de uma API o desenvolvedor pode implementar isso em uma aplicação.

### Resolvendo o problema número 3

Como já estamos dentro do portal da Azure AI Vision Studio, iremos seguir a partir do passo 10 da resolução do problema número 1.

1. No portal inicial do AI Vision Studio. Clicaremos na aba Image analysis e então em Add captions to images.

2. Em try out, marcaremos a caixa 'I acknowledge ...'. Então poderemos selecionar a imagem para que a aplicação identifique a quantidade de faces/rostos que estão na imagem, para isso clique em 'Browse for a file'. As imagens que iremos selecionar esta na pasta input aqui neste repositório do github, baixe para seu computador para poder realizar o upload.

![Browse for a file 3](https://i.ibb.co/cy3wq6w/Browse-for-a-file-3.png)

3. Neste primeiro exemplo iremos selecionar a imagem 'Paisagem1.jpg'. Observe a descrição que será feita da imagem.

![Resultado Paisagem 1](https://i.ibb.co/R2yJfq5/Resultado-paisagem-1.png)

4. Neste segundo exemplo iremos selecionar a imagem 'texto.jpg'. Observe a descrição que será feita da imagem.

![Resultado Paisagem 2](https://i.ibb.co/ZmgmkJM/Resultado-paisagem-2.png)

Aqui terminamos a resolução do terceiro problema, verificamos o poder do serviços AI Vision Studio de identificar o que está na imagem, através de uma API o desenvolvedor pode implementar isso em uma aplicação.


Parabéns! Você fez todo o processo!



## Meus Contatos

[![LinkedIn](https://img.shields.io/badge/LinkedIn-000?style=for-the-badge&logo=linkedin&logoColor=0E76A8)](https://www.linkedin.com/in/tiagolisboanovais/)

[![Instagram](https://img.shields.io/badge/instagram-000?style=for-the-badge&logo=instagram&logoColor=0E76A8)](https://www.instagram.com/tiagolisboa.ti/)

[![E-mail](https://img.shields.io/badge/-Email-000?style=for-the-badge&logo=microsoft-outlook&logoColor=007BFF)](mailto:tiagolisboanovais)

[![Github](https://img.shields.io/badge/github-000?style=for-the-badge&logo=github&logoColor=0E76A8)](https://github.com/tiagolisboanovais)



