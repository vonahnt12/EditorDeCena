#  Editor de Cena 3D (WebGL 2)

O **Editor de Cena** é uma aplicação web interativa desenvolvida em **HTML5, CSS3 e JavaScript (ES6)** para criação, edição e visualização de cenários 3D no navegador. 

Construído com **WebGL 2** e a biblioteca **TWGL.js**, o projeto conta com modelos `.OBJ` pré-definidos no catálogo, gera miniaturas 3D dinâmicas para a interface, permite aplicar transformações geométricas em tempo real, gerenciar hierarquias entre objetos, manipular uma câmera orbital e exportar/importar o estado da cena em JSON.

---

##  Funcionalidades do Projeto

###  Engine 3D & Shaders Customizados
- **Renderização em WebGL 2:** Shaders GLSL (`#version 300 es`) customizados para cálculo de posição, coordenadas UV, ajuste de tom/multiplicador de cor (*tint*) e efeito de *highlight* amarelo ao selecionar um objeto.
- **Catálogo de Modelos Pré-definidos:** Coleção integrada de modelos 3D no formato `.OBJ` (com texturas) embutidos no código, prontos para inserção na cena.
- **Miniaturas Dinâmicas (Offscreen Rendering):** Renderização em *Framebuffer Info* (FBO) para gerar automaticamente as miniaturas 3D dos modelos exibidos no catálogo.

###  Inspetor de Propriedades & Transformações
- **Transformações 3D:** Modificação em tempo real de Posição $(X, Y, Z)$, Rotação $(X, Y, Z)$ e Escala $(X, Y, Z)$.
- **Ajuste de Cor (Tint):** Seletor de cor HEX para alteração do tom/material do objeto.
- **Hierarquia Simples:** Vinculação de um objeto filho a um objeto pai para transformações encadeadas.

###  Câmera Orbital & Interatividade
- **Navegação 3D:** Rotação da câmera ao arrastar o mouse na área de visualização e controle de zoom através da roda do mouse (*scroll*).
- **Gestão da Cena:** Painel com a lista de objetos ativos, seleção visual e remoção de elementos via atalho (tecla `Delete`) ou botão no inspetor.

###  Persistência da Cena
- **Salvar / Carregar:** Exportação da cena completa para um arquivo `cena.json` e restauração simplificada do estado do projeto.

---

##  Estrutura do Repositório

```text
.
├── index.html       # Estrutura da interface (HTML5 com CSS Grid e CDN TWGL)
├── editor.css       # Estilização do editor, layout de colunas e sliders
├── editor.js        # WebGL2, shaders, modelos .OBJ, câmera e lógica da cena
├── package.json     # Metadados do projeto
└── README.md        # Documentação do projeto
```

---

##  Como Executar o Projeto

Como o projeto utiliza tecnologias nativas da web, não é necessária nenhuma etapa de compilação.

### Opção 1: Execução Direta
1. Clone o repositório:
   ```bash
   git clone [https://github.com/vonahnt12/EditorDeCena.git](https://github.com/vonahnt12/EditorDeCena.git)
   ```
2. Abra o arquivo `index.html` em qualquer navegador moderno (Chrome, Firefox, Edge, Safari).

> **Nota:** É necessária conexão com a internet na abertura do arquivo para o carregamento da biblioteca TWGL.js via CDN (`cdnjs`).

### Opção 2: Servidor Local (Recomendado)
Para rodar em um ambiente de servidor local simples:

```bash
# Executar utilizando Python 3 na pasta do projeto
python -m http.server 8000
```
Acesse `http://localhost:8000` no seu navegador.

---

##  Controles e Atalhos

| Função | Comando |
| :--- | :--- |
| **Girar Câmera** | Arrastar com o botão esquerdo do mouse no vazio |
| **Zoom** | Roda do mouse (*Scroll*) |
| **Selecionar Objeto** | Clique no item desejado na lista "Objetos na cena" |
| **Remover Objeto** | Tecla `Delete` ou botão no Inspetor |
| **Salvar / Carregar** | Botões no cabeçalho superior |

---

## 👨‍💻 Autor

Desenvolvido por **Eduardo Alencastro von Ahnt**.
