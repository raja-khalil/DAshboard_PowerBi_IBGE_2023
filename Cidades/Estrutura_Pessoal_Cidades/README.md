# Dashboard de Estrutura Pessoal Cidades

Este dashboard foi criado para analisar a estrutura de pessoal das prefeituras das cidades brasileiras, utilizando dados do IBGE de 2023. O objetivo é fornecer insights detalhados e facilitar a tomada de decisões na gestão pública.

## Descrição

O dashboard apresenta uma análise detalhada da estrutura de recursos humanos das prefeituras, incluindo a proporção de servidores em relação à população total dos municípios. Os dados foram extraídos e tratados a partir do Censo do IBGE de 2023.

## Estrutura do Dashboard

### População do Município

1. **População Total**:
   - **População**: Número total de habitantes do município.

### Distribuição Percentual dos Servidores

2. **Servidores por Tipo**:
   - **Estatutários**: Funcionários efetivos, contratados por concurso público e com estabilidade.
   - **Celetistas**: Funcionários contratados pelo regime da Consolidação das Leis do Trabalho (CLT).
   - **Comissionados**: Funcionários ocupando cargos de confiança, geralmente sem concurso público.
   - **Estagiários**: Pessoas em período de estágio, geralmente estudantes, que trabalham temporariamente para ganhar experiência.
   - **Sem Vínculo Permanente**: Funcionários contratados temporariamente ou por prestação de serviços, sem vínculo empregatício estável.
   - **Total de Servidores**: Soma de todos os tipos de servidores mencionados acima.

### Servidores por 100 Mil Habitantes

3. **Proporção de Servidores**:
   - **Servidores a cada 100 mil habitantes**: Métrica que indica quantos servidores existem para cada 100 mil habitantes do município.

### Visualizações Gráficas

4. **Gráficos de Barras**:
   - Mostrando a distribuição de servidores por categorias (Estatutários, Comissionados, Sem Vínculo, Estagiários).

5. **Gráficos Comparativos**:
   - Destacando a diferença entre administração direta e indireta.

## Medidas Utilizadas

### Medidas Básicas

```DAX
Total_Estatutarios = SUM(FatoFuncionarios[Estatutários])
Total_Celetistas = SUM(FatoFuncionarios[Celetistas])
Total_Comissionados = SUM(FatoFuncionarios[Somente Comissionados])
Total_Estagiarios = SUM(FatoFuncionarios[Estagiários])
Total_SemVinculo = SUM(FatoFuncionarios[Sem Vínculo Permanente])
Total_Servidores = SUM(FatoFuncionarios[Total])
T_AD_Total_Servidores = SUM(FatoFuncionarios[T_AD_Total_Servidores])

Proporcao_Servidores_Habitantes = 
DIVIDE(
    SUM(FatoFuncionarios[Total_Servidores]), 
    SUM(DimCidades[População dos Municípios]), 
    0
)

Total_Adm_Indireta_Estatutarios = SUM(FatoFuncionarios[Estatutários2])
Total_Adm_Indireta_Celetistas = SUM(FatoFuncionarios[Celetistas3])
Total_Adm_Indireta_Comissionados = SUM(FatoFuncionarios[Somente comissionados4])
Total_Adm_Indireta_Estagiarios = SUM(FatoFuncionarios[Estagiários5])
Total_Adm_Indireta_SemVinculo = SUM(FatoFuncionarios[Sem vínculo permanente6])
Total_Adm_Indireta_Total_Servidores = SUM(FatoFuncionarios[Total7])

## Insights Possíveis

### Eficiência Operacional
A proporção de servidores por habitante pode indicar a eficiência na alocação de recursos humanos. Municípios com alta proporção podem indicar ineficiência ou necessidade de mais servidores.

### Perfil de Vínculo Empregatício
A distribuição dos servidores por tipo pode revelar a preferência por diferentes tipos de contratos (estatutários, comissionados, etc.), indicando políticas de contratação e desenvolvimento de talentos.

### Estrutura Administrativa
A comparação entre administração direta e indireta pode fornecer insights sobre a organização interna das prefeituras e sua eficiência.

### Desigualdades Regionais
Comparar a densidade de servidores por estado e região pode revelar desigualdades na alocação de recursos humanos. Estados ou regiões com menor densidade podem ser priorizados em políticas públicas.

### Dados Não Informados
Identificar municípios com alta incidência de dados não informados pode sugerir problemas na coleta de informações, destacando a necessidade de melhorias nos processos de coleta de dados.

## Dados Utilizados
Os dados utilizados são públicos e foram extraídos do Censo do IBGE de 2023, especificamente da área de Recursos Humanos.

## Objetivo
O objetivo deste dashboard é fornecer uma ferramenta visual e interativa para análise da estrutura de pessoal das prefeituras brasileiras, auxiliando na tomada de decisões e na transição administrativa.

## Tecnologias Utilizadas
- **Power BI**: Ferramenta de visualização de dados utilizada para criar o dashboard.
- **Excel**: Utilizado para tabulação e tratamento inicial dos dados.

## Como Acessar
O dashboard completo pode ser acessado através do link: [Link do Dashboard](https://app.powerbi.com/view?r=eyJrIjoiYTFmNzQ4ZTktOGIzZS00N2ExLWJjZWEtNGM4ODY2NGY1YzEwIiwidCI6Ijc5NGU3YjM0LWFjYTQtNDM5OS05OThjLWNhZmFlZjViZTMwYiJ9)
