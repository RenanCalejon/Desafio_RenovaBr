# Desafio_RenovaBr
### Desafio focado nas bases de dados referentes às eleições de 2020, com ênfase na análise do estado de São Paulo e seus municípios.

+ Para essa análise do perfil do eleitorado e dos candidatos eu escolhi a utilização do Excel e Python.

+ Os arquivos perfil_eleitorado_2020.ipynb e resultado_candidatos.ipynb contém tratamento dos dados com utilização de Python.

### ⬇️ Abaixo segue o tratamento dos dados e as consultas pedidas em Excel 

⚠️ Analisando os arquivos em questão percebe-se que ambos ultrapassam o limite 1.048.576 linhas por planilha na qual o Excel consegue suportar, a solução para isso foi a utilização do Power Query do Excel que é um mecanismo de transformação e preparação de dados executado em nuvem, após os dados devidamente tratados dentro do Power Query foi feita a junção dos arquivos para conseguir concluir as consultas requisitadas.

## 1 -Tratamento de dados: 

 ### 📁 Arquivo perfil_eleitorado_2020 :
    
+ ❌ Colunas removidas : DT_GERACAO , HH_GERACAO , CD_MUNICIPIO , CD_MUN_SIT , CD_MN_SIT_BIOMETRIA , DS_MUN_SIT_BIOMETRIA , NR_ZONA , CD_GENERO , CD_ESTADO_CIVIL ,CD_FAIXA_ETARIA , CD_GRAU_ESCOLARIDADE , QT_ELEITORES_PERFIL , QT_ELEITORES_BIOMETRIA , QT_ELEITORES_DEFICIENCIA , QT_ELEITORES_INC_NM_SOCIAL .
    
+ ✅ Colunas aderidas : ANO_ELEICAO , SG_UF , NM_MUNICIPIO , DS_GENERO , DS_ESTADO_CIVIL , DS_FAIXA_ETARIA , DS_GRAU_ESCOLARIDADE.

+ Ultizando o filtro do Excel constantei que não foi necessario a remoção de registros brancos de nulos no arquivo perfil_eleitorado_2020 , provavelmente se          trantando de dataset importante do TSE ele já foi verificado.
    
+ Processo de filtragem no excel : Apenas o estado de São Paulo era necessário para a análise então foi feito um filtro SG_UF e feita a remoção dos outros estados.
 
 ### 📁 Arquivo SP_turno_1 :
    
+ ❌ Colunas removidas : foram removidas 39 colunas desncessárias para a intuito dessa análise.
    
+ ✅ Colunas aderidas : DS CARGO_PERGUNTA , NR_PARTIDO , SG_PARTIDO , NM_PARTIDO , NM_VOTAVEL , QT_VOTOS .

+ Utilizando o filtro do Excel verifiquei que em NR_PATIDO contia campos numéricos -1 e SG_PARTIDO contia campos #NULOS, mas era algo que já tinha sido       constatado com a disponibilização do PDF leiame do TSE, então com a utilização do filtro do Excel eu removi essas inconsistências para não deteriorar a análise.

## 2 - Consultas realizadas 🔍:

+ O ex-prefeito Bruno Covas foi o candidato escolhido
 
### 📈 Em qual município o candidato X foi mais votado:

+ Foi necessário primeiramente criar uma nova coluna (NR_VOTOS) para calcular os votos dos candidato em cada município foi utilizada essa formula para isso : CONT.SE(B2:B13;"BRUNO COVAS") 
 
+ No qual essa nova coluna mostra o número de votos para "BRUNO COVAS" no município da primeira célula .

+ Depois foi necessário criar outra coluna(QT_VOTOS_MUNICIPIO) para encontrar onde o "BRUNO COVAS" teve o maior número de votos, foi utilizada essa formula para isso : ÍNDICE(A3:A15;CORRESP(MÁXIMO(C3:C15);C3:C15;0))

+ Essa fórmula encontra o máximo de votos na NR_VOTOS e em seguida, usa a função ÍNDICE para retornar o município correspondente da coluna de municípios , que no caso de Bruno Covas retornou SP.

### 📈 Qual candidato foi mais votado em cada município:

+ No caso com a formula  ultizada ÍNDICE(A3:A15;CORRESP(MÁXIMO(C3:C15);C3:C15;0)) na coluna QT_VOTOS_MUNICIPIO arrastando para baixo ela já retorna o municipio em que o candidatos tiveram mais votos .

### 📊 Perfil do eleitorado.
+ Para a análise do eleitorado foi ultizado tabelas dinamicas e convertidas para gráficos : 

![Captura de tela 2023-08-22 180434](https://github.com/RenanCalejon/Desafio_RenovaBr/assets/101199913/e432e3f4-0204-49b2-bb00-fa0cc037be3b)

	








   

