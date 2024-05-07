
 <h1 align="center">:dart:Sistema básico de caixa eletrônico</h1>
</p>

Este código é um exemplo de um sistema básico de caixa eletrônico implementado em Python. Vamos entender como ele funciona:

<sub> <strong>Segue nas redes sociais para acompanhar mais conteúdo: </strong> <br>

[<img src = "https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white">](https://github.com/santoraf09)
[<img src="https://img.shields.io/badge/linkedin-%230077B5.svg?&style=for-the-badge&logo=linkedin&logoColor=white" />](https://www.linkedin.com/in/rafael-santiago11/)

# Definição do menu e variáveis iniciais: 

O código começa definindo o menu do caixa eletrônico em uma string de várias linhas chamada menu. Em seguida, são definidas algumas variáveis iniciais importantes: saldo (o saldo inicial da conta), limite (o limite máximo de saque por transação), extrato (uma string que irá registrar todas as transações realizadas pelo usuário), numero_saques (um contador que registrará o número de saques realizados) e LIMITE_SAQUES (o número máximo de saques permitidos).

## Loop principal: 

O código entra em um loop while True, que significa que continuará executando indefinidamente, a menos que a instrução break seja encontrada.

## Leitura da opção do usuário: 

Dentro do loop, o código solicita ao usuário que insira uma opção do menu (depósito, saque, extrato ou sair) e armazena essa opção na variável opção.

## Execução da operação escolhida pelo usuário: 

O código verifica qual opção foi selecionada pelo usuário e executa o bloco correspondente de código. 

Por exemplo:
Se o usuário escolheu depósito (d), o código solicita ao usuário o valor do depósito, adiciona esse valor ao saldo, e registra a transação no extrato.
Se o usuário escolheu sacar (s), o código verifica várias condições (se o saldo é suficiente, se o valor do saque excede o limite ou o número máximo de saques permitidos) e, se todas as condições forem atendidas, deduz o valor do saque do saldo, registra a transação no extrato e atualiza o contador de saques.
Se o usuário escolheu extrato (e), o código exibe todas as transações registradas no extrato e o saldo atual da conta.
Se o usuário escolheu sair (q), o código interrompe o loop while usando a instrução break, encerrando assim a execução do programa.
Se o usuário inseriu uma opção inválida, o código imprime uma mensagem de erro e solicita que o usuário selecione novamente uma opção válida.

## Repetição do loop: 

Após executar a operação escolhida pelo usuário, o código volta ao início do loop while e solicita novamente uma opção ao usuário, continuando assim até que o usuário decida sair do programa.
