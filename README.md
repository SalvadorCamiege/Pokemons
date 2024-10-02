Pokémon Card Component
Este componente Vue.js exibe detalhes de um Pokémon selecionado, como nome, experiência (XP), altura e imagem, com animações para destacar a interface do usuário.
Estrutura do Componente
Script Setup: Utiliza defineProps para receber as propriedades nome, xp, height, img, e loading, que são passadas ao componente.
Template:
Exibe a imagem do Pokémon e suas informações de XP e altura.
Se loading for verdadeiro, a animação é desabilitada.
Caso o Pokémon não tenha nome, é exibida uma imagem de ovo como placeholder.
Estilo:
Personalizado com CSS e mídia queries para garantir uma exibição responsiva em diferentes tamanhos de tela.
Animação usando animate.css para o efeito "bounce".
Props
nome: Nome do Pokémon.
xp: Pontos de experiência do Pokémon.
height: Altura do Pokémon.
img: URL da imagem do Pokémon.
loading: Controla a exibição de animação.
Dependências
animate.css: Para a animação de bounce.
Aqui temos a lista de component:
Pokémon List Item Component
Este componente Vue.js exibe uma carta (card) de um Pokémon com seu nome e imagem. Ele é utilizado para listar vários Pokémon de forma responsiva, com efeitos de hover e estilos personalizados.
Estrutura do Componente
Script Setup: Utiliza defineProps para receber as propriedades nome e urlBasepng.
nome: Nome do Pokémon.
urlBasepng: URL da imagem PNG do Pokémon.
Template:
O componente renderiza um card (div.cardListPokemon) com o nome e a imagem do Pokémon.
A imagem é carregada dinamicamente a partir da URL recebida pela prop urlBasepng.
Estilos
O componente utiliza gradientes de cor para o plano de fundo, aplicando um efeito hover que muda a opacidade do gradiente.
As cartas são responsivas e ajustam-se automaticamente em diferentes tamanhos de tela, variando de 4 a 6 colunas em telas pequenas e até 3 colunas em telas maiores.
Pokédex Web App Layout
Este componente Vue.js define a estrutura principal do layout do seu aplicativo web de Pokédex, incluindo uma barra de navegação, conteúdo dinâmico com router-view e um rodapé.
Estrutura do Componente
Script Setup:
Importa o módulo ref do Vue e a configuração de rotas do router.
Cria uma referência reativa num, embora atualmente não esteja sendo usada no template.
Template:
NavBar:
Inclui um logotipo (imagem de Pokémon) e links para as páginas Home e About.
Usa Router-Link para navegação interna entre diferentes rotas do app.
Main Content: O conteúdo das páginas específicas é renderizado dentro de <router-view>, que muda dinamicamente conforme a rota.
Footer:
Um rodapé fixo na parte inferior da página com o nome do desenvolvedor e o ano atual, que é gerado dinamicamente usando {{ new Date().getFullYear() }}.
Estilos
Corpo:
Fundo com gradiente de azul escuro para tons de ciano, proporcionando uma aparência suave e agradável.
O corpo da página ocupa toda a altura da tela (100vh).
NavBar:
A barra de navegação é responsiva e usa as classes Bootstrap para colapsar em telas menores.
Footer:
O rodapé tem um estilo fixo e é alinhado ao centro, com um fundo de cor primária (azul escuro) e texto em cor clara.
Dependências
Vue Router: Para gerenciar as rotas e navegação entre as páginas Home e About.
Bootstrap 5: Para estilização da navegação e suporte responsivo.
