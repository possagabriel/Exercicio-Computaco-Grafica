# Computação Gráfica com Python e OpenGL

Repositório da disciplina de **Computação Gráfica** do **Unipac Barbacena**, ministrada pelo
**Prof. Rodrigo Fernandes dos Santos**.

O projeto constrói, passo a passo, um pequeno framework gráfico com **Pygame**, **PyOpenGL** e
**NumPy**, seguindo o livro *Developing Graphics Frameworks with Python and OpenGL* (Stemkoski e
Pascale, CRC Press, 2022). Ele reúne os checkpoints feitos em sala e as aulas completas, cada uma
com slides, demonstrações e uma atividade em dupla.

## Aulas

Siga as aulas nesta ordem. Cada pasta `alunos/` é independente: tem o próprio framework, os
exemplos, o enunciado da atividade e as instruções de instalação.

| # | Aula | Capítulo do livro | Atividade |
|---|---|---|---|
| 1 | [Transformações geométricas](Aula_Transformacoes/alunos/README.md) | 3: matrizes, composição, global x local, projeção | Mini sistema solar |
| 2 | [Grafo de cena](Aula_GrafoCena/alunos/README.md) | 4: Object3D, Mesh, Camera, Renderer, pivôs | Braço robótico |
| 3 | [Texturas](Aula_Texturas/alunos/README.md) | 5: Texture, UV, TextureMaterial | Cubo com satélite texturizado |

Os slides de cada aula estão na pasta correspondente (`Aula_*/*.pptx`).

**Exercícios:** veja [EXERCICIOS.md](EXERCICIOS.md) para a lista das atividades, como entregar e
os critérios de avaliação.

## Entrega

- [Mini sistema solar](Aula_Transformacoes/alunos/README.md)
- [Braço robótico](Aula_GrafoCena/alunos/README.md)
- [Cubo com satélite texturizado](Aula_Texturas/alunos/README.md)

## Estrutura do repositório

```
├── core/                      framework dos checkpoints iniciais
├── test-2.1.py ... test-3.py  checkpoints feitos em sala
├── Exercicio.py               exercício: retângulo animado com uniforms
├── Aula_Transformacoes/
│   └── alunos/                demos 1 a 3 + atividade_sistema_solar.py
├── Aula_GrafoCena/
│   └── alunos/                demos 1 a 3 + atividade_braco.py
├── Aula_Texturas/
│   └── alunos/                exemplos do retângulo e do cubo + atividade_cubo.py
├── EXERCICIOS.md              enunciados resumidos das atividades
└── requirements.txt
```

## Checkpoints da raiz

| Arquivo | Conteúdo |
|---|---|
| `test-2.1.py` | Janela básica com Pygame e OpenGL |
| `test-2.3.py` | Hexágono com `Attribute` e `GL_LINE_LOOP` |
| `test-2-6.py`, `test-2-7.py` | Translação de triângulos com uniforms |
| `test-2-9.py` | Triângulo com cor animada (uniform `baseColor`) |
| `test-3.py` | Transformações globais e locais com matrizes (teclado) |
| `Exercicio.py` | Retângulo de dois triângulos atravessando a tela |

O `test-3.py` usa uniforms do tipo `mat4`. Para executá-lo, use as classes da aula de
Transformações (`Aula_Transformacoes/alunos/core`), que já trazem esse suporte, ou rode a
`demo3_global_local.py` daquela aula, que é a versão comentada do mesmo exemplo.

## Requisitos

- Python 3.11 a 3.13
- Pygame 2.6.1, PyOpenGL 3.1.10 e NumPy (veja `requirements.txt`)
- Placa de vídeo com OpenGL 3.2 core ou superior

## Passo a passo: clonando e executando no PyCharm

Este tutorial assume que você já tem o **PyCharm** e o **Git** instalados no seu computador. Se
ainda não tiver, instale antes de continuar:

- Git: https://git-scm.com/downloads
- PyCharm (Community, que é gratuita, já é suficiente): https://www.jetbrains.com/pycharm/download/

### 1. Clonar o repositório usando o PyCharm

1. Abra o PyCharm.
2. Na tela inicial ("Welcome to PyCharm"), clique em **Get from VCS**.
   - Se o PyCharm já estiver aberto com outro projeto, vá em **File > New > Project from Version
     Control...**.
3. Em **URL**, cole:
   ```
   https://github.com/rodrygofesantos/pygame.git
   ```
4. Escolha a pasta onde o projeto será salvo no seu computador (pode deixar o local sugerido).
5. Clique em **Clone**.
6. O PyCharm vai baixar o projeto e abri-lo automaticamente.

### 2. Configurar o interpretador Python (ambiente virtual)

1. Vá em **File > Settings** (no Windows/Linux) ou **PyCharm > Settings** (no Mac).
2. No menu à esquerda, clique em **Project: pygame > Python Interpreter**.
3. Clique em **Add Interpreter > Add Local Interpreter...**.
4. Selecione **Virtualenv Environment > New**, confirme que a versão do Python é 3.10 ou superior e
   clique em **OK**.
5. Aguarde o PyCharm terminar de criar o ambiente virtual (uma pasta `.venv` vai aparecer no projeto).

### 3. Instalar as dependências

1. Abra o terminal integrado do PyCharm: menu **View > Tool Windows > Terminal** (ou o atalho
   `Alt+F12`).
2. Confirme que aparece `(.venv)` no começo da linha do terminal — isso indica que o ambiente
   virtual está ativo.
3. Digite o comando abaixo e pressione Enter:
   ```
   pip install -r requirements.txt
   ```

### 4. Executar o projeto

1. Na árvore de arquivos à esquerda, clique duas vezes em `test-2.1.py` (ou em qualquer outro
   exemplo) para abri-lo.
2. Clique com o botão direito em qualquer lugar do código e escolha **Run**.
   - Alternativamente, clique no ícone de seta verde ▶️ no canto superior direito da janela, ou ao
     lado do número da linha onde está `Test().run()`.
3. Uma janela chamada "Graphics Window" deve abrir na tela.
4. Para fechar o programa, clique no **X** da janela.

### Problemas comuns

- **"ModuleNotFoundError: No module named 'pygame'" (ou `numpy`, `OpenGL`)** — o interpretador
  selecionado no PyCharm não é o `.venv` do projeto, ou o `pip install -r requirements.txt` não foi
  executado nesse ambiente. Repita o passo 2 e 3 conferindo se o terminal mostra `(.venv)`.
- **A janela não abre ou parece travada** — confira se não há nenhuma outra janela do programa já
  aberta por trás; feche todas e rode de novo. Se estiver usando um notebook/desktop com placa de
  vídeo dedicada, confirme que os drivers de vídeo estão atualizados.
- **Nada acontece ao clicar em Run** — confirme que o arquivo `test-2.1.py` está selecionado/aberto
  como aba ativa antes de clicar em Run.
