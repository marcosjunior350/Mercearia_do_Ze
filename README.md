# Mercearia do Zé
## Formulário com Macros para registro de vendas
A ideia desse formulário é somente explorar outros controles que não foram utilizados no projeto anterior. Além do formulário, temos uma base de dados na qual os produtos e os clientes fictícios da mercearia estão registrados e também uma guia de cadastro 
para registrar as compras feitas.

[![Veja o projeto em ação](https://youtube.com)](https://www.youtube.com/watch?v=KdFxoOXPlD4&list=PLKefA-6NcYLTm-bl23V8PNm9o8Vh3d4GA&index=5)

### Observações importantes

Antes de falarmos das fórmulas e dos controles que foram usados, é importante comentar como os cálculos foram feitos.  

1. Pagamento à vista: nessa modalidade, o formulário vai somar todos os valores que estão inseridos em "Produto 1", "Produto 2" e "Produto 3". Naturalmente, esse será o valor final e nenhum dado inserido em outras células pode mudar isso.
   
2. Pagamento a prazo: o valor final vai depender de alguns critérios.
* Juros - Os juros variam conforme a quantidade de parcelas escolhidas. De 2 a 4 parcelas, temos juros de 1%. De 5 a 6, os juros são de 2%. Acima de 6, temos 3% de juros. Lembrando que o limite é de 10 parcelas.
* Entrada - Se o usuário der alguma entrada, esse valor é abatido do total final. Ou seja, o formulário vai calcular o total da compra com os juros e subtrair o valor da entrada.
* Saldo - O valor total menos o valor da entrada.
* Parcela s/ Juros - Saldo dividido pela quantidade de parcelas. O valor vai nos permitir calcular o total final da parcela no campo "Parcela + Juros".

Após passar por todos esses critérios, teremos o valor final de um pagamento a prazo.

### Explicando algumas fórmulas

Nos campos "Produto 1", "Produto 2" e "Produto 3", foram usadas 3 fórmulas diferentes. Nos dois primeiros campos, eu poderia ter usado a mesma fórmula, mas preferi variar por questões didáticas. Cada botão de opção selecionado vai gerar um número. Na terceira categoria, em que temos as caixas de seleção, cada uma delas vai gerar um valor lógico (Verdadeiro ou Falso). É possível visualizar esses valores na guia "Base de dados". Dito isso, vamos para as fórmulas:

* Produto 1 - Com base na primeira categoria, temos um SES que vai validar se o produto selecionado é o 1, 2 ou 3. Com isso, ele multiplica o valor do produto pela quantidade selecionada.
* Produto 2 - A partir da segunda categoria, temos um ÍNDICE que vai verificar qual é o produto que está selecionado. No final, ela também vai multiplicar o valor pela quantidade selecionada. É importante lembrar que só foi possível usar o ÍNDICE aqui porque os produtos listados estão em ordem. Caso contrário, não seria possível usar essa função.
* Produto 3 - Por fim, temos um SOMASE básico que vai calcular o preço de todos os produtos que estiverem marcados como "VERDADEIRO" na base de dados (categoria 3). Assim como os demais, o valor é multiplicado pela quantidade selecionada.

Os controles de seleção "À Vista" e "Prazo" também geram um número na base de dados. Se a opção "À Vista" for selecionada, teremos o número 1. Se a opção "Prazo" for selecionada, teremos o número 2. Dessa forma, é possível realizar os cálculos mencionados no início.

### Macros

Para este formulário, temos duas macros. 

1. A primeira macro já está vinculada ao controle de seleção "À Vista". Ao selecionar essa opção, a Macro apaga automaticamente qualquer valor que esteja inserido na entrada e no campo de parcelas.
2. Por fim, a segunda macro está vinculada ao botão "CADASTRAR". Ela basicamente vai pegar todos os valores do formulário, inseri-los na guia de cadastro e apagar os valores nos campos de controle na guia "Base de dados". Dessa forma, o formulário fica limpo para uma nova seleção.

Eu só esqueci de apagar o nome do cliente na gravação da última Macro, foi mal. 😂   

## ✒️ Autor

Desenvolvido por **Marcos Junior**.

* [LinkedIn](https://www.linkedin.com/in/marcosjunior007/)
* [E-mail](mailto:marcosroberto.s.junior02@gmail.com)



