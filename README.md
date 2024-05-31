ef escolha_servico():
  while True:
    servico = input("Escolha o serviço desejado (dig/ico/ipb/fot): ").lower()
    if servico == 'dig':
       return 1.10 # Custo por página para digitalização
    elif servico == 'ico':
       return 1.00 # Custo por página para impressão colorida
    elif servico == 'ipb':
       return 0.40 # Custo por página para impressão preto e branco
    elif servico == 'fot':
       return 0.20 # Custo por página para fotocópia
    else:
         print("Opção inválida. Por favor, escolha entre dig/ico/ipb/fot.") # EXIGÊNCIA DE SAÍDA DE CONSOLE 2 de 4

def num_pagina():
    while True:
       try:
           num_paginas = int(input("Digite o número de páginas: "))
           if num_paginas >= 20000:
              print("Número de páginas inválido. Máximo permitido é 19999.") # EXIGÊNCIA DE SAÍDA DE CONSOLE 3 de 4
           elif num_paginas < 0:
              print("Número de páginas inválido. Não pode ser negativo.")
           else:
                if num_paginas < 20:
                   return num_paginas
                elif 20 <= num_paginas < 200:
                   return num_paginas * 0.85 # Desconto de 15%
                elif 200 <= num_paginas < 2000:
                   return num_paginas * 0.80 # Desconto de 20%
                elif 2000 <= num_paginas < 20000:
                   return num_paginas * 0.75 # Desconto de 25%
    except ValueError:
          print("Valor não numérico. Por favor, digite um número válido.") # EXIGÊNCIA DE SAÍDA DE CONSOLE 3 de 4

def servico_extra():
    while True:
       try:
           extra = int(input("Escolha o serviço extra (1 - Encadernação simples, 2 - Capa dura, 0 - Nenhum): "))
           if extra == 1:
              return 15.00 # Custo da encadernação simples
           elif extra == 2:
              return 40.00 # Custo da encadernação de capa dura
           elif extra == 0:
              return 0.00 # Sem custo adicional
           else:
                print("Opção inválida. Por favor, escolha entre 1, 2 ou 0.")
     except ValueError:
         print("Valor não numérico. Por favor, digite um número válido.") # EXIGÊNCIA DE SAÍDA DE CONSOLE 3 de 4
         
# Mensagem de boas-vindas
print("Bem-vindo ao sistema de cobrança da copiadora da Maria!") # EXIGÊNCIA DE CÓDIGO 1 de 7

# Coletar dados do usuário
custo_por_pagina = escolha_servico() # EXIGÊNCIA DE CÓDIGO 2 de 7
num_paginas = num_pagina() # EXIGÊNCIA DE CÓDIGO 3 de 7
valor_extra = servico_extra() # EXIGÊNCIA DE CÓDIGO 4 de 7

# Calcular o total
total = (custo_por_pagina * num_paginas) + valor_extra # EXIGÊNCIA DE CÓDIGO 5 de 7

# Exibir resultado final
print(f"Pedido realizado com sucesso!")
print(f"Serviço escolhido: {custo_por_pagina:.2f} por página")
print(f"Número de páginas (com desconto se aplicável): {num_paginas:.2f}")
print(f"Custo adicional: {valor_extra:.2f}")
print(f"Total a pagar: {total:.2f} reais") # EXIGÊNCIA DE SAÍDA DE CONSOLE 4 de 4

# Exigências adicionais de código
# EXIGÊNCIA DE CÓDIGO 6 de 7 (try/except já implementados)
# EXIGÊNCIA DE CÓDIGO 7 de 7 (comentários relevantes no código)
