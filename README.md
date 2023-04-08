# Desafio-Sistema-Bancario-Dio

saldo = 0
saque_max = 500
extrato = ""
LIMITE_SAQUE = 3

while True:

    operacao = int(input(
'''
Selecione a Operação

[01] Saque
[02] Depósito
[03] Saldo
[04] Extrato
[05] Sair
'''
))
    
    if operacao == 1:
        saque = float(input('Informe o valor do Saque: '))

        if saque <= 0:
            print('\nValor Inválido!') 
                        
        elif LIMITE_SAQUE <= 0:
            print('\nLimite de saque excedido!')
         
        elif saque <= saque_max and saque < saldo:
            LIMITE_SAQUE -= 1
            saldo -= saque           
            extrato += f'Saque:         R$ {saque:.2f}\n'
        
        elif saque > saldo:
            print('\nSaldo Insuficiente!')
        
        elif saque > saque_max:
            print('\nEsse valor excede o valor máximo permitido!')
                        
        
        
            

    elif operacao == 2:
        deposito = float(input('Informe o valor do Depósito: '))

        if deposito > 0:
            saldo += deposito
            extrato += f'Depósito:      R$ {deposito:.2f}\n'
        
        else:
            print('Operação Inválida!')

    

    elif operacao == 3:
        print(f'Valor do seu saldo é {saldo}\n')



    elif operacao == 4:
        print('========== Extrato ==========\n')
        print('Não foram Realizadas Movimentações' if not extrato else extrato )
        print(f'Seu Saldo é    R${saldo:.2f} \n')
        print('=============================')


    elif operacao == 5:
        print('Obrigado volte sempre')
        break


    else:
        print('Nenhuma Operação Selecionada!')
