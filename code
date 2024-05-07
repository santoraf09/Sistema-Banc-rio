import os

def menu():
    return """
    [d] Depositar
    [s] Sacar
    [e] Extrato
    [q] Sair
    => """

def depositar(saldo):
    valor = float(input("Informe o valor do depósito: "))
    if valor > 0:
        saldo += valor
        print(f"Depósito de R$ {valor:.2f} realizado com sucesso.")
        return saldo
    else:
        print("Operação falhou! O valor informado é inválido.")
        return saldo

def sacar(saldo, limite, numero_saques, LIMITE_SAQUES):
    valor = float(input("Informe o valor do saque: "))

    excedeu_saldo = valor > saldo
    excedeu_limite = valor > limite
    excedeu_saques = numero_saques >= LIMITE_SAQUES

    if excedeu_saldo:
        print("Operação falhou! Você não tem saldo suficiente.")
    elif excedeu_limite:
        print("Operação falhou! O valor do saque excede o limite.")
    elif excedeu_saques:
        print("Operação falhou! Número máximo de saques excedido.")
    elif valor > 0:
        saldo -= valor
        numero_saques += 1
        print(f"Saque de R$ {valor:.2f} realizado com sucesso.")
    else:
        print("Operação falhou! O valor informado é inválido.")

    return saldo, numero_saques

def extrato(saldo, extrato):
    print("\n================ EXTRATO ================")
    if extrato:
        print(extrato)
    else:
        print("Não foram realizadas movimentações.")
    print(f"\nSaldo: R$ {saldo:.2f}")
    print("==========================================")


def salvar_dados(saldo, extrato):
    with open("dados.txt", "w") as arquivo:
        arquivo.write(f"{saldo}\n")
        arquivo.write(extrato)


def carregar_dados():
    if os.path.exists("dados.txt"):
        with open("dados.txt", "r") as arquivo:
            linhas = arquivo.readlines()
            saldo = float(linhas[0])
            extrato = "".join(linhas[1:])
        return saldo, extrato
    else:
        return 0, ""


def main():
    saldo, extrato = carregar_dados()
    limite = 500
    numero_saques = extrato.count("Saque")
    LIMITE_SAQUES = 3

    while True:
        opcao = input(menu())

        if opcao == "d":
            saldo = depositar(saldo)
            extrato += f"Depósito: R$ {saldo:.2f}\n"

        elif opcao == "s":
            saldo, numero_saques = sacar(saldo, limite, numero_saques, LIMITE_SAQUES)
            extrato += f"Saque: R$ {saldo:.2f}\n"

        elif opcao == "e":
            extrato(saldo, extrato)

        elif opcao == "q":
            salvar_dados(saldo, extrato)
            print("Obrigado por utilizar nosso caixa eletrônico. Até mais!")
            break

        else:
            print("Operação inválida, por favor selecione novamente a operação desejada.")


if __name__ == "__main__":
    main()
