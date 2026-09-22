#!/usr/bin/env python3

def somar(a, b):
    return a + b

def subtrair(a, b):
    return a - b

def multiplicar(a, b):
    return a * b

def dividir(a, b):
    if b == 0:
        return "Erro: Divisão por zero não é permitida!"
    return a / b

def exibir_menu():
    print("\n=== CALCULADORA SIMPLES ===")
    print("1. Soma (+)")
    print("2. Subtração (-)")
    print("3. Multiplicação (*)")
    print("4. Divisão (/)")
    print("5. Sair")

def executar_calculadora():
    while True:
        exibir_menu()
        opcao = input("\nEscolha uma opção (1-5): ").strip()

        if opcao == '5':
            print("Encerrando a calculadora. Até logo!")
            break

        if opcao in ('1', '2', '3', '4'):
            try:
                num1 = float(input("Digite o primeiro número: "))
                num2 = float(input("Digite o segundo número: "))
            except ValueError:
                print("Erro: Por favor, digite apenas números válidos.")
                continue

            if opcao == '1':
                print(f"Resultado: {num1} + {num2} = {somar(num1, num2)}")
            elif opcao == '2':
                print(f"Resultado: {num1} - {num2} = {subtrair(num1, num2)}")
            elif opcao == '3':
                print(f"Resultado: {num1} * {num2} = {multiplicar(num1, num2)}")
            elif opcao == '4':
                resultado = dividir(num1, num2)
                if isinstance(resultado, str):
                    print(resultado)
                else:
                    print(f"Resultado: {num1} / {num2} = {resultado}")
        else:
            print("Opção inválida! Escolha um número de 1 a 5.")

if __name__ == "__main__":
    executar_calculadora()

