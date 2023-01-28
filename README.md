<h1 align="center"> Desafio intermediário - Recriando layout </h1>
<div class="video">
https://user-images.githubusercontent.com/75433659/215268377-2260f0df-bdcd-4eef-a380-6c0e7db3f3ce.mp4
</div>

<div class="section">
    <p align="center">vídeo demonstrativo</p>
</div>

## Relatorio 🚦

Gostei muito da pegada do desafio de fazer sozinho juntando com oque aprendemos nas ultimas aulas. De ter o figma tanto como referência mas também como uma "apostila".

Bom primeiramente eu espero que não tenha problemas eu ter gostado até demais de ficar mexendo no projeto e explorando no css. 

De certo modo tenho uma pequena pequenininha experiência com o css pois ele sempre dispertou um grande interesse em mim no front-end. Então desde um bom tempo vejo sempre tutoriais e até videos pra matar o tempo sobre o assunto. Sobre <span class="span">semântica</span>, sobre <span class="span">responsividade</span>, ```displays:flex;``` e ```grid;```.


O que eu conseguia lembrar eu colocava e fazia do meu jeito. Claro, seguindo como as instruções. 

Espero que não seja um problema pois acabo me levando no processo criativo e quero sempre experimentar algo ou adicionar na tela. 

## Log das mudanças e como afetam 🍵

Queria deixa-la por último mas como pode perceber, se já acessou o site e tem consciencia de como é o arquivo figma. Já deve ter percebido que o ```footer``` está um pouco diferente.

No momento que eu bati o olho no figma eu sabia que eu ia fazer essa ondinha animada. Só não sabia como.
Primeiro eu dupliquei, flipei horizontalmente, depois editei as pontas no vector para suavizar e aumentar os "níveis" da onda para que eu podesse usar:
```css
background-size:1000px 100px
```
sem ter problema com tamanho futuramente quando trabalhar com ```scale``` e ```keyframes```.

Outras mudanças (já não tão grandes), que dá pra dizer como adições.
Foram os efeitos de ```hover```. O ato de passar o cursor do mouse num objeto, neste caso, links.


A primeira foi no destaque <span class="span" id="destino">destino</span>. Que no fim do projeto decidi deixá-lo como link. Imaginando então como se ele fosse um link de navegação local no site que poderia levar, no caso scrollar para uma categoria sobre assunto de viagens. Ou levar o usuário para uma aba, também local, de agendamento e planos sobre pacotes e preços.

```css
.prp a {
        color: #EE24FF;
        text-decoration: none;
        position: relative;
    }

    .prp a::before {
        background: #EE24FF;
        content: "";
        inset: 0;
        position: absolute;
        transform: scaleX(0);
        transform-origin: left;
        transition: transform .3s ease-in-out;
        z-index: -1;

    }

    .prp a:hover::before {
        transform: scaleX(1);
        
    }

    .prp a:hover {
        color: #fff;
        transition: .7s;
    }
```
<p class="p" align="center"> Uma maneira muito interessante também é mudando o ponto de origem da transição, de, ao invés de vir da lateral direita. Vir da parte inferior do contêiner.</p>

Assim:
```css
a::hover {
transform: scaleY(0);
transform-origin: bottom;
}
a:hover::before {
        transform: scaleY(1);  
    }
```
Aqui fiz de uma maneira resumida, mas não vale esquecer que no ```::hover``` se vão todas as caracteristicas do objeto. Tanto as que definem quanto as que queremos modificar com a ```:pseudo-classe``` e os ```::pseudo-elementos```

Por último mas não menos importante:

As ```nav-bars```. 

As mais simples até então. Somente pseudo-elemento de ```::hover``` e uma transição.

```css
.footer-nav a {
        text-decoration: none;
        color: #3F3D56;
        transition: .3s;
        }
.footer-nav a:hover {
        color: #EE24FF;
        }

```

<style>
    .span {
        font-weight: bold;
        font-style: italic;
    }

    #destino{
        color:#EE24FF
    }

    .p{
        font-size:12px
    }
</style>
