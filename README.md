

import random

def verificacao(matriz):
    linhas = len(matriz)
    colunas = len(matriz[0])

    for i in range(linhas):
        for j in range(colunas):
            if i == j:
                if matriz[i][j] != 1:
                    return False
                
            else:
                if matriz[i][j] != 0:
                    return False
            
    return True    


linhas = int(input('Digite a quantidade de linhas da sua matriz: '))
colunas = int(input('Digite a quantidade de colunas da sua matriz: '))

contador = 0

while True:
    contador += 1

    matriz = []
    for i in range(linhas):
        linha = []
        for j in range(colunas):
            valor = int(random.randint(0, 1))
            linha.append(valor)
        matriz.append(linha)

    print('\nMatriz:')
    print()
    for linha in matriz:
        print(linha)

    resultado = verificacao(matriz)

    if resultado == True:
        print('\nMatriz Identidade Encontrada!')
        break

    print(resultado)
    print(f'\nTentativas: {contador}')
