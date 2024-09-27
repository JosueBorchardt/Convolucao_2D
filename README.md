## Convolução 2D em Tempo Discreto

A convolução 2D é uma extensão do conceito de convolução 1D, aplicada para sinais bidimensionais, como imagens. Essa operação consiste em deslocar um kernel (filtro) sobre a imagem, multiplicando os valores do kernel pelos pixels correspondentes e somando os resultados. A fórmula que define a convolução 2D é dada por:

$$ c[x, n]=I[x, y]*K[x,y]=\sum_{i=-∞}^{\infty}\sum_{j=-∞}^{\infty} I[i,j]K[x-i, y-i] $$

Onde $𝐼[𝑥,𝑦]$ representa a imagem de entrada, e $𝐾[𝑥,𝑦]$ é o kernel aplicado.

### Filtro de Suavização

Para suavizar a imagem, foi utilizado o seguinte filtro:

$$K_{suavizacao}=\frac{1}{9}\begin{bmatrix}
1 & 1 & 1\\
1 & 1 & 1\\
1 & 1 & 1\\
\end{bmatrix}$$
 
Esse filtro tem como efeito principal a redução de detalhes finos na imagem, suavizando áreas com variações leves de intensidade. Ao aplicar esse kernel na imagem, notou-se uma perda significativa de detalhes na textura, deixando a imagem mais homogênea e menos nítida. Embora esse efeito seja desejável para reduzir ruído, ele também pode gerar um efeito de "borrão", especialmente nas bordas de objetos, devido à suavização excessiva.

### Filtro de Detecção de Bordas

Para realçar as bordas, foi aplicado o seguinte filtro de detecção de bordas:

$$K_{bordas}=\begin{bmatrix}
-1 & -1 & -1\\
-1 & 8 & -1\\
-1 & -1 & -1\\
\end{bmatrix}$$

Esse filtro é utilizado para destacar as mudanças abruptas de intensidade, como as transições entre diferentes objetos ou áreas de diferentes tons de cinza. No entanto, a detecção de bordas resultante apresentou alguns desafios. Apesar de realçar as bordas, o filtro também introduziu ruído adicional em algumas áreas da imagem, o que dificultou a visualização precisa das bordas. Isso pode ser atribuído à falta de contraste suficiente entre certas partes da imagem ou à suavização aplicada anteriormente, que pode ter "escondido" algumas bordas mais sutis.
