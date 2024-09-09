
def perguntar(perguntas_respostas):
    pontuacao = 0
    for pergunta, dados in perguntas_respostas.items():
        print("\n" + pergunta)
        alternativas = dados['alternativas']
        resposta_certa = dados['resposta']

        for alternativa, opcao in alternativas.items():
            print(f"{alternativa}. {opcao}")

        resposta_usuario = input("Escolha a alternativa (A, B, C, D): ").strip().upper()

        if resposta_usuario == resposta_certa:
            print("Correto!")
            pontuacao += 1
        else:
            print(f"Errado! A resposta correta é: {resposta_certa}")
    return pontuacao
1
def quiz_matematica():
    perguntas = [
        {"pergunta": "Quanto é 5 + 7?", "opcoes": ["10", "11", "12", "13"], "resposta": "12"},
        {"pergunta": "Quanto é 37 - 15?", "opcoes": ["18", "22", "24", "26"], "resposta": "22"},
        {"pergunta": "Quanto é 9 x 9?", "opcoes": ["72", "81", "90", "99"], "resposta": "81"},
        {"pergunta": "quanto é 49 : 7?", "opcoes": ["3", "11", "9", "7"], "resposta": "7"},                                    
    ]
    executar_quiz(perguntas)

def quiz_cultura_geral():
    perguntas = [
        {"pergunta": "Quem pintou a Mona Lisa?", "opcoes": ["Vincent van Gogh", "Pablo Picasso", "Leonardo da Vinci", "Michelangelo"], "resposta": "Leonardo da Vinci"},
        {"pergunta": "Em qual país fica a Torre Eiffel?", "opcoes": ["França", "Itália", "Espanha", "Alemanha"], "resposta": "França"},
        {"pergunta": "Qual é o menor país do mundo?", "opcoes": ["Mônaco", "Malta", "Vaticano", "Liechtenstein"], "resposta": "Vaticano"},
         {"pergunta": "qual artista é conhecido como rei do pop?", "opcoes": ["Michael Jackson", "Justin Bieber", "Roberto Carlos", "Luan Santana"], "resposta": "Michael Jackson"},
    ]
    executar_quiz(perguntas)

def quiz_ciencia():
    perguntas = [
        {"pergunta": "Qual é o planeta mais próximo do Sol?", "opcoes": ["Vênus", "Terra", "Marte", "Mercúrio"], "resposta": "Mercúrio"},
        {"pergunta": "O que é a fórmula H2O?", "opcoes": ["Oxigênio", "Água", "Hidrogênio", "Gelo"], "resposta": "Água"},
        {"pergunta": "Qual é o maior órgão do corpo humano?", "opcoes": ["Coração", "Cérebro", "Pele", "Pulmão"], "resposta": "Pele"},
        {"pergunta": "Qual o gás é essencial para respiração humana" , "opcoes": ["Nitrôgenio", "Oxigênio", "Carbono", "Hidrogênio"], "resposta": "Oxigênio"},
    ]
    executar_quiz(perguntas)

def executar_quiz(perguntas):
    pontuacao = 0
    for pergunta in perguntas:
        print(pergunta["pergunta"])
        for i, opcao in enumerate(pergunta["opcoes"], start=1):
            print(f"{i}. {opcao}")
        resposta_usuario = input("Escolha a resposta (digite o número): ")
        resposta_certa = pergunta["opcoes"].index(pergunta["resposta"]) + 1
        if int(resposta_usuario) == resposta_certa:
            print("Correto!\n")
            pontuacao += 1
        else:
            print(f"Incorreto! A resposta correta é: {pergunta['resposta']}\n")
    print(f"Sua pontuação final: {pontuacao}/{len(perguntas)}\n")

def menu():
    while True:
        print("Escolha um quiz:")
        print("1. Quiz de Matemática")
        print("2. Quiz de Cultura Geral")
        print("3. Quiz de Ciência")
        print("4. Sair")

        escolha = input("Digite o número da sua escolha: ")

        if escolha == "1":
            quiz_matematica()
        elif escolha == "2":
            quiz_cultura_geral()
        elif escolha == "3":
            quiz_ciencia()
        elif escolha == "4":
            print("Saindo do programa...")
            break
        else:
            print("Opção inválida! Tente novamente.\n")
        print== 1
        "4. Sair" # Função para calcular percentual de acertos e erros
def calcular_percentual(acertos, erros):
    total = acertos + erros
    if total == 0:
        return 0, 0
    percentual_acertos = (acertos / total) * 100
    percentual_erros = (erros / total) * 100
    return percentual_acertos, percentual_erros

# Exemplo de uso
acertos = int(input("Digite o número de acertos: "))
erros = int(input("Digite o número de erros: "))

percentual_acertos, percentual_erros = calcular_percentual(acertos, erros)

print(f"Percentual de acertos: {percentual_acertos:.2f}%")
print(f"Percentual de erros: {percentual_erros:.2f}%")


# Executa o menu principal
menu()
