### Hi there 👋

**kynszz/Kynszz** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on python

computador = 0
usuario = 0
rodada = 0

def computador_escolhe_jogada(n, m):
    global computador
    n = n - m
    if (n == 1):
        print(" ")
        print("O computador tirou %s peça." % n)
        print("Agora restam %s peças no tabuleiro." % n)
        print(" ")
        if (n == 0):
            print ("Fim do jogo! O computador ganhou!")
            partida()
    else:
        print(" ")
        print("O computador tirou %s peça." % m)
        print("Agora restam %s peças no tabuleiro." % n)
        print(" ")
        if (n == 0):
            print ("Fim do jogo! O computador ganhou!")
            partida()
    return n
    return m


def usuario_escolhe_jogada(n, m):
    global usuario
    print(" ")
    n_user = int(input("Quantas peças você vai tirar? "))
    print("Voce tirou %s peças." % n_user)
    if (n_user <= m):
        n = n - m
        print(" ")
        print("Agora restam apenas %s peças no tabuleiro." % n)
    else:
        while (n_user > m):
            print("Oops! Jogada inválida! Tente de novo.")
            print(" ")
            n_user = int(input("Quantas peças você vai tirar? "))
    if (n == 0):
        print ("Vitoria do usuario")
    return n_user
    return n
    return m

def partida():
    global computador
    global usuario
    global rodada
    while(rodada <= 3):
        rodada = rodada + 1
        if (rodada <= 3 ):
            print(" ")
            print("**** Rodada %s ****" % rodada)
            print(" ")
            n = int(input("Quantas peças? "))
            m = int(input("Limite de peças por jogada? "))
            if (((n )%(m + 1)) == 0):
                while (n > 0):
                    print(" ")
                    print("Voce começa!")
                    usuario_escolhe_jogada(n,m)
                    if n > 0:
                        n = n - m    
                    computador_escolhe_jogada(n,m)
                    n = n - m
                    computador = computador + 1
            else:
                print(" ")
                print("Computador Começa!!")
                while( n > 0):
                    computador_escolhe_jogada(n,m)
                    computador = computador + 1
                    n = n - m
                    if n > 0:
                        usuario_escolhe_jogada(n,m)
                        n = n - m
        else:
            print("**** Final do campeonato! ****")
            print(" ")
            print("Fim de Campeonato: Computador %s x 0 Usuario " % computador)
        break

print("Bem-vindo ao jogo do NIM! Escolha:")
print(" ")
print("1 - para jogar uma partida isolada ")
tipo_jogo = int(input("2 - para jogar um campeonato "))
print(" ")
if ( tipo_jogo == 1 ):
    print("Voce escolheu partida isolada!")
if ( tipo_jogo == 2):
    print("Voce escolheu um campeonato!")
    partida()
else:
    pass
