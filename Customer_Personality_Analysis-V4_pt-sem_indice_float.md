Análise de Personalidade do Cliente
================
Gleynner Ghiotto

-   [1 Atributos](#1-atributos)
-   [2 Examinando o conjunto de dados
    (Geral):](#2-examinando-o-conjunto-de-dados-geral)
    -   [2.1 Detectando Valores ausentes
        (NA)](#21-detectando-valores-ausentes-na)
    -   [2.2 Detectando valores
        duplicados](#22-detectando-valores-duplicados)
    -   [2.3 Eliminar colunas
        indesejadas](#23-eliminar-colunas-indesejadas)
    -   [2.4 Estatísticas](#24-estatísticas)
-   [3 Análises univariadas](#3-análises-univariadas)
    -   [3.1 ID (Identificador único do
        cliente)](#31-id-identificador-único-do-cliente)
    -   [3.2 Year_Birth (Ano de nascimento do
        cliente)](#32-year_birth-ano-de-nascimento-do-cliente)
    -   [3.3 Education (Nível de instrução do
        cliente)](#33-education-nível-de-instrução-do-cliente)
    -   [3.4 Marital_Status (Estado civil do
        cliente)](#34-marital_status-estado-civil-do-cliente)
    -   [3.5 Income (Renda familiar anual do
        cliente)](#35-income-renda-familiar-anual-do-cliente)
    -   [3.6 Kidhome e Teenhome (Número de crianças e adolescentes na
        residência do
        cliente)](#36-kidhome-e-teenhome-número-de-crianças-e-adolescentes-na-residência-do-cliente)
    -   [3.7 Dt_Customer (Data do cadastro do cliente na
        empresa)](#37-dt_customer-data-do-cadastro-do-cliente-na-empresa)
    -   [3.8 Recency (Quantidade de dias desde a última compra do
        cliente)](#38-recency-quantidade-de-dias-desde-a-última-compra-do-cliente)
    -   [3.9 Variáveis MntWines, MntFruits, MntMeatProducts,
        MntFishProducts, MntSweetProducts e
        MntGoldProds](#39-variáveis-mntwines-mntfruits-mntmeatproducts-mntfishproducts-mntsweetproducts-e-mntgoldprods)
    -   [3.10 NumDealsPurchases (Número de compras feitas com
        desconto)](#310-numdealspurchases-número-de-compras-feitas-com-desconto)
    -   [3.11 NumWebPurchases, NumCatalogPurchases e
        NumStorePurchases](#311-numwebpurchases-numcatalogpurchases-e-numstorepurchases)
    -   [3.12 NumWebVisitsMonth (Número de visitas ao site da empresa no
        último
        mês)](#312-numwebvisitsmonth-número-de-visitas-ao-site-da-empresa-no-último-mês)
    -   [3.13 Variáveis AcceptedCmp1, AcceptedCmp2, AcceptedCmp3,
        AcceptedCmp4 e
        AcceptedCmp5](#313-variáveis-acceptedcmp1-acceptedcmp2-acceptedcmp3-acceptedcmp4-e-acceptedcmp5)
    -   [3.14 Complain (1 se o cliente reclamou nos últimos 2 anos, 0
        caso
        contrário)](#314-complain-1-se-o-cliente-reclamou-nos-últimos-2-anos-0-caso-contrário)
    -   [3.15 Response (1 se o cliente aceitou a oferta na última
        campanha, 0 caso
        contrário)](#315-response-1-se-o-cliente-aceitou-a-oferta-na-última-campanha-0-caso-contrário)
    -   [3.16 Prosseguir apenas com as colunas que seja de interesse
        para as
        análies](#316-prosseguir-apenas-com-as-colunas-que-seja-de-interesse-para-as-análies)
    -   [3.17 Calcular o valor médio por
        compra](#317-calcular-o-valor-médio-por-compra)
-   [4 Análise gráfica](#4-análise-gráfica)
    -   [4.1 Gráfico de barras](#41-gráfico-de-barras)
        -   [4.1.1 Nível educacional x
            Gasto_total](#411-nível-educacional-x-gasto_total)
        -   [4.1.2 Estado civil x
            Gasto_total](#412-estado-civil-x-gasto_total)
        -   [4.1.3 Número de filhos x
            Gasto_total](#413-número-de-filhos-x-gasto_total)
        -   [4.1.4 Número de campanhas aceitas x
            Gasto_total](#414-número-de-campanhas-aceitas-x-gasto_total)
    -   [4.2 Gráfico de dispersão](#42-gráfico-de-dispersão)
        -   [4.2.1 Renda anual x Valor médio por
            compra](#421-renda-anual-x-valor-médio-por-compra)
        -   [4.2.2 Renda anual x Gasto
            total](#422-renda-anual-x-gasto-total)
-   [5 Correlação entre variáveis](#5-correlação-entre-variáveis)
-   [6 Gerar clusters](#6-gerar-clusters)
    -   [6.1 Renda Anual e gasto total](#61-renda-anual-e-gasto-total)
    -   [6.2 Renda Anual e Idade](#62-renda-anual-e-idade)
    -   [6.3 Gasto total e Idade](#63-gasto-total-e-idade)

# 1 Atributos

-   **Pessoas**:

**ID:** Identificador único do cliente <br> **Year_Birth:** Ano de
nascimento do cliente <br> **Education:** Nível de instrução do cliente
<br> **Marital_Status:** Estado civil do cliente <br> **Income:** Renda
familiar anual do cliente <br> **Kidhome:** Número de crianças na
residência do cliente <br> **Teenhome:** Número de adolescentes na casa
do cliente <br> **Dt_Customer:** Data do cadastro do cliente na empresa
<br> **Recency:** Quantidade de dias desde a última compra do cliente
<br> **Complain:** 1 se o cliente reclamou nos últimos 2 anos, 0 caso
contrário <br>

-   **Produtos**:

**MntWines:** Montante gasto em vinho nos últimos 2 anos <br>
**MntFruits:** Montante gasto com frutas nos últimos 2 anos <br>
**MntMeatProducts:** Valor gasto com carnes nos últimos 2 anos <br>
**MntFishProducts:** Valor gasto em pescado nos últimos 2 anos <br>
**MntSweetProducts:** Valor gasto em doces nos últimos 2 anos <br>
**MntGoldProds:** Valor gasto em dinheiro nos últimos 2 anos <br>

-   **Promoção**:

**NumDealsPurchases:** Número de compras feitas com desconto <br>
**AcceptedCmp1:** 1 se o cliente aceitou a oferta na 1ª campanha, 0 caso
contrário <br> **AcceptedCmp2:** 1 se o cliente aceitou a oferta na 2ª
campanha, 0 caso contrário <br> **AcceptedCmp3:** 1 se o cliente aceitou
a oferta na 3ª campanha, 0 caso contrário <br> **AcceptedCmp4:** 1 se o
cliente aceitou a oferta na 4ª campanha, 0 caso contrário <br>
**AcceptedCmp5:** 1 se o cliente aceitou a oferta na 1ª campanha, 0 caso
contrário <br> **Response:** 1 se o cliente aceitou a oferta na última
campanha, 0 caso contrário <br>

-   **Local**:

**NumWebPurchases:** Número de compras feitas pelo site da empresa <br>
**NumCatalogPurchases:** Número de compras feitas usando um catálogo
<br> **NumStorePurchases:** Número de compras feitas diretamente nas
lojas <br> **NumWebVisitsMonth:** Número de visitas ao site da empresa
no último mês <br>

# 2 Examinando o conjunto de dados (Geral):

``` r
# carregar dados
dados <- read.csv("G:/Meu Drive/Dados_R/PORTFOLIO/Customer_personality_analysis/marketing_campaign.csv",header = TRUE, sep = "\t")
head(dados, n=10)
```

<div data-pagedtable="false">

<script data-pagedtable-source type="application/json">
{"columns":[{"label":[""],"name":["_rn_"],"type":[""],"align":["left"]},{"label":["ID"],"name":[1],"type":["int"],"align":["right"]},{"label":["Year_Birth"],"name":[2],"type":["int"],"align":["right"]},{"label":["Education"],"name":[3],"type":["chr"],"align":["left"]},{"label":["Marital_Status"],"name":[4],"type":["chr"],"align":["left"]},{"label":["Income"],"name":[5],"type":["int"],"align":["right"]},{"label":["Kidhome"],"name":[6],"type":["int"],"align":["right"]},{"label":["Teenhome"],"name":[7],"type":["int"],"align":["right"]},{"label":["Dt_Customer"],"name":[8],"type":["chr"],"align":["left"]},{"label":["Recency"],"name":[9],"type":["int"],"align":["right"]},{"label":["MntWines"],"name":[10],"type":["int"],"align":["right"]},{"label":["MntFruits"],"name":[11],"type":["int"],"align":["right"]},{"label":["MntMeatProducts"],"name":[12],"type":["int"],"align":["right"]},{"label":["MntFishProducts"],"name":[13],"type":["int"],"align":["right"]},{"label":["MntSweetProducts"],"name":[14],"type":["int"],"align":["right"]},{"label":["MntGoldProds"],"name":[15],"type":["int"],"align":["right"]},{"label":["NumDealsPurchases"],"name":[16],"type":["int"],"align":["right"]},{"label":["NumWebPurchases"],"name":[17],"type":["int"],"align":["right"]},{"label":["NumCatalogPurchases"],"name":[18],"type":["int"],"align":["right"]},{"label":["NumStorePurchases"],"name":[19],"type":["int"],"align":["right"]},{"label":["NumWebVisitsMonth"],"name":[20],"type":["int"],"align":["right"]},{"label":["AcceptedCmp3"],"name":[21],"type":["int"],"align":["right"]},{"label":["AcceptedCmp4"],"name":[22],"type":["int"],"align":["right"]},{"label":["AcceptedCmp5"],"name":[23],"type":["int"],"align":["right"]},{"label":["AcceptedCmp1"],"name":[24],"type":["int"],"align":["right"]},{"label":["AcceptedCmp2"],"name":[25],"type":["int"],"align":["right"]},{"label":["Complain"],"name":[26],"type":["int"],"align":["right"]},{"label":["Z_CostContact"],"name":[27],"type":["int"],"align":["right"]},{"label":["Z_Revenue"],"name":[28],"type":["int"],"align":["right"]},{"label":["Response"],"name":[29],"type":["int"],"align":["right"]}],"data":[{"1":"5524","2":"1957","3":"Graduation","4":"Single","5":"58138","6":"0","7":"0","8":"04-09-2012","9":"58","10":"635","11":"88","12":"546","13":"172","14":"88","15":"88","16":"3","17":"8","18":"10","19":"4","20":"7","21":"0","22":"0","23":"0","24":"0","25":"0","26":"0","27":"3","28":"11","29":"1","_rn_":"1"},{"1":"2174","2":"1954","3":"Graduation","4":"Single","5":"46344","6":"1","7":"1","8":"08-03-2014","9":"38","10":"11","11":"1","12":"6","13":"2","14":"1","15":"6","16":"2","17":"1","18":"1","19":"2","20":"5","21":"0","22":"0","23":"0","24":"0","25":"0","26":"0","27":"3","28":"11","29":"0","_rn_":"2"},{"1":"4141","2":"1965","3":"Graduation","4":"Together","5":"71613","6":"0","7":"0","8":"21-08-2013","9":"26","10":"426","11":"49","12":"127","13":"111","14":"21","15":"42","16":"1","17":"8","18":"2","19":"10","20":"4","21":"0","22":"0","23":"0","24":"0","25":"0","26":"0","27":"3","28":"11","29":"0","_rn_":"3"},{"1":"6182","2":"1984","3":"Graduation","4":"Together","5":"26646","6":"1","7":"0","8":"10-02-2014","9":"26","10":"11","11":"4","12":"20","13":"10","14":"3","15":"5","16":"2","17":"2","18":"0","19":"4","20":"6","21":"0","22":"0","23":"0","24":"0","25":"0","26":"0","27":"3","28":"11","29":"0","_rn_":"4"},{"1":"5324","2":"1981","3":"PhD","4":"Married","5":"58293","6":"1","7":"0","8":"19-01-2014","9":"94","10":"173","11":"43","12":"118","13":"46","14":"27","15":"15","16":"5","17":"5","18":"3","19":"6","20":"5","21":"0","22":"0","23":"0","24":"0","25":"0","26":"0","27":"3","28":"11","29":"0","_rn_":"5"},{"1":"7446","2":"1967","3":"Master","4":"Together","5":"62513","6":"0","7":"1","8":"09-09-2013","9":"16","10":"520","11":"42","12":"98","13":"0","14":"42","15":"14","16":"2","17":"6","18":"4","19":"10","20":"6","21":"0","22":"0","23":"0","24":"0","25":"0","26":"0","27":"3","28":"11","29":"0","_rn_":"6"},{"1":"965","2":"1971","3":"Graduation","4":"Divorced","5":"55635","6":"0","7":"1","8":"13-11-2012","9":"34","10":"235","11":"65","12":"164","13":"50","14":"49","15":"27","16":"4","17":"7","18":"3","19":"7","20":"6","21":"0","22":"0","23":"0","24":"0","25":"0","26":"0","27":"3","28":"11","29":"0","_rn_":"7"},{"1":"6177","2":"1985","3":"PhD","4":"Married","5":"33454","6":"1","7":"0","8":"08-05-2013","9":"32","10":"76","11":"10","12":"56","13":"3","14":"1","15":"23","16":"2","17":"4","18":"0","19":"4","20":"8","21":"0","22":"0","23":"0","24":"0","25":"0","26":"0","27":"3","28":"11","29":"0","_rn_":"8"},{"1":"4855","2":"1974","3":"PhD","4":"Together","5":"30351","6":"1","7":"0","8":"06-06-2013","9":"19","10":"14","11":"0","12":"24","13":"3","14":"3","15":"2","16":"1","17":"3","18":"0","19":"2","20":"9","21":"0","22":"0","23":"0","24":"0","25":"0","26":"0","27":"3","28":"11","29":"1","_rn_":"9"},{"1":"5899","2":"1950","3":"PhD","4":"Together","5":"5648","6":"1","7":"1","8":"13-03-2014","9":"68","10":"28","11":"0","12":"6","13":"1","14":"1","15":"13","16":"1","17":"1","18":"0","19":"0","20":"20","21":"1","22":"0","23":"0","24":"0","25":"0","26":"0","27":"3","28":"11","29":"0","_rn_":"10"}],"options":{"columns":{"min":{},"max":[10]},"rows":{"min":[10],"max":[10]},"pages":{}}}
  </script>

</div>

``` r
cat("O Data Frame original possui", dim(dados)[1],"linhas e", dim(dados)[2],"colunas")
```

    O Data Frame original possui 2240 linhas e 29 colunas

``` r
cat("Variáveis presentes no Data Frame: \n", colnames(dados), "\n Total de variáveis:", length(colnames(dados)), sep = " \n ")
```

    Variáveis presentes no Data Frame: 
     
     ID 
     Year_Birth 
     Education 
     Marital_Status 
     Income 
     Kidhome 
     Teenhome 
     Dt_Customer 
     Recency 
     MntWines 
     MntFruits 
     MntMeatProducts 
     MntFishProducts 
     MntSweetProducts 
     MntGoldProds 
     NumDealsPurchases 
     NumWebPurchases 
     NumCatalogPurchases 
     NumStorePurchases 
     NumWebVisitsMonth 
     AcceptedCmp3 
     AcceptedCmp4 
     AcceptedCmp5 
     AcceptedCmp1 
     AcceptedCmp2 
     Complain 
     Z_CostContact 
     Z_Revenue 
     Response 
     
     Total de variáveis: 
     29

## 2.1 Detectando Valores ausentes (NA)

``` r
func_my_summary(dados)
```

<div data-pagedtable="false">

<script data-pagedtable-source type="application/json">
{"columns":[{"label":["Variavel"],"name":[1],"type":["chr"],"align":["left"]},{"label":["Tipo"],"name":[2],"type":["chr"],"align":["left"]},{"label":["N"],"name":[3],"type":["int"],"align":["right"]},{"label":["Missing"],"name":[4],"type":["int"],"align":["right"]},{"label":["Missing_Percent"],"name":[5],"type":["dbl"],"align":["right"]},{"label":["N_unique"],"name":[6],"type":["int"],"align":["right"]}],"data":[{"1":"ID","2":"integer","3":"2240","4":"0","5":"0.0","6":"2240"},{"1":"Year_Birth","2":"integer","3":"2240","4":"0","5":"0.0","6":"59"},{"1":"Education","2":"character","3":"2240","4":"0","5":"0.0","6":"5"},{"1":"Marital_Status","2":"character","3":"2240","4":"0","5":"0.0","6":"8"},{"1":"Income","2":"integer","3":"2240","4":"24","5":"1.1","6":"1975"},{"1":"Kidhome","2":"integer","3":"2240","4":"0","5":"0.0","6":"3"},{"1":"Teenhome","2":"integer","3":"2240","4":"0","5":"0.0","6":"3"},{"1":"Dt_Customer","2":"character","3":"2240","4":"0","5":"0.0","6":"663"},{"1":"Recency","2":"integer","3":"2240","4":"0","5":"0.0","6":"100"},{"1":"MntWines","2":"integer","3":"2240","4":"0","5":"0.0","6":"776"},{"1":"MntFruits","2":"integer","3":"2240","4":"0","5":"0.0","6":"158"},{"1":"MntMeatProducts","2":"integer","3":"2240","4":"0","5":"0.0","6":"558"},{"1":"MntFishProducts","2":"integer","3":"2240","4":"0","5":"0.0","6":"182"},{"1":"MntSweetProducts","2":"integer","3":"2240","4":"0","5":"0.0","6":"177"},{"1":"MntGoldProds","2":"integer","3":"2240","4":"0","5":"0.0","6":"213"},{"1":"NumDealsPurchases","2":"integer","3":"2240","4":"0","5":"0.0","6":"15"},{"1":"NumWebPurchases","2":"integer","3":"2240","4":"0","5":"0.0","6":"15"},{"1":"NumCatalogPurchases","2":"integer","3":"2240","4":"0","5":"0.0","6":"14"},{"1":"NumStorePurchases","2":"integer","3":"2240","4":"0","5":"0.0","6":"14"},{"1":"NumWebVisitsMonth","2":"integer","3":"2240","4":"0","5":"0.0","6":"16"},{"1":"AcceptedCmp3","2":"integer","3":"2240","4":"0","5":"0.0","6":"2"},{"1":"AcceptedCmp4","2":"integer","3":"2240","4":"0","5":"0.0","6":"2"},{"1":"AcceptedCmp5","2":"integer","3":"2240","4":"0","5":"0.0","6":"2"},{"1":"AcceptedCmp1","2":"integer","3":"2240","4":"0","5":"0.0","6":"2"},{"1":"AcceptedCmp2","2":"integer","3":"2240","4":"0","5":"0.0","6":"2"},{"1":"Complain","2":"integer","3":"2240","4":"0","5":"0.0","6":"2"},{"1":"Z_CostContact","2":"integer","3":"2240","4":"0","5":"0.0","6":"1"},{"1":"Z_Revenue","2":"integer","3":"2240","4":"0","5":"0.0","6":"1"},{"1":"Response","2":"integer","3":"2240","4":"0","5":"0.0","6":"2"}],"options":{"columns":{"min":{},"max":[10]},"rows":{"min":[10],"max":[10]},"pages":{}}}
  </script>

</div>

``` r
cat("Índices das linhas com valores ausentes para a variável Income: ",which(is.na(dados$Income)), "\nTotal de NA's:", sum(is.na(dados$Income)), sep = "\n" )
```

    Índices das linhas com valores ausentes para a variável Income: 
    11
    28
    44
    49
    59
    72
    91
    92
    93
    129
    134
    313
    320
    1380
    1383
    1384
    1387
    2060
    2062
    2079
    2080
    2082
    2085
    2229

    Total de NA's:
    24

``` r
# Eliminar valores NA da variável Income
dados_1 <- dados %>% drop_na(Income)         #dados_1 é o data frame que sofrerá alteração nesta parte exploratória.

cat("Quantidade de valores ausentes (NA) após eliminação:", sum(is.na(dados_1)))
```

    Quantidade de valores ausentes (NA) após eliminação: 0

## 2.2 Detectando valores duplicados

``` r
cat("Quantidade de valores duplicados é:", sum(duplicated(dados_1)))
```

    Quantidade de valores duplicados é: 0

## 2.3 Eliminar colunas indesejadas

``` r
unique(dados_1$Z_CostContact)
```

    [1] 3

``` r
unique(dados_1$Z_Revenue)
```

    [1] 11

``` r
dados_1[,c("Z_CostContact","Z_Revenue")] <- NULL

cat('Após a exclusão das variáveis Z_CostContact e Z_Revenue, o data frame "dados_1" possui',
    dim(dados_1)[2],
    'colunas. Tais variáveis foram eliminadas por possuirem o mesmo valor para todas as observações.')
```

    Após a exclusão das variáveis Z_CostContact e Z_Revenue, o data frame "dados_1" possui 27 colunas. Tais variáveis foram eliminadas por possuirem o mesmo valor para todas as observações.

## 2.4 Estatísticas

``` r
my_summary_all(dados_1)
```

<div data-pagedtable="false">

<script data-pagedtable-source type="application/json">
{"columns":[{"label":[""],"name":["_rn_"],"type":[""],"align":["left"]},{"label":["ID"],"name":[1],"type":["dbl"],"align":["right"]},{"label":["Year_Birth"],"name":[2],"type":["dbl"],"align":["right"]},{"label":["Income"],"name":[3],"type":["dbl"],"align":["right"]},{"label":["Kidhome"],"name":[4],"type":["dbl"],"align":["right"]},{"label":["Teenhome"],"name":[5],"type":["dbl"],"align":["right"]},{"label":["Recency"],"name":[6],"type":["dbl"],"align":["right"]},{"label":["MntWines"],"name":[7],"type":["dbl"],"align":["right"]},{"label":["MntFruits"],"name":[8],"type":["dbl"],"align":["right"]},{"label":["MntMeatProducts"],"name":[9],"type":["dbl"],"align":["right"]},{"label":["MntFishProducts"],"name":[10],"type":["dbl"],"align":["right"]},{"label":["MntSweetProducts"],"name":[11],"type":["dbl"],"align":["right"]},{"label":["MntGoldProds"],"name":[12],"type":["dbl"],"align":["right"]},{"label":["NumDealsPurchases"],"name":[13],"type":["dbl"],"align":["right"]},{"label":["NumWebPurchases"],"name":[14],"type":["dbl"],"align":["right"]},{"label":["NumCatalogPurchases"],"name":[15],"type":["dbl"],"align":["right"]},{"label":["NumStorePurchases"],"name":[16],"type":["dbl"],"align":["right"]},{"label":["NumWebVisitsMonth"],"name":[17],"type":["dbl"],"align":["right"]},{"label":["AcceptedCmp3"],"name":[18],"type":["dbl"],"align":["right"]},{"label":["AcceptedCmp4"],"name":[19],"type":["dbl"],"align":["right"]},{"label":["AcceptedCmp5"],"name":[20],"type":["dbl"],"align":["right"]},{"label":["AcceptedCmp1"],"name":[21],"type":["dbl"],"align":["right"]},{"label":["AcceptedCmp2"],"name":[22],"type":["dbl"],"align":["right"]},{"label":["Complain"],"name":[23],"type":["dbl"],"align":["right"]},{"label":["Response"],"name":[24],"type":["dbl"],"align":["right"]}],"data":[{"1":"0.00","2":"1893.00","3":"1730.00","4":"0.00","5":"0.00","6":"0.00","7":"0.00","8":"0.00","9":"0.00","10":"0.00","11":"0.00","12":"0.00","13":"0.00","14":"0.00","15":"0.00","16":"0.00","17":"0.00","18":"0.00","19":"0.00","20":"0.00","21":"0.00","22":"0.00","23":"0.00","24":"0.00","_rn_":"Min"},{"1":"2814.75","2":"1959.00","3":"35303.00","4":"0.00","5":"0.00","6":"24.00","7":"24.00","8":"2.00","9":"16.00","10":"3.00","11":"1.00","12":"9.00","13":"1.00","14":"2.00","15":"0.00","16":"3.00","17":"3.00","18":"0.00","19":"0.00","20":"0.00","21":"0.00","22":"0.00","23":"0.00","24":"0.00","_rn_":"Q1"},{"1":"5458.50","2":"1970.00","3":"51381.50","4":"0.00","5":"0.00","6":"49.00","7":"174.50","8":"8.00","9":"68.00","10":"12.00","11":"8.00","12":"24.50","13":"2.00","14":"4.00","15":"2.00","16":"5.00","17":"6.00","18":"0.00","19":"0.00","20":"0.00","21":"0.00","22":"0.00","23":"0.00","24":"0.00","_rn_":"Mediana"},{"1":"5588.35","2":"1968.82","3":"52247.25","4":"0.44","5":"0.51","6":"49.01","7":"305.09","8":"26.36","9":"167.00","10":"37.64","11":"27.03","12":"43.97","13":"2.32","14":"4.09","15":"2.67","16":"5.80","17":"5.32","18":"0.07","19":"0.07","20":"0.07","21":"0.06","22":"0.01","23":"0.01","24":"0.15","_rn_":"Media"},{"1":"8421.75","2":"1977.00","3":"68522.00","4":"1.00","5":"1.00","6":"74.00","7":"505.00","8":"33.00","9":"232.25","10":"50.00","11":"33.00","12":"56.00","13":"3.00","14":"6.00","15":"4.00","16":"8.00","17":"7.00","18":"0.00","19":"0.00","20":"0.00","21":"0.00","22":"0.00","23":"0.00","24":"0.00","_rn_":"Q3"},{"1":"11191.00","2":"1996.00","3":"666666.00","4":"2.00","5":"2.00","6":"99.00","7":"1493.00","8":"199.00","9":"1725.00","10":"259.00","11":"262.00","12":"321.00","13":"15.00","14":"27.00","15":"28.00","16":"13.00","17":"20.00","18":"1.00","19":"1.00","20":"1.00","21":"1.00","22":"1.00","23":"1.00","24":"1.00","_rn_":"Max"},{"1":"3249.38","2":"11.99","3":"25173.08","4":"0.54","5":"0.54","6":"28.95","7":"337.33","8":"39.79","9":"224.28","10":"54.75","11":"41.07","12":"51.82","13":"1.92","14":"2.74","15":"2.93","16":"3.25","17":"2.43","18":"0.26","19":"0.26","20":"0.26","21":"0.24","22":"0.12","23":"0.10","24":"0.36","_rn_":"DevPad"},{"1":"0.00","2":"0.00","3":"0.00","4":"0.00","5":"0.00","6":"0.00","7":"0.00","8":"0.00","9":"0.00","10":"0.00","11":"0.00","12":"0.00","13":"0.00","14":"0.00","15":"0.00","16":"0.00","17":"0.00","18":"0.00","19":"0.00","20":"0.00","21":"0.00","22":"0.00","23":"0.00","24":"0.00","_rn_":"N_missing"}],"options":{"columns":{"min":{},"max":[10]},"rows":{"min":[10],"max":[10]},"pages":{}}}
  </script>

</div>

# 3 Análises univariadas

## 3.1 ID (Identificador único do cliente)

``` r
summary(dados_1$ID)
```

       Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
          0    2815    5458    5588    8422   11191 

``` r
cat("Quantidade de valores distintos em ID é igual a", 
    length(unique(dados_1$ID)),"em um total de",dim(dados_1)[1],
    "linhas/valores.\n\nQuantidade de valores duplicados:",
    sum(duplicated(dados_1$ID)))
```

    Quantidade de valores distintos em ID é igual a 2216 em um total de 2216 linhas/valores.

    Quantidade de valores duplicados: 0

## 3.2 Year_Birth (Ano de nascimento do cliente)

``` r
summary(dados_1$Year_Birth)
```

       Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
       1893    1959    1970    1969    1977    1996 

``` r
boxplot(dados_1$Year_Birth,horizontal = T)
```

<img src="Customer_Personality_Analysis-V4_pt-sem_indice_float_files/figure-gfm/unnamed-chunk-13-1.png" style="display: block; margin: auto;" />

``` r
# Calcular a idade do cliente
dados_1$Idade <- round(year(Sys.Date())-dados_1$Year_Birth, digits = 2)

summary(dados_1$Idade)
```

       Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
      26.00   45.00   52.00   53.18   63.00  129.00 

``` r
boxplot(dados_1$Idade,horizontal = T)
```

<img src="Customer_Personality_Analysis-V4_pt-sem_indice_float_files/figure-gfm/unnamed-chunk-14-1.png" style="display: block; margin: auto;" />

``` r
# Percebe-se clientes com idade muito elevada
```

``` r
dados_1 <- dados_1[dados_1$Idade < 120,]

summary(dados_1$Idade)
```

       Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
      26.00   45.00   52.00   53.08   63.00   82.00 

``` r
# as dez idades mais frequentes
head(dados_1 %>% count(Idade) %>% arrange(desc(n)),10)
```

<div data-pagedtable="false">

<script data-pagedtable-source type="application/json">
{"columns":[{"label":[""],"name":["_rn_"],"type":[""],"align":["left"]},{"label":["Idade"],"name":[1],"type":["dbl"],"align":["right"]},{"label":["n"],"name":[2],"type":["int"],"align":["right"]}],"data":[{"1":"46","2":"89","_rn_":"1"},{"1":"51","2":"86","_rn_":"2"},{"1":"47","2":"83","_rn_":"3"},{"1":"50","2":"78","_rn_":"4"},{"1":"44","2":"76","_rn_":"5"},{"1":"52","2":"75","_rn_":"6"},{"1":"57","2":"74","_rn_":"7"},{"1":"49","2":"72","_rn_":"8"},{"1":"53","2":"70","_rn_":"9"},{"1":"48","2":"69","_rn_":"10"}],"options":{"columns":{"min":{},"max":[10]},"rows":{"min":[10],"max":[10]},"pages":{}}}
  </script>

</div>

## 3.3 Education (Nível de instrução do cliente)

``` r
# Corrigir categorias da variável Education
dados_1$Education[dados_1$Education %in% c("Basic","2n Cycle")] <- "Undergraduate"
dados_1$Education[dados_1$Education %in% c("Graduation","Master","PhD")] <- "Postgraduate"

cat("As categorias existentes em Education são:\n",
    unique(dados_1$Education),sep = "\n")
```

    As categorias existentes em Education são:

    Postgraduate
    Undergraduate

``` r
# Quantidade de Undergraduate e Postgraduate
n_educacao <- dados_1 %>% count(Education) %>% mutate(percentage= n/dim(dados_1)[1],
                      percent_lab = paste0(round(percentage*100,2),"%")) 

ggplot(data = n_educacao) +
  geom_col(aes(x = Education, y = n), width =0.5) +
  labs(x = "Educação",y = "Quantidade") +
  theme_bw() +
  geom_text(aes(x = Education, y = n,label=percent_lab), vjust = -0.5) +
  scale_y_continuous(limits = c(0,2100), labels = scales::comma)
```

<img src="Customer_Personality_Analysis-V4_pt-sem_indice_float_files/figure-gfm/unnamed-chunk-18-1.png" style="display: block; margin: auto;" />

## 3.4 Marital_Status (Estado civil do cliente)

``` r
unique(dados_1$Marital_Status)
```

    [1] "Single"   "Together" "Married"  "Divorced" "Widow"    "Alone"    "Absurd"  
    [8] "YOLO"    

``` r
# COrrigir classes da variável Marital_Status
dados_1$Marital_Status[dados_1$Marital_Status %in% c("Single","Divorced","Absurd","Widow","YOLO")] <- "Alone"
dados_1$Marital_Status[dados_1$Marital_Status %in% c("Married","Together")] <- "In couple"

cat("As classificações para o estado civil são: \n",unique(dados_1$Marital_Status)[1],unique(dados_1$Marital_Status)[2], sep = "\n")
```

    As classificações para o estado civil são: 

    Alone
    In couple

``` r
# Quantidade de Alone e In couple
n_marital <- dados_1 %>% count(Marital_Status) %>% 
  mutate(percentage = n/dim(dados_1)[1],
          percent_lab = paste0(round(percentage*100,2),"%"))

ggplot(data = n_marital) +
  geom_col(aes(x = Marital_Status, y = n), width =0.5) +
  labs(x = "Estado civil",y = "Quantidade") +
  theme_bw() +
  geom_text(aes(x = Marital_Status, y = n,label=percent_lab), vjust = -0.5) +
  scale_y_continuous(limits = c(0,1500))
```

<img src="Customer_Personality_Analysis-V4_pt-sem_indice_float_files/figure-gfm/unnamed-chunk-21-1.png" style="display: block; margin: auto;" />

## 3.5 Income (Renda familiar anual do cliente)

``` r
summary(dados_1$Income)
```

       Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
       1730   35246   51373   52237   68487  666666 

``` r
par(mfrow = c(1,2))
boxplot(dados_1$Income, horizontal = T,xlab = "Renda anual")
hist(dados_1$Income,breaks = 100, main = NULL,xlab = "Renda anual")
```

<img src="Customer_Personality_Analysis-V4_pt-sem_indice_float_files/figure-gfm/unnamed-chunk-22-1.png" style="display: block; margin: auto;" />

``` r
# Existe a presença de outliers!!! 
```

``` r
# Eliminar valor discrepante da variável Income
dados_1 <- dados_1[dados_1$Income < 600000,]
```

``` r
summary(dados_1$Income)
```

       Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
       1730   35234   51371   51959   68487  162397 

``` r
par(mfrow = c(1,2))
boxplot(dados_1$Income, horizontal = T, xlab = "Renda anual")
hist(dados_1$Income,breaks = 100,xlab = "Renda anual", main = NULL)
```

<img src="Customer_Personality_Analysis-V4_pt-sem_indice_float_files/figure-gfm/unnamed-chunk-24-1.png" style="display: block; margin: auto;" />

## 3.6 Kidhome e Teenhome (Número de crianças e adolescentes na residência do cliente)

``` r
unique(dados_1$Kidhome)
```

    [1] 0 1 2

``` r
unique(dados_1$Teenhome)
```

    [1] 0 1 2

``` r
percent_kidhome <- as.data.frame(prop.table(table(dados_1$Kidhome)))
g1 <- ggplot(data = percent_kidhome) +
  geom_col(aes(x = Var1, y = Freq), width =0.5) +
  labs(x="Nº de crianças",y = "Percentual", title = "kidhome") +
  scale_y_continuous(limits = c(0,1), labels = scales::percent) +
  theme_bw()

percent_Teenhome <- as.data.frame(prop.table(table(dados_1$Teenhome)))
g2 <- ggplot(data = percent_Teenhome) +
  geom_col(aes(x = Var1, y = Freq), width =0.5) +
  labs(x="Nº de adolescentes",y = "Percentual", title = "Teenhome") +
  scale_y_continuous(limits = c(0,1), labels = scales::percent) +
  theme_bw()
(g1+g2)
```

<img src="Customer_Personality_Analysis-V4_pt-sem_indice_float_files/figure-gfm/unnamed-chunk-26-1.png" style="display: block; margin: auto;" />

``` r
# Cálculo do total de Filhos
dados_1$N_Children <- dados_1$Kidhome + dados_1$Teenhome 
```

``` r
dados_1$Has_Children <- ifelse(dados_1$N_Children > 0,"Has child","No child")
unique(dados_1$Has_Children)
```

    [1] "No child"  "Has child"

``` r
dados_1$Children <- ifelse(dados_1$N_Children == 3, "3 children",
                                ifelse(dados_1$N_Children == 2, "2 children",
                                       ifelse(dados_1$N_Children == 1, "1 children",
                                              "No children")))
unique(dados_1$N_Children); unique(dados_1$Children)
```

    [1] 0 2 1 3

    [1] "No children" "2 children"  "1 children"  "3 children" 

``` r
percent_Children <- as.data.frame(prop.table(table(dados_1$Children)))
percent_Children$Var1 <- factor(percent_Children$Var1,
                                   levels= c("No children","1 children",
                                             "2 children","3 children"))

ggplot(data = percent_Children) +
  geom_col(aes(x = Var1, y = Freq), width =0.5) +
  labs(x="Nº de filhos",y = "Percentual") +
  scale_y_continuous(limits = c(0,1),labels = scales::percent_format(scale = 100,accuracy =5L)) +
  theme_bw()
```

<img src="Customer_Personality_Analysis-V4_pt-sem_indice_float_files/figure-gfm/unnamed-chunk-29-1.png" style="display: block; margin: auto;" />

## 3.7 Dt_Customer (Data do cadastro do cliente na empresa)

``` r
dados_1$Dt_Customer <- as_date(dmy(dados_1$Dt_Customer))
class(dados_1$Dt_Customer)
```

    [1] "Date"

``` r
#(min(dados_1$Dt_Customer) %--% max(dados_1$Dt_Customer) %/% days(x=1))/365
summary(dados_1$Dt_Customer)
```

            Min.      1st Qu.       Median         Mean      3rd Qu.         Max. 
    "2012-07-30" "2013-01-16" "2013-07-08" "2013-07-10" "2013-12-31" "2014-06-29" 

``` r
# quantidade de dias desde a inscrição do cliente na empresa até o dia atual
dados_1$Dt_inscricao_ate_atual <- Sys.Date() - dados_1$Dt_Customer
dados_1$Dt_inscricao_ate_atual <- as.numeric(dados_1$Dt_inscricao_ate_atual)

summary(dados_1$Dt_inscricao_ate_atual)
```

       Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
       2843    3023    3199    3197    3372    3542 

## 3.8 Recency (Quantidade de dias desde a última compra do cliente)

``` r
summary(dados_1$Recency)
```

       Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
       0.00   24.00   49.00   49.02   74.00   99.00 

## 3.9 Variáveis MntWines, MntFruits, MntMeatProducts, MntFishProducts, MntSweetProducts e MntGoldProds

``` r
summary(dados_1$MntWines)
```

       Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
        0.0    24.0   175.5   305.3   505.0  1493.0 

``` r
summary(dados_1$MntFruits)
```

       Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
       0.00    2.00    8.00   26.33   33.00  199.00 

``` r
summary(dados_1$MntMeatProducts)
```

       Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
        0.0    16.0    68.0   167.0   232.2  1725.0 

``` r
summary(dados_1$MntFishProducts)
```

       Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
       0.00    3.00   12.00   37.65   50.00  259.00 

``` r
summary(dados_1$MntSweetProducts)
```

       Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
       0.00    1.00    8.00   27.05   33.00  262.00 

``` r
summary(dados_1$MntGoldProds)
```

       Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
       0.00    9.00   24.50   43.93   56.00  321.00 

``` r
# Calcular a quantia total gasta nos últimos 2 anos
dados_1$Gasto_total <- dados_1$MntWines + dados_1$MntFruits + dados_1$MntMeatProducts +
  dados_1$MntFishProducts + dados_1$MntSweetProducts + dados_1$MntGoldProds

# MntWines: Amount spent on wine in last 2 years
# MntFruits: Amount spent on fruits in last 2 years
# MntMeatProducts: Amount spent on meat in last 2 years
# MntFishProducts: Amount spent on fish in last 2 years
# MntSweetProducts: Amount spent on sweets in last 2 years
# MntGoldProds: Amount spent on gold in last 2 years
```

``` r
summary(dados_1$Gasto_total)
```

       Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
        5.0    69.0   397.0   607.3  1048.0  2525.0 

``` r
par(mfrow = c(1,2))
boxplot(dados_1$Gasto_total,horizontal = T,xlab ="Gasto total")
hist(dados_1$Gasto_total, breaks = 100,xlab ="Gasto total", main = NULL)
```

<img src="Customer_Personality_Analysis-V4_pt-sem_indice_float_files/figure-gfm/unnamed-chunk-35-1.png" style="display: block; margin: auto;" />

``` r
head(dados_1 %>% arrange(desc(Gasto_total)) %>%
  select("Marital_Status","Education","Idade","Income","Gasto_total"),10)
```

<div data-pagedtable="false">

<script data-pagedtable-source type="application/json">
{"columns":[{"label":[""],"name":["_rn_"],"type":[""],"align":["left"]},{"label":["Marital_Status"],"name":[1],"type":["chr"],"align":["left"]},{"label":["Education"],"name":[2],"type":["chr"],"align":["left"]},{"label":["Idade"],"name":[3],"type":["dbl"],"align":["right"]},{"label":["Income"],"name":[4],"type":["int"],"align":["right"]},{"label":["Gasto_total"],"name":[5],"type":["int"],"align":["right"]}],"data":[{"1":"Alone","2":"Postgraduate","3":"31","4":"90638","5":"2525","_rn_":"1"},{"1":"Alone","2":"Postgraduate","3":"31","4":"90638","5":"2525","_rn_":"2"},{"1":"In couple","2":"Postgraduate","3":"34","4":"87679","5":"2524","_rn_":"3"},{"1":"In couple","2":"Postgraduate","3":"53","4":"75759","5":"2486","_rn_":"4"},{"1":"In couple","2":"Postgraduate","3":"73","4":"69098","5":"2440","_rn_":"5"},{"1":"In couple","2":"Postgraduate","3":"66","4":"90226","5":"2352","_rn_":"6"},{"1":"Alone","2":"Postgraduate","3":"52","4":"93790","5":"2349","_rn_":"7"},{"1":"In couple","2":"Postgraduate","3":"50","4":"83151","5":"2346","_rn_":"8"},{"1":"In couple","2":"Postgraduate","3":"69","4":"94384","5":"2302","_rn_":"9"},{"1":"In couple","2":"Postgraduate","3":"69","4":"94384","5":"2302","_rn_":"10"}],"options":{"columns":{"min":{},"max":[10]},"rows":{"min":[10],"max":[10]},"pages":{}}}
  </script>

</div>

## 3.10 NumDealsPurchases (Número de compras feitas com desconto)

``` r
summary(dados_1$NumDealsPurchases)
```

       Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
      0.000   1.000   2.000   2.325   3.000  15.000 

``` r
par(mfrow = c(1,2))
boxplot(dados_1$NumDealsPurchases, horizontal = T,xlab ="Compras com desconto")
hist(dados_1$NumDealsPurchases, breaks = 100,xlab ="Compras com desconto", main = NULL)
```

<img src="Customer_Personality_Analysis-V4_pt-sem_indice_float_files/figure-gfm/unnamed-chunk-37-1.png" style="display: block; margin: auto;" />

``` r
# Quantidade de compra realizada com desconto
dados_1 %>% count(NumDealsPurchases)
```

<div data-pagedtable="false">

<script data-pagedtable-source type="application/json">
{"columns":[{"label":["NumDealsPurchases"],"name":[1],"type":["int"],"align":["right"]},{"label":["n"],"name":[2],"type":["int"],"align":["right"]}],"data":[{"1":"0","2":"44"},{"1":"1","2":"957"},{"1":"2","2":"493"},{"1":"3","2":"293"},{"1":"4","2":"187"},{"1":"5","2":"94"},{"1":"6","2":"60"},{"1":"7","2":"39"},{"1":"8","2":"14"},{"1":"9","2":"8"},{"1":"10","2":"5"},{"1":"11","2":"5"},{"1":"12","2":"3"},{"1":"13","2":"3"},{"1":"15","2":"7"}],"options":{"columns":{"min":{},"max":[10]},"rows":{"min":[10],"max":[10]},"pages":{}}}
  </script>

</div>

## 3.11 NumWebPurchases, NumCatalogPurchases e NumStorePurchases

``` r
# Número total de compras por cliente
dados_1$Numero_compras <- dados_1$NumWebPurchases + dados_1$NumCatalogPurchases + 
  dados_1$NumStorePurchases
```

``` r
summary(dados_1$Numero_compras)
```

       Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
       0.00    6.00   12.00   12.57   18.25   32.00 

``` r
par(mfrow = c(1,2))
boxplot(dados_1$Numero_compras,xlab ="Nº de compras por cliente", horizontal = T)
hist(dados_1$Numero_compras, breaks = 100,xlab ="Nº de compras por cliente", main = NULL)
```

<img src="Customer_Personality_Analysis-V4_pt-sem_indice_float_files/figure-gfm/unnamed-chunk-40-1.png" style="display: block; margin: auto;" />

``` r
local <- c("Web","Catalogo","Store")
valor <- c(sum(dados_1$NumWebPurchases),
           sum(dados_1$NumCatalogPurchases),
           sum(dados_1$NumStorePurchases))
local_vendas <- data.frame(local,valor)
local_vendas$local <- factor(local_vendas$local, levels = c("Catalogo","Web","Store"))

ggplot(data = local_vendas) +
  geom_col(aes(x = reorder(local,-valor), y = valor), width = 0.5) +
  labs(x = "Local de compra",y = "Quantidade total comprada em cada local") +
  theme_bw() + geom_text(aes(x = local, y = valor,label=valor), vjust = -0.5) +
  scale_y_continuous(limits = c(0,14000))
```

<img src="Customer_Personality_Analysis-V4_pt-sem_indice_float_files/figure-gfm/unnamed-chunk-41-1.png" style="display: block; margin: auto;" />

## 3.12 NumWebVisitsMonth (Número de visitas ao site da empresa no último mês)

``` r
summary(dados_1$NumWebVisitsMonth)
```

       Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
      0.000   3.000   6.000   5.321   7.000  20.000 

## 3.13 Variáveis AcceptedCmp1, AcceptedCmp2, AcceptedCmp3, AcceptedCmp4 e AcceptedCmp5

``` r
unique(dados_1$AcceptedCmp1)
```

    [1] 0 1

``` r
unique(dados_1$AcceptedCmp2)
```

    [1] 0 1

``` r
unique(dados_1$AcceptedCmp3)
```

    [1] 0 1

``` r
unique(dados_1$AcceptedCmp4)
```

    [1] 0 1

``` r
unique(dados_1$AcceptedCmp5)
```

    [1] 0 1

``` r
# AcceptedCmp1: 1 if customer accepted the offer in the 1st campaign, 0 otherwise
# AcceptedCmp2: 1 if customer accepted the offer in the 2nd campaign, 0 otherwise
# AcceptedCmp3: 1 if customer accepted the offer in the 3rd campaign, 0 otherwise
# AcceptedCmp4: 1 if customer accepted the offer in the 4th campaign, 0 otherwise
# AcceptedCmp5: 1 if customer accepted the offer in the 5th campaign, 0 otherwise
```

``` r
dados_1$Num_campaign_acc <- dados_1$AcceptedCmp1 + dados_1$AcceptedCmp2 + dados_1$AcceptedCmp3 + dados_1$AcceptedCmp4 + dados_1$AcceptedCmp5

unique(dados_1$Num_campaign_acc)
```

    [1] 0 1 2 3 4

``` r
n_campaign_acc <- dados_1 %>% count(Num_campaign_acc) %>% mutate(perc_camp = n/sum(n),
                                                                 perc_lab = paste0(round(perc_camp*100,2),"%"))
n_campaign_acc$Num_campaign_acc <-  as.factor(n_campaign_acc$Num_campaign_acc)

ggplot(data = n_campaign_acc) +
  geom_col(aes(x = Num_campaign_acc, y = n), width = 0.5) +
  labs(x = "Campanhas aceitas",y = "Quantidade") +
  theme_bw() + geom_text(aes(x = Num_campaign_acc, y = n,label=perc_lab), vjust = -0.5) +
  scale_y_continuous(limits = c(0,2000))
```

<img src="Customer_Personality_Analysis-V4_pt-sem_indice_float_files/figure-gfm/unnamed-chunk-45-1.png" style="display: block; margin: auto;" />

## 3.14 Complain (1 se o cliente reclamou nos últimos 2 anos, 0 caso contrário)

``` r
unique(dados_1$Complain)
```

    [1] 0 1

``` r
cat("Foram feitas um total de",sum(dados_1$Complain),"reclamações.")
```

    Foram feitas um total de 20 reclamações.

``` r
n_complain <- dados_1 %>% count(Complain)
n_complain$Complain <-  as.factor(n_complain$Complain)

ggplot(data = n_complain) +
  geom_col(aes(x = Complain, y = n), width = 0.5) +
  labs(x = "Complain",y = "Quantidade") +
  theme_bw()
```

<img src="Customer_Personality_Analysis-V4_pt-sem_indice_float_files/figure-gfm/unnamed-chunk-47-1.png" style="display: block; margin: auto;" />

## 3.15 Response (1 se o cliente aceitou a oferta na última campanha, 0 caso contrário)

``` r
unique(dados_1$Response)
```

    [1] 1 0

``` r
cat("Foram aceitas um total de",sum(dados_1$Response),"ofertas na última campanha.")
```

    Foram aceitas um total de 333 ofertas na última campanha.

``` r
n_response <- dados_1 %>% count(Response)
n_response$Response <-  as.factor(n_response$Response)

ggplot(data = n_response) +
  geom_col(aes(x = Response, y = n), width = 0.5) +
  labs(x = "Response",y = "Quantidade") +
  theme_bw()
```

<img src="Customer_Personality_Analysis-V4_pt-sem_indice_float_files/figure-gfm/unnamed-chunk-49-1.png" style="display: block; margin: auto;" />

## 3.16 Prosseguir apenas com as colunas que seja de interesse para as análies

``` r
dados_2 <- dados_1 %>% select(-c("ID","Kidhome","Teenhome","MntWines","MntFruits",                                             "MntMeatProducts","MntFishProducts","MntSweetProducts","MntGoldProds",
                    "NumWebPurchases","NumCatalogPurchases","NumStorePurchases",
                    "AcceptedCmp3","AcceptedCmp4","AcceptedCmp5","AcceptedCmp1",
                    "AcceptedCmp2"))

df_eda <- dados_2 %>% select("Year_Birth","Idade","Dt_Customer","Dt_inscricao_ate_atual",
                             "Education","Marital_Status","Has_Children","N_Children",
                             "Children","Income","Gasto_total","Numero_compras",
                             "Num_campaign_acc","NumDealsPurchases","NumWebVisitsMonth",
                             "Recency","Complain","Response")
```

## 3.17 Calcular o valor médio por compra

``` r
df_eda_1 <- df_eda[df_eda$Numero_compras > 0,]  #são eliminas apenas 6 linhas

# Número médio de compra por cliente
df_eda_1$Valor_medio_de_compra <- round(df_eda_1$Gasto_total/df_eda_1$Numero_compras, 
                                       digits = 2)
```

# 4 Análise gráfica

## 4.1 Gráfico de barras

### 4.1.1 Nível educacional x Gasto_total

``` r
# Gasto por nível educacional
Gst_niv_educ <- df_eda_1 %>% group_by(Education) %>% summarise(Gasto_Edu = sum(Gasto_total)) %>% 
  mutate(perc_gasto = Gasto_Edu/sum(Gasto_Edu),
         perc_lab = paste0(round(perc_gasto*100,2),"%"))

ggplot(data = Gst_niv_educ) +
  geom_col(aes(x = Education,y = Gasto_Edu), width = 0.5) +
  labs(x="Nível educacional",y = "Valor gasto") +
  theme_bw() + geom_text(aes(x = Education,y = Gasto_Edu,label=perc_lab), vjust = -0.5) +
  scale_y_continuous(limits = c(0,1300000), labels = scales::comma)
```

<img src="Customer_Personality_Analysis-V4_pt-sem_indice_float_files/figure-gfm/unnamed-chunk-52-1.png" style="display: block; margin: auto;" />

### 4.1.2 Estado civil x Gasto_total

``` r
# gasto por estado civil
Gst_est_civ <- df_eda_1 %>% group_by(Marital_Status) %>% summarise(Gasto_Marital = sum(Gasto_total)) %>% 
  mutate(perc_gasto = Gasto_Marital/sum(Gasto_Marital),
         perc_lab = paste0(round(perc_gasto*100,2),"%"))

ggplot(data = Gst_est_civ) +
  geom_col(aes(x = Marital_Status,y = Gasto_Marital), width = 0.5) +
  labs(x="Estado civil",y = "Valor gasto") +
  theme_bw()  + geom_text(aes(x = Marital_Status,y = Gasto_Marital,label=perc_lab), vjust = -0.5) +
  scale_y_continuous(limits = c(0,1000000), labels = scales::comma)
```

<img src="Customer_Personality_Analysis-V4_pt-sem_indice_float_files/figure-gfm/unnamed-chunk-53-1.png" style="display: block; margin: auto;" />

### 4.1.3 Número de filhos x Gasto_total

``` r
# gasto por quantidade de filhos
Gst_n_Children <- df_eda_1 %>% group_by(Children) %>% summarise(Gasto_Child = sum(Gasto_total)) %>% 
  mutate(perc_gasto = Gasto_Child/sum(Gasto_Child),
         perc_lab = paste0(round(perc_gasto*100,2),"%"))


Gst_n_Children$Children <- factor(Gst_n_Children$Children, levels = c("No children","1 children","2 children","3 children"))

ggplot(data = Gst_n_Children) +
  geom_col(aes(x = Children,y = Gasto_Child), width = 0.5) +
  labs(x = "Nº de filhos",y = "Valor gasto") +
  theme_bw()  + geom_text(aes(x = Children,y = Gasto_Child,label=perc_lab), vjust = -0.5) +
  scale_y_continuous(limits = c(0,800000), labels = scales::comma)
```

<img src="Customer_Personality_Analysis-V4_pt-sem_indice_float_files/figure-gfm/unnamed-chunk-54-1.png" style="display: block; margin: auto;" />

### 4.1.4 Número de campanhas aceitas x Gasto_total

``` r
# gasto pelo número de campanhas aceitas
Gst_campaign_acc <- df_eda_1 %>% 
  group_by(Num_campaign_acc) %>% summarise(Gasto_camp_acc = sum(Gasto_total)) %>% 
  mutate(perc_gasto_camp = round((Gasto_camp_acc/sum(Gasto_camp_acc))*100,2),
         perc_lab = paste0(perc_gasto_camp,"%"))

ggplot(data = Gst_campaign_acc) +
  geom_col(aes(x = Num_campaign_acc,y = Gasto_camp_acc), width = 0.5) +
  labs(x = "Campanhas aceitas",y = "Valor gasto") +
  theme_bw() + geom_text(aes(x = Num_campaign_acc,y = Gasto_camp_acc,label = perc_lab), vjust = -0.5) +
  scale_y_continuous(limits = c(0,1000000), breaks = c(0,200000,400000,600000,800000,1000000),
                     labels = scales::comma)
```

<img src="Customer_Personality_Analysis-V4_pt-sem_indice_float_files/figure-gfm/unnamed-chunk-55-1.png" style="display: block; margin: auto;" />

## 4.2 Gráfico de dispersão

``` r
df_eda_1 %>% group_by(Education) %>% count()
```

<div data-pagedtable="false">

<script data-pagedtable-source type="application/json">
{"columns":[{"label":["Education"],"name":[1],"type":["chr"],"align":["left"]},{"label":["n"],"name":[2],"type":["int"],"align":["right"]}],"data":[{"1":"Postgraduate","2":"1954"},{"1":"Undergraduate","2":"252"}],"options":{"columns":{"min":{},"max":[10]},"rows":{"min":[10],"max":[10]},"pages":{}}}
  </script>

</div>

``` r
df_eda_1 %>% group_by(Marital_Status) %>% count()
```

<div data-pagedtable="false">

<script data-pagedtable-source type="application/json">
{"columns":[{"label":["Marital_Status"],"name":[1],"type":["chr"],"align":["left"]},{"label":["n"],"name":[2],"type":["int"],"align":["right"]}],"data":[{"1":"Alone","2":"780"},{"1":"In couple","2":"1426"}],"options":{"columns":{"min":{},"max":[10]},"rows":{"min":[10],"max":[10]},"pages":{}}}
  </script>

</div>

``` r
df_eda_1 %>% group_by(Has_Children) %>% count()
```

<div data-pagedtable="false">

<script data-pagedtable-source type="application/json">
{"columns":[{"label":["Has_Children"],"name":[1],"type":["chr"],"align":["left"]},{"label":["n"],"name":[2],"type":["int"],"align":["right"]}],"data":[{"1":"Has child","2":"1578"},{"1":"No child","2":"628"}],"options":{"columns":{"min":{},"max":[10]},"rows":{"min":[10],"max":[10]},"pages":{}}}
  </script>

</div>

``` r
df_eda_1 %>% group_by(Children) %>% count()
```

<div data-pagedtable="false">

<script data-pagedtable-source type="application/json">
{"columns":[{"label":["Children"],"name":[1],"type":["chr"],"align":["left"]},{"label":["n"],"name":[2],"type":["int"],"align":["right"]}],"data":[{"1":"1 children","2":"1113"},{"1":"2 children","2":"415"},{"1":"3 children","2":"50"},{"1":"No children","2":"628"}],"options":{"columns":{"min":{},"max":[10]},"rows":{"min":[10],"max":[10]},"pages":{}}}
  </script>

</div>

### 4.2.1 Renda anual x Valor médio por compra

-   Disciminando por educacão

``` r
ggplot(data = df_eda_1) +
  geom_point(aes(x = Income, y = Valor_medio_de_compra, color = Education),size=1.8) +
  labs(x="Renda anual",y="Valor médio por compra") +
  theme_bw() +
  scale_colour_manual("Nível educacional", values = c("darkorchid","deepskyblue1"))
```

<img src="Customer_Personality_Analysis-V4_pt-sem_indice_float_files/figure-gfm/unnamed-chunk-57-1.png" style="display: block; margin: auto;" />

-   Disciminando por quantidade de filhos

``` r
df_eda_1$Children <- factor(df_eda_1$Children, levels = c("3 children","2 children",
                                                          "1 children","No children"))


ggplot(data = df_eda_1) +
  geom_point(aes(x = Income, y = Valor_medio_de_compra, color = Children),size=1.8) +
  labs(x="Renda anual",y="Valor médio por compra") +
  theme_bw() +
  scale_colour_manual("Nº de filhos", values = c("deepskyblue1","antiquewhite3","forestgreen","darkorchid"))
```

<img src="Customer_Personality_Analysis-V4_pt-sem_indice_float_files/figure-gfm/unnamed-chunk-58-1.png" style="display: block; margin: auto;" />

### 4.2.2 Renda anual x Gasto total

-   Disciminando por quantidade de filhos

``` r
ggplot(data = df_eda_1) +
  geom_point(aes(x = Income, y = Gasto_total, color = Children),size=1.8) +
  labs(x="Renda anual",y="Gasto total") +
  theme_bw() +
  scale_colour_manual("Nº de filhos", values = c("deepskyblue1","antiquewhite3","forestgreen","darkorchid"))
```

<img src="Customer_Personality_Analysis-V4_pt-sem_indice_float_files/figure-gfm/unnamed-chunk-59-1.png" style="display: block; margin: auto;" />

# 5 Correlação entre variáveis

<img src="Customer_Personality_Analysis-V4_pt-sem_indice_float_files/figure-gfm/unnamed-chunk-60-1.png" style="display: block; margin: auto;" />

# 6 Gerar clusters

## 6.1 Renda Anual e gasto total

``` r
X1 = data.frame(Renda_anual = df_eda_1$Income, 
               Gasto_em_compras = df_eda_1$Gasto_total)

X1 = scale(X1)
```

``` r
set.seed(1)
wcss = vector()
for (i in 1:10) {
  kmeans = kmeans(x = X1, centers = i)
  wcss[i] = sum(kmeans$withinss)
}

ggplot(data = data.frame(n = c(1:10),WCSS = wcss),aes(x = n, y=WCSS)) +
  geom_line(size=0.7,linetype = 1,lineend   = "round",linejoin = "round",linemitre=1) + 
  geom_point(size = 2.5) +
  labs(x="Número de clusters (k)",y="WCSS") +
  scale_x_continuous(breaks = seq(0,10,2)) +
  theme_bw()
```

<img src="Customer_Personality_Analysis-V4_pt-sem_indice_float_files/figure-gfm/unnamed-chunk-62-1.png" style="display: block; margin: auto;" />

``` r
set.seed(3)
kmeans = kmeans(x = X1, centers = 2)
previsoes = kmeans$cluster

X1 <- as.data.frame(X1)

pairs(X1, col = c(1:4)[previsoes])
```

<img src="Customer_Personality_Analysis-V4_pt-sem_indice_float_files/figure-gfm/unnamed-chunk-63-1.png" style="display: block; margin: auto;" />

``` r
df_resumo <- data.frame(Income=df_eda_1$Income,Gasto_total=df_eda_1$Gasto_total,Previsoes=previsoes) %>% 
  group_by(Previsoes) %>% 
  summarise(Renda_media= mean(Income), Gasto_medio = mean(Gasto_total))

previsoes = as.factor(previsoes)
df_resumo$Previsoes = as.factor(df_resumo$Previsoes)
ggplot(data = df_eda_1) +
  geom_point(aes(x=Income,y=Gasto_total,color=previsoes,fill=previsoes),size=1.8,shape=19) +
  geom_point(data=df_resumo, aes(x=Renda_media,y=Gasto_medio,color=Previsoes,fill=Previsoes), size = 5,shape=21) +
  labs(x="Renda anual",y="Gasto total em compras") +
  scale_colour_manual("Clusters",values = c("forestgreen","darkorchid2"),
                      labels = c("Cluster 1", "Cluster 2")) + 
  scale_fill_manual(name="Centroides", values=c("black","gray25")) + theme_bw()
```

<img src="Customer_Personality_Analysis-V4_pt-sem_indice_float_files/figure-gfm/unnamed-chunk-64-1.png" style="display: block; margin: auto;" />

## 6.2 Renda Anual e Idade

``` r
X2 = data.frame(Renda_anual = df_eda_1$Income, 
                Idade = df_eda_1$Idade)

X2 = scale(X2)
```

``` r
set.seed(1)
wcss2 = vector()
for (i in 1:10) {
  kmeans2 = kmeans(x = X2, centers = i)
  wcss2[i] = sum(kmeans2$withinss)
}

ggplot(data = data.frame(n = c(1:10),WCSS = wcss2),aes(x = n, y=WCSS)) +
  geom_line(size=0.7,linetype = 1,lineend   = "round",linejoin = "round",linemitre=1) + 
  geom_point(size = 2.5) +
  labs(x="Número de clusters (k)",y="WCSS") +
  scale_x_continuous(breaks = seq(0,10,2)) +
  theme_bw()
```

<img src="Customer_Personality_Analysis-V4_pt-sem_indice_float_files/figure-gfm/unnamed-chunk-66-1.png" style="display: block; margin: auto;" />

``` r
set.seed(3)
kmeans2 = kmeans(x = X2, centers = 3)
previsoes2 = kmeans2$cluster

X2 <- as.data.frame(X2)

pairs(X2, col = c(1:4)[previsoes2])
```

<img src="Customer_Personality_Analysis-V4_pt-sem_indice_float_files/figure-gfm/unnamed-chunk-67-1.png" style="display: block; margin: auto;" />

``` r
df_resumo2 <- data.frame(Income=df_eda_1$Income,Gasto_total=df_eda_1$Gasto_total,Previsoes=previsoes2,Idade=df_eda_1$Idade) %>% group_by(Previsoes) %>% 
  summarise(Renda_media= mean(Income), Gasto_medio = mean(Gasto_total),Idade_media = mean(Idade), max_renda =max(Income))


previsoes2 = as.factor(previsoes2)
df_resumo2$Previsoes = as.factor(df_resumo2$Previsoes)
ggplot(data = df_eda_1) +
  geom_point(aes(y=Income,x=Idade,color=previsoes2,fill=previsoes2),size=1.8,shape=19) +
  geom_point(data=df_resumo2, aes(y=Renda_media,x=Idade_media,color=Previsoes,fill=Previsoes), size = 5,shape=21) +
  labs(y="Renda anual",x=NULL, subtitle = "(a)") +
  scale_colour_manual("Clusters",values = c("forestgreen","darkorchid2","deepskyblue1","black","red"),
                      labels = c("Cluster 1", "Cluster 2","Cluster 3")) + 
  scale_fill_manual(name="Centroides", values=c("black","blue","gray25","white","red")) + theme_bw()
```

<img src="Customer_Personality_Analysis-V4_pt-sem_indice_float_files/figure-gfm/unnamed-chunk-68-1.png" style="display: block; margin: auto;" />

## 6.3 Gasto total e Idade

``` r
X3 = data.frame(Gasto = df_eda_1$Gasto_total, 
                Idade = df_eda_1$Idade)

X3 = scale(X3)
```

``` r
set.seed(1)
wcss3 = vector()
for (i in 1:10) {
  kmeans3 = kmeans(x = X3, centers = i)
  wcss3[i] = sum(kmeans3$withinss)
}
ggplot(data = data.frame(n = c(1:10),WCSS = wcss3),aes(x = n, y=wcss3)) +
  geom_line(size=0.7,linetype = 1,lineend   = "round",linejoin = "round",linemitre=1) + 
  geom_point(size = 2.5) +
  labs(x="Número de clusters (k)",y="WCSS") +
  scale_x_continuous(breaks = seq(0,10,2)) +
  theme_bw()
```

<img src="Customer_Personality_Analysis-V4_pt-sem_indice_float_files/figure-gfm/unnamed-chunk-70-1.png" style="display: block; margin: auto;" />

``` r
set.seed(3)
kmeans3 = kmeans(x = X3, centers = 3)
previsoes3 = kmeans3$cluster

X3 <- as.data.frame(X3)

pairs(X3, col = c(1:4)[previsoes3])
```

<img src="Customer_Personality_Analysis-V4_pt-sem_indice_float_files/figure-gfm/unnamed-chunk-71-1.png" style="display: block; margin: auto;" />

``` r
df_resumo3 <- data.frame(Income=df_eda_1$Income,Gasto_total=df_eda_1$Gasto_total,Previsoes=previsoes3,Idade=df_eda_1$Idade) %>%  group_by(Previsoes) %>% 
  summarise(Renda_media= mean(Income), Gasto_medio = mean(Gasto_total),Idade_media = mean(Idade))

previsoes3 = as.factor(previsoes3)
df_resumo3$Previsoes = as.factor(df_resumo3$Previsoes)
ggplot(data = df_eda_1) +
  geom_point(aes(y=Gasto_total,x=Idade,color=previsoes3,fill=previsoes3),size=1.8,shape=19) +
  geom_point(data=df_resumo3, aes(y=Gasto_medio,x=Idade_media,color=Previsoes,fill=Previsoes), size = 5,shape=21) +
  labs(y="Gasto em compras",x="Idade", subtitle = "(b)") +
  scale_colour_manual("Clusters",values = c("forestgreen","darkorchid2","deepskyblue1","black","red"),
                      labels = c("Cluster 1", "Cluster 2","Cluster 3")) + 
  scale_fill_manual(name="Centroides", values=c("black","blue","gray25","white","red")) + theme_bw()
```

<img src="Customer_Personality_Analysis-V4_pt-sem_indice_float_files/figure-gfm/unnamed-chunk-72-1.png" style="display: block; margin: auto;" />
