# Desafio - Desenvolvimento de Dashboard de E-commerce com Power BI Usando Fórmulas DAX

Este documento descreve os passos seguidos para concluir o desafio de modelar um dashboard de e-commerce no Power BI, utilizando fórmulas DAX.

## STAR SCHEMA no PoweR BI

As tabelas foram criadas de acordo com as orientações do arquivo fornecido pela professora.

![starchemaPowerBI](https://github.com/user-attachments/assets/f6278698-6e12-412b-9aeb-9553903b16e6)


### Estrutura das Tabelas

1. **Tabela Fato - F_Vendas**  
   **Campos:** `SK_ID`, `ID_Produto`, `Produto`, `Units Sold`, `Sales Price`, `Discount Band`, `Segment`, `Country`, `Salers`, `Profit`, `Date`.

2. **Tabela Dimensão - D_Produtos**  
   **Campos:** `ID_Produto`, `Produto`, `Média de Unidades Vendidas`, `Média do Valor de Vendas`, `Mediana do Valor de Vendas`, `Valor Máximo de Venda`, `Valor Mínimo de Venda`.

   **Nota:** As colunas "Média de Unidades Vendidas" e "Média do Valor de Vendas" foram configuradas com tipo decimal fixo.

3. **Tabela Dimensão - D_Descontos**  
   **Campos:** `ID_Produto`, `Discount`, `Discount Band`.

4. **Tabela Dimensão - D_Produtos_Detalhes**  
   **Campos:** `ID_Produtos`, `Discount Band`, `Sale Price`, `Units Sold`, `Manufacturing Price`.

5. **Tabela Dimensão - D_Data**  
   Criada por meio de DAX com a função `CALENDARAUTO()`, conforme o desafio.

### Fórmulas DAX para a Tabela D_Data

A tabela `D_Data` foi gerada com as seguintes fórmulas DAX:

```dax
Tabela D_Data = CALENDARAUTO(12)
Year = YEAR('D_Data'[Date])
Month Number = MONTH('D_Data'[Date])
Week Number = WEEKNUM('D_Data'[Date])
Weeks Day = FORMAT('D_Data'[Date], "DDDD")
Day of the Week = WEEKDAY('D_Data'[Date])
