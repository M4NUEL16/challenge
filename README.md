# challenge

saldo=0
limite=500
extrato=""
numero_saque=0
limite_saque=3

while True:
    menu= input("""
   [d] depositar
   [s] sacar       
   [e] extrato   
   [w] sair    
     
   =>""")
    
    if menu== "d": 
        valor= float(input("Inisra o seu valor de deposito: "))

        if valor>0:
            saldo += valor
            extrato += f"Deposito: {valor: .2f}$\n "
        else:
         print ("Falha na operacao, tente novamente.")

    elif menu== "s":
        valor= float(input("Insira o saque a deseijar: "))

        excendeu_saldo = valor > saldo
        excendeu_limite = valor> limite
        excendeu_saque = numero_saque> limite_saque

        if excendeu_saldo:
            print("Falha na operacao. Nao possui saldo suficiente.")

        elif excendeu_limite:
            print("Falha na operacao. O valor do saque excede o limite.")

        elif excendeu_saque:
            print("Falha na operacao. O limite de saque atingido. ")

        elif valor >0:
            saldo -= valor
            extrato += f"saque: {valor:.2f}$\n"
            numero_saque +=1 

        else:
         print ("Falha na operacao, tente novamente.")





    elif menu== "e":
        print(f"""
__________________Extrato_____________________     """)

        print("Nao teve qualquer alteracoes na sua conta." if not extrato else extrato)
      
        print(f"""
    Saldo: {saldo:.2f}                
______________________________________________              
              """)
        
        
    elif menu== "w":
        exit()
    
    else:
        print("Operacao invalida.")
