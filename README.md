Agrupamento

Objetivo:

Aplicar conceitos de Mineração de Dados, com foco em algoritmos de agrupamento, utilizando o K-Means. Visamos segmentar clientes com base em seus padrões de consumo e perfis demográficos.

Cenário:

Uma empresa de marketing deseja segmentar seus clientes para criar campanhas mais eficientes. Com base no dataset "marketing_campaign.csv", contendo informações como idade, renda e hábitos de compra. Identificar diferentes grupos de consumidores, auxiliando na tomada de decisão para campanhas personalizadas.

Informações sobre o Dataset

A Análise de Personalidade do Cliente é uma análise detalhada dos clientes ideais de uma empresa. Ela auxilia o negócio a compreender melhor seus clientes, facilitando a adaptação de produtos às necessidades, comportamentos e preocupações específicas de diferentes tipos de clientes.

A análise de personalidade do cliente permite que uma empresa ajuste seus produtos com base nos clientes-alvo de diferentes segmentos. Por exemplo, em vez de gastar dinheiro promovendo um novo produto para todos os clientes do banco de dados da empresa, a empresa pode analisar qual segmento de clientes tem maior probabilidade de comprá-lo e direcionar a divulgação apenas para esse segmento específico.

No dataset há um total de 29 colunas.

As colunas podem ser entendidas da seguinte forma:

Pessoas:

● ID: Identificador único do cliente

● Year_Birth: Ano de nascimento do cliente

● Education: Nível de escolaridade do cliente

● Marital_Status: Estado civil do cliente

● Income: Renda anual familiar do cliente

● Kidhome: Número de crianças no domicílio do cliente

● Teenhome: Número de adolescentes no domicílio do cliente

● Dt_Customer: Data de cadastro do cliente na empresa

● Recency: Número de dias desde a última compra do cliente

● Complain: 1 se o cliente fez uma reclamação nos últimos 2 anos, 0 caso contrário

Produtos:

● MntWines: Quantia gasta com vinhos nos últimos 2 anos

● MntFruits: Quantia gasta com frutas nos últimos 2 anos

● MntMeatProducts: Quantia gasta com carne nos últimos 2 anos

● MntFishProducts: Quantia gasta com peixes nos últimos 2 anos

● MntSweetProducts: Quantia gasta com doces nos últimos 2 anos

● MntGoldProds: Quantia gasta com ouro nos últimos 2 anos

Promoção:

● NumDealsPurchases: Número de compras feitas com desconto

● AcceptedCmp1: 1 se o cliente aceitou a oferta na 1ª campanha, 0 caso contrário

● AcceptedCmp2: 1 se o cliente aceitou a oferta na 2ª campanha, 0 caso contrário

● AcceptedCmp3: 1 se o cliente aceitou a oferta na 3ª campanha, 0 caso contrário

● AcceptedCmp4: 1 se o cliente aceitou a oferta na 4ª campanha, 0 caso contrário

● AcceptedCmp5: 1 se o cliente aceitou a oferta na 5ª campanha, 0 caso contrário

● Response: 1 se o cliente aceitou a oferta na última campanha, 0 caso contrário

Local:

● NumWebPurchases: Número de compras feitas pelo site da empresa

● NumCatalogPurchases: Número de compras feitas por catálogo

● NumStorePurchases: Número de compras feitas diretamente em lojas físicas

● NumWebVisitsMonth: Número de visitas ao site da empresa no último mês

Padrões identificados nos Agrupamentos:
Analisamos como as variáveis renda (Income) e gasto total (Total_Gasto) influenciam na segmentação dos clientes. 
Com base no K-Means, cada cluster apresenta padrões específicos que refletem seu comportamento financeiro e os clusters são descritos da seguinte maneira:
Grupo "Jovem" (Laranja)
Os indivíduos desse grupo possuem baixa renda e baixo gasto total, esse padrão pode indicar um perfil de jovens em início de carreira, estudantes ou profissionais com pouca estabilidade financeira. 
Grupo "Adulto" (Verde)
Esse grupo apresenta renda e gastos médios, sugerindo um perfil de indivíduos financeiramente ativos e estabilizados, são pessoas que já consolidaram suas carreiras, possuem um planejamento financeiro mais estruturado e mantêm um equilíbrio entre ganhos e despesas. 
Grupo "Idoso" (Azul)
O grupo dos idosos possui um comportamento contraditório em relação à renda e ao consumo, sua renda média ser mais baixa que a dos adultos, seus gastos totais são mais elevados. Esse padrão pode estar relacionado a despesas específicas, como saúde, lazer e bem-estar, que costumam ter maior peso nessa fase da vida, dependem de aposentadorias, reservas financeiras ou suporte familiar para manter seu padrão de consumo.
Os resultados do agrupamento mostram que a renda e o gasto total seguem padrões distintos em cada faixa etária. Jovens apresentam menor capacidade de consumo, adultos encontram um equilíbrio entre renda e despesa, enquanto idosos mantêm gastos elevados, apesar da menor renda. Esses padrões podem ser úteis para estratégias de segmentação de mercado, oferta de produtos e políticas de planejamento financeiro voltadas para diferentes perfis de consumidores.

Análise do índice de Silhouette Score
O índice de silhueta (Silhouette Score) é uma métrica usada para avaliar a qualidade dos agrupamentos (clusters) feito por algoritmo como o K-Means.
Ele mede o quanto cada ponto está relacionado ao seu próprio cluster em comparação com outros clusters.
O valor do Silhouette Score varia de -1 a 1:
+1 → O ponto está muito bem atribuído ao seu próprio cluster.
0 → O ponto está na fronteira entre dois clusters.
-1 → O ponto pode estar mal alocado.

Resultado obtido na análise:
Silhouette Score com K-Means: 0.2341
Silhouette Score com K-Means++: 0.5091
O valor 0.2341, indica clusters com sobreposição significativa, baixa coesão interna e possível alocação incorreta de pontos.
O valor 0.5091 com K-Means++ representa uma melhor qualidade de agrupamento, com os clientes mais bem separados e internamente mais coesos dentro de seus grupos.
No K-means++ mostrou ser mais eficiente para este conjunto de dados formando clusters agrupados e com melhor definição e separação entre eles.

Conclusões
•	Quanto maior a renda, maior o gasto total, indicando que a empresa pode segmentar suas ofertas com base no poder aquisitivo.
•	O grupo jovem tem menor participação nos gastos totais, o que sugere a necessidade de estratégias para aumentar sua conversão e engajamento.
•	O grupo idoso representa os clientes mais lucrativos, tornando essencial garantir sua satisfação e retenção.

Sugestão de estratégias de marketing baseada nos resultados:
0	Adulto	Ofertas em combos de produtos do dia a dia (vinho + carne + doces).	E-mail marketing com promoções sazonais e fidelidade.
1	Jovem	Descontos em primeira compra e produtos de menor valor unitário.	Redes sociais e campanhas digitais com cupons.
2	Idoso	Programas de fidelidade premium e produtos sofisticados (vinhos, ouro).	Catálogo físico ou contato direto com consultores.


Limitações do K-Means:
O K-Means é utilizado amplamente, por possuir uma simplicidade e eficiência, mas possui limitações importantes, tais como assumir Clusters Globulares e Esféricos, pressupõe que os clusters são esféricos e de tamanho semelhante. Isso significa que ele funciona melhor quando os grupos são bem separados e têm distribuição semelhante em todas as direções (formato de "bola"). Em dados com clusters alongados, irregulares ou com diferentes densidades, o K-Means pode agrupar incorretamente. Ele é sensível a Outliers, utilizando médias (centroides), o que torna o algoritmo sensível à outliers, pois esses pontos podem deslocar significativamente os centroides. O número de Clusters (K) precisa ser definido, o algoritmo exige que o número de clusters seja informado a priori, o que pode ser desafiador quando não se tem conhecimento prévio da estrutura dos dados, e limitações em dados categóricos o K-Means depende de distância Euclidiana, que não é adequada para variáveis categóricas, mesmo com técnicas de codificação, o resultado pode ser distorcido.
Possíveis Melhorias e Alternativas é utilizar o próprio K-Means++.
