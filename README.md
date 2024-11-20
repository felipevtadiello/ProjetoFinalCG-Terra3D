# Projeto Terra 3D - Computa��o Gr�fica

## Descri��o

Este projeto renderiza um modelo 3D realista da Terra utilizando OpenGL. A aplica��o permite a intera��o com a cena atrav�s de controles de c�mera que permitem movimenta��o e rota��o, proporcionando uma experi�ncia imersiva de visualiza��o do planeta. Texturas de alta qualidade s�o aplicadas ao modelo para real�ar detalhes como continentes e oceanos.

## Pr�-requisitos

Antes de compilar e executar o projeto, certifique-se de que os seguintes componentes est�o instalados no seu sistema:

- **Compilador C++**: Compat�vel com C++11 ou superior.
- **Bibliotecas Necess�rias**:
  - [OpenGL](https://www.opengl.org/): Biblioteca para importa��o de modelos 3D.
  - [GLEW](http://glew.sourceforge.net/): Biblioteca para cria��o de janelas e gerenciamento de contexto OpenGL.
  - [GLFW](https://www.glfw.org/): Biblioteca para gerenciamento de extens�es OpenGL.
  - [Assimp](https://www.assimp.org/): Biblioteca matem�tica para gr�ficos 3D.
  - [GLM](https://glm.g-truc.net/0.9.9/index.html): Biblioteca para carregamento de imagens.
  - [stb_image](https://github.com/nothings/stb): Fontes utilizadas para o modelo e texturas da Terra.

- **Sistema Operacional**: Windows, Linux ou macOS.

## Instala��o

1. **Clone o Reposit�rio**

   ```bash
   git clone https://github.com/seu-usuario/projeto-terra-3d.git

2. **Abra a pasta ProjetoFinal no Microsoft Visual Studio e execute o projeto**


## Controles

### Movimenta��o da C�mera:
- `W`: Move a c�mera para frente.
- `S`: Move a c�mera para tr�s.
- `A`: Move a c�mera para a esquerda.
- `D`: Move a c�mera para a direita.
- `Q`: Move a c�mera para cima.
- `E`: Move a c�mera para baixo.

### Rota��o da C�mera:
- Mova o mouse para rotacionar a vis�o da c�mera em torno do modelo.

### Fechar Aplicativo:
- `ESC`: Fecha a janela e encerra a aplica��o.

## Elementos do Cen�rio

- **Modelo 3D da Terra**: Utiliza um arquivo `.obj` detalhado representando a superf�cie terrestre com texturas aplicadas para realismo.
- **Textura de Alta Resolu��o**: A textura aplicada (`Earth_diff.jpg`) real�a detalhes como continentes, oceanos e caracter�sticas geogr�ficas.
- **Ilumina��o**: O shader aplicado simula a ilumina��o natural, destacando a curvatura do planeta e criando efeitos de sombra.
- **C�mera Interativa**: Permite ao usu�rio explorar o modelo da Terra a partir de diferentes �ngulos e dist�ncias, proporcionando uma experi�ncia din�mica.

## Estrutura do Projeto

- `main.cpp`: Arquivo principal contendo a l�gica de inicializa��o, carregamento de modelos e texturas, e o loop de renderiza��o.
- `shaders/`: Diret�rio contendo os arquivos de shader GLSL.
    - `vertex_shader.glsl`: Shader de v�rtice respons�vel por transformar as coordenadas dos v�rtices.
    - `fragment_shader.glsl`: Shader de fragmento respons�vel por aplicar as texturas e cores aos pixels.
- `earth/`: Diret�rio contendo o modelo 3D e a textura da Terra.
    - `13902_Earth_v1_l3.obj`: Arquivo do modelo 3D da Terra.
    - `Earth_diff.jpg`: Arquivo de textura para a superf�cie da Terra.
- `deps/`: Diret�rio para depend�ncias externas.
- `out/`: Diret�rio para arquivos de sa�da (build outputs).
