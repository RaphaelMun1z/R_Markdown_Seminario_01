<h2><b>1.1 CONCEITOS INICIAIS</b></h2>

<h3>1.1.1 O que é Estatística?</h3>
<p>A estatística é uma parte da matemática aplicada que fornece métodos para planejar experimentos, obter dados e organiza-los, resumi-los, analisa-los, e interpreta-los e deles extrair conclusões.</p>

<h3>1.1.2 Qual a diferença entre população e amostra?</h3>
<ul>
    <li><b>População:</b> é o conjunto de elementos que têm, em comum, determinada característica (pessoas, coisas, objetos).</li>
    <li><b>Amostra:</b> é todo subconjunto não vazio e com menor número de elementos do que o conjunto definido como população.</li>
    <li><b>Tendenciosidade:</b> todos os elementos da população tem que ter a mesma chance de fazer parte da amostra. Se existir elementos com maior ou menor possibilidade de participar da amostra então há tendenciosidade.</li>
</ul>

<h3>1.1.3 O que são dados e variáveis?</h3>
<ul>
    <li><b>Dados:</b> são informações obtidas, seja com base nos elementos que constituem a população, seja com base nos elementos que constituem a amostra.</li>
    <li><b>Variáveis (xi):</b> é convencionalmente, o conjunto de resultados possíveis de um fenômeno.</li>
</ul>

<h2><b>1.2 CLASSIFICAÇÃO DAS VARIÁVEIS</b></h2>
<ul>
    <li><b>Qualitativas:</b> são qualidades (ou atributos) podem ser separados em diferentes categorias que se distinguem por alguma característica não numérica.</li>
    <ul>
        <li><b>Nominais:</b> dados nominais são aqueles em que as categorias não possuem nenhuma ordem intrínseca, como cores ou tipos de carros.</li>
        <li><b>Ordinais:</b> dados ordinais possuem uma ordem natural entre suas categorias, como níveis de escolaridade ou grau de satisfação</li>
    </ul>
    <li><b>Quantitativas:</b> são números que representam contagens ou medidas, e podem ser: </li>
    <ul>
        <li><b>Contínuas:</b> variável que assume, teoricamente, qualquer valor entre dois limites (medidas por algum aparelho).</li>
        <li><b>Discretas:</b> variável resultante de um conjunto finito de valores possíveis (contagens ou enumerações)</li>
    </ul>
</ul>

<h2><b>1.3 COLETA, ORGANIZAÇÃO E APRESENTAÇÃO DE DADOS</b></h2>
<h3>1.3.1 Dados brutos vs. dados elaborados.</h3>
<ul>
    <li><b>Dados brutos:</b> dados coletados de forma sem ordenação e sem nenhum tipo de arranjo sistemático.</li>
    <li><b>Dados elaborados:</b> dados que sofreram uma simples organização (ordenação).</li>
</ul>

<h3>1.3.2 Tabelas de frequência para:</h3>
<ul>
    <li>Qualitativas nominais.</li>
    <li>Quantitativas discretas.</li>
    <li>Quantitativas contínuas (com classes).</li>
</ul>

<h2><b>1.4 TIPOS DE FREQUÊNCIA</b></h2>
<ul>
    <li><b>Frequência absoluta (fi):</b> são os dados estatísticos resultantes da coleta direta da fonte, sem outra manipulação senão a contagem ou medida.</li>
    <li><b>Frequência relativa (fr):</b> são os resultados de comparações por quociente (razões) que se estabeleça entre os dados absolutos e têm por finalidade realçar ou facilitar as comparações entre quantidades.</li>
    <li><b>Frequência percentual (fp):</b> traduzem-se os dados relativos, em geral, por meio de percentagens, índices, coeficientes e taxas.</li>
</ul>

<h2><b>1.5 TIPOS DE GRÁFICOS</b></h2>
<h3>1.5.1 O que é um gráfico?</h3>
<p>É uma forma de apresentação dos dados estatísticos, cujo objetivo é o de produzir, uma impressão mais rápida e viva do fenômeno em estudo, já que os gráficos falam mais rápido à compreensão que as tabelas.</p>
<ul>
    <li><b>Gráfico em colunas ou em barras:</b></li>
    <ul>
        <li><b>Gráfico de barras:</b> quando em barras, os retângulos têm a mesma base e as alturas são proporcionais aos respectivos dados.</li>
        
```{r, echo=FALSE}
    ggplot(data = dados_selecionados, aes(x = Method)) + 
    geom_bar(fill = "#2b6cb0", alpha = 0.8) + 
    geom_text(stat = 'count', aes(label = after_stat(count)), hjust = -0.2) + 
    labs(title = "Quantidade de Imóveis por Método de Venda", x = "Método de Venda", y = "Quantidade (Frequência Absoluta)") + 
    theme_minimal() + 
    coord_flip()
```
        
        <li><b>Gráfico de colunas:</b> quando em colunas, os retângulos têm a mesma altura e os comprimentos são proporcionais aos respectivos dados.</li>
        
```{r, echo=FALSE, message=FALSE}
    top_5_vendedores <- dados_selecionados %>%
    count(SellerG, sort = TRUE) %>%
    top_n(5)

    ggplot(data = top_5_vendedores, aes(x = reorder(SellerG, n), y = n)) +
    geom_col(fill = "#2b6cb0", alpha = 0.8) +
    geom_text(aes(label = n), hjust = -0.2) +
    labs(title = "Top 5 Vendedores por Quantidade de Imóveis", x = "Vendedor", y = "Quantidade de Imóveis") +
    theme_minimal()
```

    </ul>
    <li><b>Gráfico de setores (pizza):</b>Este gráfico é constituído com base em um circulo.</li>
    <li><b>Histograma:</b> gráfico formado por retângulos cujas bases são proporcional ás amplitudes de classes e as alturas proporcionais às frequências.</li>
    <li><b>Polígono de frequência:</b> gráfico de linhas que une os pontos médios das classes no topo dos retângulos.</li>
    <li><b>Ogiva (para dados contínuos):</b> gráficos de frequências acumuladas (“abaixo de” e “acima de”).</li>
</ul>