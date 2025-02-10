# Gemini 2.0 Flash: O RAG Tradicional Está Morto?

(conteúdo retirado desse vídeo e traduzido: https://www.youtube.com/watch?v=iK9wefkOjkY)

O Google lançou seu modelo mais recente, o Gemini 2.0 Flash, e provavelmente é o modelo com a melhor relação custo-benefício disponível hoje. Fiz uma postagem sugerindo que o RAG (Retrieval Augmented Generation ou Geração Aumentada por Recuperação) pode não ser mais necessário, e algumas pessoas interpretaram mal o que eu quis dizer, chegando até a ficar chateadas. Então, neste vídeo, vou esclarecer o que eu quis dizer. Vou abordar o RAG, por que acho que sua forma tradicional está se tornando obsoleta, como esses novos modelos de IA estão mudando o desenvolvimento de produtos de IA e o que isso significa para construtores e aqueles que estão começando em IA.

## O que é RAG?

Para aqueles que não estão familiarizados, RAG significa Geração Aumentada por Recuperação. É uma técnica que existe há algum tempo, usada para ajudar LLMs (Large Language Models ou Modelos de Linguagem Grandes) como o ChatGPT a acessar informações não presentes em seus dados de treinamento. Você vê isso com empresas como a Perplexity, onde eles aumentam suas perguntas durante as pesquisas na web. Além disso, quando você adiciona arquivos aos projetos do ChatGPT, o RAG está acontecendo nos bastidores.

## Janelas de Contexto e o Passado

Por trás dos bastidores, existe uma coisa chamada janelas de contexto. Janelas de contexto basicamente significam a quantidade de texto que você pode inserir em uma IA antes que ela não consiga responder. Em 2023, os limites de token eram significativamente menores, em torno de 4.000 tokens. Isso tornou o RAG muito importante.

## RAG Tradicional Explicado

A técnica tradicional de RAG envolvia:

*   **Chunking (Fragmentação):** Dividir grandes corpora de texto (arquivos, PDFs) em pedaços menores, aproximadamente 256 a 512 tokens (um parágrafo).
*   **Embedding (Incorporação):** Converter cada fragmento em uma incorporação.
*   **Banco de Dados Vetorial:** Armazenar essas incorporações em um banco de dados vetorial.
*   **Querying (Consulta):** Quando um usuário fazia uma pergunta, o sistema encontrava os fragmentos mais relevantes usando a pesquisa vetorial.
*   **Augmentation (Aumento):** Fornecer esses fragmentos ao LLM para ajudá-lo a responder à pergunta.

## O Que Mudou o Jogo: Janelas de Contexto Enormes

O problema que é resolvido pelas enormes janelas de contexto, é que anteriormente tínhamos apenas 4.000 token Els agora atualmente o limite de token é muito grande.
Você tem limites de token muito, muito grandes.
Hoje, os limites de token são muito maiores. O Gemini 2.0 possui janelas de contexto de 1 milhão a 2 milhões de tokens. Isso significa que você pode simplesmente dar à IA o documento inteiro e deixá-la raciocinar sobre ele.

*   **ChatGPT 3.5:** 4.000 tokens (aprox. 6 páginas)
*   **Gemini 2.0 Flash:** Mais de 1 milhão de tokens (uma quantidade substancial de texto)

## Taxas de Alucinação

O modelo mais recente do Gemini tem as menores taxas de alucinação. Alucinação se refere à probabilidade de um modelo de IA inventar coisas.

## RAG Está Morto (no Sentido Tradicional)

Quando eu disse que RAG está morto, eu quis dizer que a abordagem tradicional de pegar um único documento e dividi-lo em pequenos pedaços não é mais necessária para perguntas e respostas simples. Os trechos de código modernos para isso têm cerca de 20 linhas de código. Com ferramentas como o ChatGPT ou o Cursor Sonic, você pode codificar isso facilmente e fornecer um link direto para o PDF. O processo é muito mais fácil.

## "RAG Está Morto" - Explicado

Então, eu digo "RAG está morto" (entre aspas). Vamos analisar cenários onde dar o contexto diretamente ao modelo é melhor.

### Exemplo: Transcrição da Chamada de Resultados (50.000 tokens)

Imagine uma grande transcrição de uma chamada de áudio, como um relatório de resultados. O CEO discute finanças, tecnologia e perspectivas futuras. Digamos que tenha uma hora de duração, aproximadamente 50.000 tokens.

*   **Abordagem Tradicional (Ineficiente):** Você pode dividir isso em fragmentos menores de 512 tokens.
*   **Problema:** A fragmentação ingênua como essa impede que a IA raciocine sobre todo o conteúdo.

## Raciocínio vs. Descoberta de Fatos

No RAG, existem duas coisas principais:

1.  Posso encontrar os fatos e as informações
2.  Posso raciocinar sobre os dados

RAG é ruim no último.
O RAG tem dificuldades com o raciocínio sobre os dados. Em reg existem duas coisas principais: posso encontrar os fatos e as informações e posso raciocinar sobre os dados o problema com o rag hoje é que quando você está fragmentando e você está meio que incorporando, você não consegue raciocinar sobre as informações.

Com o RAG, você pode facilmente encontrar fatos simples ("Qual foi a receita líquida?"). Mas uma pergunta mais complexa requer raciocínio sobre toda a transcrição.
Você pode fazer uma pergunta carregada que requer raciocínio. você pode dizer Ok eu quero saber você sabe o que é a perspectiva, quero perguntar à IA, talvez seja um bom investimento, é um mau investimento agora para fazer isso, como você traduziria isso para encontrar os pedaços certos e quando você faz esse processo de fragmentação geralmente o que acontece é que você pega a consulta do usuário você basicamente tenta encontrar o mais semelhante os fragmentos de texto e então dar isso a um llm rag tradicional não funciona você não pode fazer isso.

Por exemplo: "Como a perspectiva de ganhos deles se compara a [Concorrente]?" ou "Este é um bom investimento?" Isso requer entender todo o contexto da chamada. O RAG tradicional (encontrar fragmentos semelhantes) não funcionará para isso.

## O Poder do Contexto Grande

Ao fornecer toda a transcrição de 50.000 tokens para o Gemini, ele pode:

*   Analisar a transcrição na íntegra.
*   Considerar as declarações do CEO, os números mencionados e as perguntas respondidas.
*   Raciocinar sobre o conjunto de dados completo.
*   Fornecer uma resposta significativamente melhor e mais precisa.

É por isso que eu disse "RAG killer": a prática de pegar um único documento/PDF e simplesmente responder a perguntas sobre ele está obsoleta.

## Exemplo Prático

Agora você pode arrastar e soltar documentos diretamente no Google AI Studio e perguntar ao Google. Eu recomendo fortemente que todos, se vocês tiverem esse tipo de documentos, por favor, vão para o Google e enviem porque vocês não vão obter resultados melhores.

## RAG em um Sentido Mais Amplo - Ainda Relevante

No entanto, o RAG em um sentido mais amplo porque existem tantas definições não está morto e eu vou dar um exemplo muito bom porque às vezes o que as pessoas vão dizer nos comentários eles estavam dizendo bem, e se eu tiver 100.000 documentos, e se eu tiver a teleconferência de resultados para 2023 e 2024 e 2025 e talvez eu tenha também por alguma razão em todos os meus arquivos que eu enviei para a IA eu tenho nvidias você sabe talvez eu esteja talvez essas transcrições sejam sobre a Apple talvez eu tenha nvidias e talvez eu tenha você sabe um monte de documentos irrelevantes e nesse caso o rag se aplica agora.
Então, quando você tem 100.000 documentos, o que você provavelmente vai querer fazer se eu tenho 100.000 documentos você sabe que eu provavelmente vou apenas pesquisar por eles eu não vou complicar as coisas eu vou pesquisar eu vou você sabe fazer um não um control F, mas há muitos sistemas de pesquisa existentes que vão te ajudar a encontrar então agora eu vou dizer ok olha eu encontrei todos os relatórios de ganhos da Apple ok ótimo isso é talvez 10 documentos, no entanto, eu ainda não iria em frente e fragmentá-los porque você está perdendo você não é capaz de raciocinar sobre isso e o que eu faria em vez disso é realmente eu jogaria todos os 10 documentos para o Google Gemini separadamente, então ok vamos apenas passar por um exemplo, digamos que eu tenho 10.000 documentos e eu preciso eu consegui filtrar para três agora o que eu gosto de fazer mais recentemente se você sabe que você não se importa muito em pagar um pouco mais como eu gosto de fazer é fazer paralelização e esta é uma técnica que eu meio que vi acontecer no Twitter e muitas pessoas meio que têm falado sobre isso mais recentemente com o lançamento do Deep Seek e praticamente o que você vai fazer é você vai você sabe encontrar seus três ou talvez cinco documentos mais relevantes e em vez de fragmentá-los e fazer aqueles 512 pequenos tokens porque os modelos de IA são tão baratos hoje em dia o que eu recomendaria é você pegar esses documentos e você jogar todos os três deles em paralelo para o Gemini do Google, então em vez de eu dizer ei eu vou pegar isso eu vou encontrar eu vou realmente pegá-los separadamente, a propósito, separadamente e eu vou fazer a eles a mesma pergunta e a diferença que você vai ver e você pode ir em frente e experimentar isso por conta própria quando você estiver recebendo perguntas respondidas seria Monumental.

## Quando o RAG Ainda é Valioso: Grandes Coleções de Documentos

O RAG permanece importante ao lidar com coleções enormes de documentos (por exemplo, 100.000 documentos, vários anos de chamadas de resultados, documentos irrelevantes misturados).

Neste caso:

*   **Pesquisa:** Use sistemas de pesquisa existentes para filtrar e identificar os documentos mais relevantes (por exemplo, todos os relatórios de resultados da Apple).
*   **Evite a Fragmentação:** Não fragmente esses documentos.
*   **Paralelize:** Use o Google Gemini e envie a eles uma pergunta do usuário e faça perguntas sobre um determinado documento.
*   **Paralelização:** Use o Google Gemini e envie a eles a pergunta de um usuário e faça perguntas sobre um determinado documento.
*   **Resposta Final:** Então, junte tudo isso e, finalmente, responda à pergunta do usuário para fazer o que quiser, esta não é uma nova técnica de forma alguma, isso é meio que um mapa reduzir onde você está filtrando e removendo todas as informações irrelevantes relevantes ok.

## Paralelização: Uma Abordagem Moderna

Encontre seus três ou talvez cinco documentos mais relevantes e em vez de fragmentá-los e fazer aqueles 512 pequenos tokens porque os modelos de IA são tão baratos hoje em dia o que eu recomendaria é você pegar esses documentos e você jogar todos os três deles em paralelo para o Gemini do Google, então em vez de eu dizer ei eu vou pegar isso eu vou encontrar eu vou realmente pegá-los separadamente, a propósito, separadamente e eu vou fazer a eles a mesma pergunta e a diferença que você vai ver e você pode ir em frente e experimentar isso por conta própria quando você estiver recebendo perguntas respondidas seria Monumental.

Este método envolve:

1.  Identificar 3-5 dos documentos mais relevantes (após a filtragem).
2.  Enviar cada documento *separadamente* para o Gemini com a mesma pergunta do usuário.
3.  Coletar as respostas de cada instância do Gemini.
4.  Mesclar/combinar essas respostas para fornecer uma resposta final abrangente ao usuário.

Pergunta do Usuário -> Documento 1 (Gemini) -> Resposta 1
-> Documento 2 (Gemini) -> Resposta 2
-> Documento 3 (Gemini) -> Resposta 3
-> Mesclar Respostas -> Resposta Final ao Usuário

## Isso NÃO é incorporação e fragmentação

Sistemas rag tradicionais é eu faço uma pesquisa e então eu vou pegar esses três documentos eu vou paralelizar eles eu vou pedir ao Google para olhar para todos eles separadamente pegar as respostas e finalmente pegar aquela resposta final e dar para outra IA e responder isso agora este é um sistema significativamente mais robusto e porque os modelos são tão mais baratos hoje em dia, a propósito, os modelos do Google são extremamente baratos se você está procurando por respostas de qualidade esta é a melhor maneira de fazer isso especialmente por causa de quão baixas são as taxas de alucinação e quão bem eles podem meio que encontrar encontrar as informações que você está encontrando então espero que isso explique a postagem aqui de rag está morto.

Este embed-and-chunk é o que os sistemas rag tradicionais são. Com a paralelização, pegue as respostas e finalmente pegue essa resposta final e dê para outra IA e responda. É um sistema significativamente mais robusto, e porque os modelos são tão mais baratos hoje em dia, os modelos do Google são extremamente baratos se você está procurando por respostas de qualidade esta é a melhor maneira de fazer isso especialmente por causa de quão baixas são as taxas de alucinação e quão bem eles podem meio que encontrar encontrar as informações que você está encontrando.

## Conclusão: Comece Simples e Não Complique Demais

Espero que isso explique a postagem de que o rag está morto um pouco mais e se você está olhando para construir rag ou fazer coisas eu apenas recomendo começar simples eu sinto que as pessoas gostam de complicar as coisas se você é um hobbyista solo apenas mantenha simples use coisas como você sabe enviar o arquivo para este sistema específico e apenas quando você precisa torná-lo mais complexo novamente eu acho que muitas pessoas vão gostar de adicionar complexidade quando não é necessário.
Eu recomendo começar simples. Use ferramentas onde você envie o arquivo diretamente para o sistema. Adicione complexidade apenas quando absolutamente necessário. Isso pode mudar em um ano. Talvez as coisas fiquem mais baratas e eficientes.
No sentido tradicional, porque não é possível raciocinar sobre todos os dados para fornecer uma resposta suficiente, então é tudo por hoje espero que isso tenha dado a vocês um pouco mais de compreensão de por que o rag no sentido tradicional não funciona e por que novamente o modelo do Google do Gemini é tão forte e útil, especialmente para esse tipo de casos de uso, se você está construindo um produto se você mesmo é como um analista e você quer ler todos os documentos o novo modelo do Google muito útil.

O método tradicional é obsoleto porque não raciocina bem sobre os dados. O Gemini é uma boa solução, especialmente para esses casos de uso.

## Bônus: Misture e Combine Modelos de IA

Outra coisa a acrescentar quando você faz este passo ok você diz dando todas essas coisas você pode meio que misturar e combinar os modelos de IA, mas se você realmente quisesse você diz ei olha eu vou pegar um modelo realmente muito barato eu vou pedir para ele olhar para todos esses documentos dar suas respostas e eu vou pegar essas respostas e dar para 01 Pro ou 03 você sabe que eu posso dar para um modelo muito mais inteligente do que tentar conseguir que o modelo de IA escolha os pedaços certos, isso simplesmente não funciona.
Você pode combinar modelos de IA. Você pode pegar as saídas desses modelos e alimentá-las para outros também. Isso é tudo!

## Considerações Finais

Espero que este vídeo tenha dado a você uma melhor compreensão de por que o RAG tradicional não funciona tão bem mais e por que o modelo Gemini do Google é tão forte e útil, se você está construindo um produto ou um analista revisando documentos.


   
