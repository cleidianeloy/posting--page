<h1>Projeto de certificação 2 – Postagem de blog</h1>

<h2>Resumo do projeto</h2>

<p>
Crie uma página web que contenha um input para titulo e outro para escrever um conteúdo. Vamos simular a criação de um post semelhante ao facebook, linkedIn... Onde daremos um título, e escreveremos um texto qualquer e postamos. E o mais legal deste projeto, é que estaremos fazendo uma comunicação com uma API aberta. Simulando um pouco do mundo real.
</p>

<h2>Introdução</h2>
<p>
Este desafio é interessante, pois estaremos utilizando a família completa do front-end. A base para se fazer qualquer App que consome API's. Relaxe pequeno gafanhoto, que não será o bixo de 7 cabeças; Mas, te levará ao próximo nível, com certeza!
</p>
<p>
Os requisitos mínimos para avaliar a sua página dinâmica seriam:
</p>
<ol>
    <li>Basicamente no html, precisaremos de algum lugar para entrada de dados (input). E, outro para saída (output) 
    <ol>
        <li>
            Para a entrada, teremos form, dois inputs de texto e um botão para requisição post;
        </li>
        <li>
            Para saída de renderização, teremos alguma tag de título para receber o título; e outro de parágrafo para receber o conteúdo.
        </li>
    </ol>
    <li>
        No js, precisaremos de seletores.
        <ol>
            <li>Um, para aplicar evento de submit. </li>
            <li>Outros dois, para retirar título e conteúdo que quero enviar em meu post</li>
            <li>Outros dois, para renderizar o retorno do post, também titulo-renderizar e conteudo-renderizar.</li>
        </ol>
    </li>
    </li>
</ol>
<h2>Especificações</h2>
<p>Especificações dos requisitos mínimos</p>
<ol>
    <li>
        <ol>
            <li>
                Vale ressaltar, que é para fazer o form. Você pode utilizar para o conteúdo um textarea ao invés de input de texto. Utilizar um button ao invés de input de submit, utilizar um button mesmo... Vai de cada freguês, de testes, de erros e acertos!!! Caso, queira seguir algum fórmula: 
                <br><br>
                <code>
                &lt;form&gt;&lt;input type='text'&gt;&lt;input type='submit'&gt;
                </code>
            </li>
            <li>
                Para renderizar, é livre também! Porém, alguma fórmula?
                <br><br>
                <code>
                    &lt;h2&gt;&lt;/h2&gt;
                    &lt;p&gt;&lt;/p&gt;
                </code>
                <br><br>
                Para que não criemos dinamicamente, os elementos que precisamos para renderizar o conteúdo que será retornado do fetch/post, você pode ter algum h1,h2,h3... Para receber o título. E, algum p, div, article, textarea, ou o que for, onde você poderá receber o valor retornado do seu post, como no exemplo acima. Porém, deve sempre identificar com o seu id (identificador único);
                <br><br>
                <code>
                    &lt;h2 id="renderizador-titulo"&gt;&lt;/h2&gt;
                </code>
                <br><br>
                Já no js, algumas especificações para se pensar:
            </li>
        </ol>
    </li>
    <li>
        <ol>
            <li>
                Os seletores essenciais para qualquer dinâmica ou troca de dados que eu queira fazer entre os documentos html e js.
                <br><br>
                <code>const renderizadorTitulo = document.querySelector('#renderizador-titulo')
                </code>
            </li>
            <li>
                Deve-se adicionar um evento de "addEventListener" para submeter o conteúdo que está no form.
            </li>
            <li>
             Não esquecer de capturar o event, ou e, para poder prevenir o comportamento padrão do formulário (preventDefault). 
            </li>
            <li>
            o criar um post, você deve montar o seu objeto! 
            </li>
            <li>
            A estrutura do objeto que você enviará na sua chamada de API post, deve ser a seguinte:
            <code>
                const data = {
                    title: titulo.value,
                    body: conteudo.value, 
                    userId:1
                }
            </code>
            <br>
            Não mude o nome de data, nem title, nem body e nem userId. Deixe os elementos como estão. A única coisa que pode varia é <code>titulo.value</code> ou <code>conteudo.value</code> que seriam os valores dos seletores que você criou. Se seu seletor se chamar, tituloPost. Então, ficaria <code>tituloPost.value</code>!
                Para o nosso fetch, precisaremos ficar atentos às nossas configurações:
                url: <code>https://jsonplaceholder.typicode.com/posts</code>
                method: <code>"POST"</code>
                body: <code>JSON.stringify(data)</code>
                headers: <code>{"Content-type": "application/json; charset=UTF-8"} </code>
            Em nosso segundo then é onde ocorre a nossa mágica :
            Onde juntos, renderizamos o nosso post enviado!
            <code>tituloRenderizar.innerHTML = data.title</code>
            Lembrando, que tituloRenderizar, significaria o seletor de onde eu gostaria que os meu titulo postado fosse renderizado!
            </li>
        </ol>
    </li>
</ol>
