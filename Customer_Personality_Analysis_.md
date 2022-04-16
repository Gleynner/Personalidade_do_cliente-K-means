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

         ID Year_Birth  Education Marital_Status Income Kidhome Teenhome
    1  5524       1957 Graduation         Single  58138       0        0
    2  2174       1954 Graduation         Single  46344       1        1
    3  4141       1965 Graduation       Together  71613       0        0
    4  6182       1984 Graduation       Together  26646       1        0
    5  5324       1981        PhD        Married  58293       1        0
    6  7446       1967     Master       Together  62513       0        1
    7   965       1971 Graduation       Divorced  55635       0        1
    8  6177       1985        PhD        Married  33454       1        0
    9  4855       1974        PhD       Together  30351       1        0
    10 5899       1950        PhD       Together   5648       1        1
       Dt_Customer Recency MntWines MntFruits MntMeatProducts MntFishProducts
    1   04-09-2012      58      635        88             546             172
    2   08-03-2014      38       11         1               6               2
    3   21-08-2013      26      426        49             127             111
    4   10-02-2014      26       11         4              20              10
    5   19-01-2014      94      173        43             118              46
    6   09-09-2013      16      520        42              98               0
    7   13-11-2012      34      235        65             164              50
    8   08-05-2013      32       76        10              56               3
    9   06-06-2013      19       14         0              24               3
    10  13-03-2014      68       28         0               6               1
       MntSweetProducts MntGoldProds NumDealsPurchases NumWebPurchases
    1                88           88                 3               8
    2                 1            6                 2               1
    3                21           42                 1               8
    4                 3            5                 2               2
    5                27           15                 5               5
    6                42           14                 2               6
    7                49           27                 4               7
    8                 1           23                 2               4
    9                 3            2                 1               3
    10                1           13                 1               1
       NumCatalogPurchases NumStorePurchases NumWebVisitsMonth AcceptedCmp3
    1                   10                 4                 7            0
    2                    1                 2                 5            0
    3                    2                10                 4            0
    4                    0                 4                 6            0
    5                    3                 6                 5            0
    6                    4                10                 6            0
    7                    3                 7                 6            0
    8                    0                 4                 8            0
    9                    0                 2                 9            0
    10                   0                 0                20            1
       AcceptedCmp4 AcceptedCmp5 AcceptedCmp1 AcceptedCmp2 Complain Z_CostContact
    1             0            0            0            0        0             3
    2             0            0            0            0        0             3
    3             0            0            0            0        0             3
    4             0            0            0            0        0             3
    5             0            0            0            0        0             3
    6             0            0            0            0        0             3
    7             0            0            0            0        0             3
    8             0            0            0            0        0             3
    9             0            0            0            0        0             3
    10            0            0            0            0        0             3
       Z_Revenue Response
    1         11        1
    2         11        0
    3         11        0
    4         11        0
    5         11        0
    6         11        0
    7         11        0
    8         11        0
    9         11        1
    10        11        0

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

                  Variavel      Tipo    N Missing Missing_Percent N_unique
    1                   ID   integer 2240       0             0.0     2240
    2           Year_Birth   integer 2240       0             0.0       59
    3            Education character 2240       0             0.0        5
    4       Marital_Status character 2240       0             0.0        8
    5               Income   integer 2240      24             1.1     1975
    6              Kidhome   integer 2240       0             0.0        3
    7             Teenhome   integer 2240       0             0.0        3
    8          Dt_Customer character 2240       0             0.0      663
    9              Recency   integer 2240       0             0.0      100
    10            MntWines   integer 2240       0             0.0      776
    11           MntFruits   integer 2240       0             0.0      158
    12     MntMeatProducts   integer 2240       0             0.0      558
    13     MntFishProducts   integer 2240       0             0.0      182
    14    MntSweetProducts   integer 2240       0             0.0      177
    15        MntGoldProds   integer 2240       0             0.0      213
    16   NumDealsPurchases   integer 2240       0             0.0       15
    17     NumWebPurchases   integer 2240       0             0.0       15
    18 NumCatalogPurchases   integer 2240       0             0.0       14
    19   NumStorePurchases   integer 2240       0             0.0       14
    20   NumWebVisitsMonth   integer 2240       0             0.0       16
    21        AcceptedCmp3   integer 2240       0             0.0        2
    22        AcceptedCmp4   integer 2240       0             0.0        2
    23        AcceptedCmp5   integer 2240       0             0.0        2
    24        AcceptedCmp1   integer 2240       0             0.0        2
    25        AcceptedCmp2   integer 2240       0             0.0        2
    26            Complain   integer 2240       0             0.0        2
    27       Z_CostContact   integer 2240       0             0.0        1
    28           Z_Revenue   integer 2240       0             0.0        1
    29            Response   integer 2240       0             0.0        2

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

                    ID Year_Birth    Income Kidhome Teenhome Recency MntWines
    Min           0.00    1893.00   1730.00    0.00     0.00    0.00     0.00
    Q1         2814.75    1959.00  35303.00    0.00     0.00   24.00    24.00
    Mediana    5458.50    1970.00  51381.50    0.00     0.00   49.00   174.50
    Media      5588.35    1968.82  52247.25    0.44     0.51   49.01   305.09
    Q3         8421.75    1977.00  68522.00    1.00     1.00   74.00   505.00
    Max       11191.00    1996.00 666666.00    2.00     2.00   99.00  1493.00
    DevPad     3249.38      11.99  25173.08    0.54     0.54   28.95   337.33
    N_missing     0.00       0.00      0.00    0.00     0.00    0.00     0.00
              MntFruits MntMeatProducts MntFishProducts MntSweetProducts
    Min            0.00            0.00            0.00             0.00
    Q1             2.00           16.00            3.00             1.00
    Mediana        8.00           68.00           12.00             8.00
    Media         26.36          167.00           37.64            27.03
    Q3            33.00          232.25           50.00            33.00
    Max          199.00         1725.00          259.00           262.00
    DevPad        39.79          224.28           54.75            41.07
    N_missing      0.00            0.00            0.00             0.00
              MntGoldProds NumDealsPurchases NumWebPurchases NumCatalogPurchases
    Min               0.00              0.00            0.00                0.00
    Q1                9.00              1.00            2.00                0.00
    Mediana          24.50              2.00            4.00                2.00
    Media            43.97              2.32            4.09                2.67
    Q3               56.00              3.00            6.00                4.00
    Max             321.00             15.00           27.00               28.00
    DevPad           51.82              1.92            2.74                2.93
    N_missing         0.00              0.00            0.00                0.00
              NumStorePurchases NumWebVisitsMonth AcceptedCmp3 AcceptedCmp4
    Min                    0.00              0.00         0.00         0.00
    Q1                     3.00              3.00         0.00         0.00
    Mediana                5.00              6.00         0.00         0.00
    Media                  5.80              5.32         0.07         0.07
    Q3                     8.00              7.00         0.00         0.00
    Max                   13.00             20.00         1.00         1.00
    DevPad                 3.25              2.43         0.26         0.26
    N_missing              0.00              0.00         0.00         0.00
              AcceptedCmp5 AcceptedCmp1 AcceptedCmp2 Complain Response
    Min               0.00         0.00         0.00     0.00     0.00
    Q1                0.00         0.00         0.00     0.00     0.00
    Mediana           0.00         0.00         0.00     0.00     0.00
    Media             0.07         0.06         0.01     0.01     0.15
    Q3                0.00         0.00         0.00     0.00     0.00
    Max               1.00         1.00         1.00     1.00     1.00
    DevPad            0.26         0.24         0.12     0.10     0.36
    N_missing         0.00         0.00         0.00     0.00     0.00

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

<img src="Customer_Personality_Analysis__files/figure-gfm/unnamed-chunk-13-1.png" style="display: block; margin: auto;" />

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

<img src="Customer_Personality_Analysis__files/figure-gfm/unnamed-chunk-14-1.png" style="display: block; margin: auto;" />

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

       Idade  n
    1     46 89
    2     51 86
    3     47 83
    4     50 78
    5     44 76
    6     52 75
    7     57 74
    8     49 72
    9     53 70
    10    48 69

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

<img src="Customer_Personality_Analysis__files/figure-gfm/unnamed-chunk-18-1.png" style="display: block; margin: auto;" />

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

<img src="Customer_Personality_Analysis__files/figure-gfm/unnamed-chunk-21-1.png" style="display: block; margin: auto;" />

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

<img src="Customer_Personality_Analysis__files/figure-gfm/unnamed-chunk-22-1.png" style="display: block; margin: auto;" />

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

<img src="Customer_Personality_Analysis__files/figure-gfm/unnamed-chunk-24-1.png" style="display: block; margin: auto;" />

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

<img src="Customer_Personality_Analysis__files/figure-gfm/unnamed-chunk-26-1.png" style="display: block; margin: auto;" />

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

<img src="Customer_Personality_Analysis__files/figure-gfm/unnamed-chunk-29-1.png" style="display: block; margin: auto;" />

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
       2848    3028    3204    3202    3377    3547 

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

<img src="Customer_Personality_Analysis__files/figure-gfm/unnamed-chunk-35-1.png" style="display: block; margin: auto;" />

``` r
head(dados_1 %>% arrange(desc(Gasto_total)) %>%
  select("Marital_Status","Education","Idade","Income","Gasto_total"),10)
```

       Marital_Status    Education Idade Income Gasto_total
    1           Alone Postgraduate    31  90638        2525
    2           Alone Postgraduate    31  90638        2525
    3       In couple Postgraduate    34  87679        2524
    4       In couple Postgraduate    53  75759        2486
    5       In couple Postgraduate    73  69098        2440
    6       In couple Postgraduate    66  90226        2352
    7           Alone Postgraduate    52  93790        2349
    8       In couple Postgraduate    50  83151        2346
    9       In couple Postgraduate    69  94384        2302
    10      In couple Postgraduate    69  94384        2302

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

<img src="Customer_Personality_Analysis__files/figure-gfm/unnamed-chunk-37-1.png" style="display: block; margin: auto;" />

``` r
# Quantidade de compra realizada com desconto
dados_1 %>% count(NumDealsPurchases)
```

       NumDealsPurchases   n
    1                  0  44
    2                  1 957
    3                  2 493
    4                  3 293
    5                  4 187
    6                  5  94
    7                  6  60
    8                  7  39
    9                  8  14
    10                 9   8
    11                10   5
    12                11   5
    13                12   3
    14                13   3
    15                15   7

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

<img src="Customer_Personality_Analysis__files/figure-gfm/unnamed-chunk-40-1.png" style="display: block; margin: auto;" />

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

<img src="Customer_Personality_Analysis__files/figure-gfm/unnamed-chunk-41-1.png" style="display: block; margin: auto;" />

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

<img src="Customer_Personality_Analysis__files/figure-gfm/unnamed-chunk-45-1.png" style="display: block; margin: auto;" />

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

<img src="Customer_Personality_Analysis__files/figure-gfm/unnamed-chunk-47-1.png" style="display: block; margin: auto;" />

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

<img src="Customer_Personality_Analysis__files/figure-gfm/unnamed-chunk-49-1.png" style="display: block; margin: auto;" />

## 3.16 Prosseguir apenas com as colunas que seja de interesse para as análies

``` r
dados_2 <- dados_1 %>% select(-c("ID","Kidhome","Teenhome","MntWines","MntFruits",                                                          "MntMeatProducts","MntFishProducts","MntSweetProducts","MntGoldProds",
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

<img src="Customer_Personality_Analysis__files/figure-gfm/unnamed-chunk-52-1.png" style="display: block; margin: auto;" />

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

<img src="Customer_Personality_Analysis__files/figure-gfm/unnamed-chunk-53-1.png" style="display: block; margin: auto;" />

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

<img src="Customer_Personality_Analysis__files/figure-gfm/unnamed-chunk-54-1.png" style="display: block; margin: auto;" />

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

<img src="Customer_Personality_Analysis__files/figure-gfm/unnamed-chunk-55-1.png" style="display: block; margin: auto;" />

## 4.2 Gráfico de dispersão

``` r
df_eda_1 %>% group_by(Education) %>% count()
```

    # A tibble: 2 x 2
    # Groups:   Education [2]
      Education         n
      <chr>         <int>
    1 Postgraduate   1954
    2 Undergraduate   252

``` r
df_eda_1 %>% group_by(Marital_Status) %>% count()
```

    # A tibble: 2 x 2
    # Groups:   Marital_Status [2]
      Marital_Status     n
      <chr>          <int>
    1 Alone            780
    2 In couple       1426

``` r
df_eda_1 %>% group_by(Has_Children) %>% count()
```

    # A tibble: 2 x 2
    # Groups:   Has_Children [2]
      Has_Children     n
      <chr>        <int>
    1 Has child     1578
    2 No child       628

``` r
df_eda_1 %>% group_by(Children) %>% count()
```

    # A tibble: 4 x 2
    # Groups:   Children [4]
      Children        n
      <chr>       <int>
    1 1 children   1113
    2 2 children    415
    3 3 children     50
    4 No children   628

### 4.2.1 Renda anual x Valor médio por compra

-   Disciminando por educacão

``` r
ggplot(data = df_eda_1) +
  geom_point(aes(x = Income, y = Valor_medio_de_compra, color = Education),size=1.8) +
  labs(x="Renda anual",y="Valor médio por compra") +
  theme_bw() +
  scale_colour_manual("Nível educacional", values = c("darkorchid","deepskyblue1"))
```

<img src="Customer_Personality_Analysis__files/figure-gfm/unnamed-chunk-57-1.png" style="display: block; margin: auto;" />

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

<img src="Customer_Personality_Analysis__files/figure-gfm/unnamed-chunk-58-1.png" style="display: block; margin: auto;" />

### 4.2.2 Renda anual x Gasto total

-   Disciminando por quantidade de filhos

``` r
ggplot(data = df_eda_1) +
  geom_point(aes(x = Income, y = Gasto_total, color = Children),size=1.8) +
  labs(x="Renda anual",y="Gasto total") +
  theme_bw() +
  scale_colour_manual("Nº de filhos", values = c("deepskyblue1","antiquewhite3","forestgreen","darkorchid"))
```

<img src="Customer_Personality_Analysis__files/figure-gfm/unnamed-chunk-59-1.png" style="display: block; margin: auto;" />

# 5 Correlação entre variáveis

``` r
xy <- df_eda_1 %>% select("Idade","N_Children","Income","Numero_compras","Gasto_total",
                         "Num_campaign_acc","Dt_inscricao_ate_atual","Valor_medio_de_compra")

correlacao <- cor(xy)
corrplot(correlacao, type = "upper", order = "hclust", 
         tl.col = "black", tl.srt = 45)
```

<img src="Customer_Personality_Analysis__files/figure-gfm/unnamed-chunk-60-1.png" style="display: block; margin: auto;" />

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

<img src="Customer_Personality_Analysis__files/figure-gfm/unnamed-chunk-62-1.png" style="display: block; margin: auto;" />

``` r
set.seed(3)
kmeans = kmeans(x = X1, centers = 2)
previsoes = kmeans$cluster

X1 <- as.data.frame(X1)

pairs(X1, col = c(1:4)[previsoes])
```

<img src="Customer_Personality_Analysis__files/figure-gfm/unnamed-chunk-63-1.png" style="display: block; margin: auto;" />

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

<img src="Customer_Personality_Analysis__files/figure-gfm/unnamed-chunk-64-1.png" style="display: block; margin: auto;" />

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

<img src="Customer_Personality_Analysis__files/figure-gfm/unnamed-chunk-66-1.png" style="display: block; margin: auto;" />

``` r
set.seed(3)
kmeans2 = kmeans(x = X2, centers = 3)
previsoes2 = kmeans2$cluster

X2 <- as.data.frame(X2)

pairs(X2, col = c(1:4)[previsoes2])
```

<img src="Customer_Personality_Analysis__files/figure-gfm/unnamed-chunk-67-1.png" style="display: block; margin: auto;" />

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

<img src="Customer_Personality_Analysis__files/figure-gfm/unnamed-chunk-68-1.png" style="display: block; margin: auto;" />

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

<img src="Customer_Personality_Analysis__files/figure-gfm/unnamed-chunk-70-1.png" style="display: block; margin: auto;" />

``` r
set.seed(3)
kmeans3 = kmeans(x = X3, centers = 3)
previsoes3 = kmeans3$cluster

X3 <- as.data.frame(X3)

pairs(X3, col = c(1:4)[previsoes3])
```

<img src="Customer_Personality_Analysis__files/figure-gfm/unnamed-chunk-71-1.png" style="display: block; margin: auto;" />

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

<img src="Customer_Personality_Analysis__files/figure-gfm/unnamed-chunk-72-1.png" style="display: block; margin: auto;" />
