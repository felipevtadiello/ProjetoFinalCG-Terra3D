# Projeto Terra 3D - Computação Gráfica

## Descrição

Este projeto renderiza um modelo 3D realista da Terra utilizando OpenGL. A aplicação permite a interação com a cena através de controles de câmera que permitem movimentação e rotação, proporcionando uma experiência imersiva de visualização do planeta. Texturas de alta qualidade são aplicadas ao modelo para realçar detalhes como continentes e oceanos.

## Pré-requisitos

Antes de compilar e executar o projeto, certifique-se de que os seguintes componentes estão instalados no seu sistema:

- **Compilador C++**: Compatível com C++11 ou superior.
- **Bibliotecas Necessárias**:
  - [OpenGL](https://www.opengl.org/): Biblioteca para importação de modelos 3D.
  - [GLEW](http://glew.sourceforge.net/): Biblioteca para criação de janelas e gerenciamento de contexto OpenGL.
  - [GLFW](https://www.glfw.org/): Biblioteca para gerenciamento de extensões OpenGL.
  - [Assimp](https://www.assimp.org/): Biblioteca matemática para gráficos 3D.
  - [GLM](https://glm.g-truc.net/0.9.9/index.html): Biblioteca para carregamento de imagens.
  - [stb_image](https://github.com/nothings/stb): Fontes utilizadas para o modelo e texturas da Terra.

- **Sistema Operacional**: Windows, Linux ou macOS.

## Instalação

1. **Clone o Repositório**

   ```bash
   git clone https://github.com/seu-usuario/projeto-terra-3d.git

2. **Abra a pasta ProjetoFinal no Microsoft Visual Studio e execute o projeto**


## Controles

### Movimentação da Câmera:
- `W`: Move a câmera para frente.
- `S`: Move a câmera para trás.
- `A`: Move a câmera para a esquerda.
- `D`: Move a câmera para a direita.
- `Q`: Move a câmera para cima.
- `E`: Move a câmera para baixo.

### Rotação da Câmera:
- Mova o mouse para rotacionar a visão da câmera em torno do modelo.

### Fechar Aplicativo:
- `ESC`: Fecha a janela e encerra a aplicação.

## Elementos do Cenário

- **Modelo 3D da Terra**: Utiliza um arquivo `.obj` detalhado representando a superfície terrestre com texturas aplicadas para realismo.
- **Textura de Alta Resolução**: A textura aplicada (`Earth_diff.jpg`) realça detalhes como continentes, oceanos e características geográficas.
- **Iluminação**: O shader aplicado simula a iluminação natural, destacando a curvatura do planeta e criando efeitos de sombra.
- **Câmera Interativa**: Permite ao usuário explorar o modelo da Terra a partir de diferentes ângulos e distâncias, proporcionando uma experiência dinâmica.

## Estrutura do Projeto

- `main.cpp`: Arquivo principal contendo a lógica de inicialização, carregamento de modelos e texturas, e o loop de renderização.
- `shaders/`: Diretório contendo os arquivos de shader GLSL.
    - `vertex_shader.glsl`: Shader de vértice responsável por transformar as coordenadas dos vértices.
    - `fragment_shader.glsl`: Shader de fragmento responsável por aplicar as texturas e cores aos pixels.
- `earth/`: Diretório contendo o modelo 3D e a textura da Terra.
    - `13902_Earth_v1_l3.obj`: Arquivo do modelo 3D da Terra.
    - `Earth_diff.jpg`: Arquivo de textura para a superfície da Terra.
- `deps/`: Diretório para dependências externas.
- `out/`: Diretório para arquivos de saída (build outputs).
