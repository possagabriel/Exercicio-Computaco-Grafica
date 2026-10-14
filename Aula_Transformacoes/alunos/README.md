# Mini sistema solar

Disciplina: Computação Gráfica

Atividade: Mini sistema solar

Integrantes: Gabriel Possa Lima e Darlan José dos Santos

Descrição: O Sol gira no próprio centro. O planeta usa uma rotação orbital seguida de uma translação de raio 0,6, com rotação própria independente. A Lua reutiliza a matriz da órbita do planeta e acrescenta sua órbita de raio 0,2. As setas ajustam a velocidade orbital sem permitir valores negativos.

Resposta da questão: A órbita usa `R @ T` porque a translação desloca primeiro o planeta até o raio da órbita e a rotação seguinte gira esse deslocamento ao redor do Sol. A rotação própria fica à direita da translação para atuar no planeta ainda em suas coordenadas locais, antes de ele ser posicionado na órbita; assim, ela gira o planeta em torno do próprio centro sem mudar o raio orbital. A escala também fica à direita da translação para preservar as distâncias.

![resultado](capturas/resultado.png)
