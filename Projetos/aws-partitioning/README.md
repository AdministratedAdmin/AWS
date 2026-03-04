<h2>Componentes Utilizados</h2>

<li>Amazon S3</li>
<li>AWS Glue Data Catalog</li>
<li>Glue Crawlers</li>
<li>Glue Jobs</li>
<li>Amazon Athena</li>

<h2></h2>
<p>O intuito de converter os dados de CSV para Parquet é baseado na economia. O CSV pesa mais na leitura pelo Athena devido à estrutura de seus dados, causando assim, um aumento de cobrança.</p>
<p>Como o Athena cobra por dados escaneados. Ao particionar, o Athena busca os dados diretamente no bucket já filtrado.</p>

<h2>Exemplo</h2>
<p>Ao invés de usar a query

SELECT * FROM x
WHERE Founded_Year = y;

Você pode buscar diretamente no bucket que corresponde à data ou critério de partição, sendo assim, o Athena não precisa escanear todos os dados para depois retornar os dados filtrados, economizando dinheiro.
</p>

<p>Também é possível usar o script de ingestão para criar pastas e separar arquivos por data de upload, afim de evitar usar dados antigos.</p>
