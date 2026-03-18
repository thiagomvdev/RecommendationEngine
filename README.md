# RecommendationEngine
Esse projeto é parte do curso introdutório às Ciências da Computação, da Khan Academy.
Visa concretizar 4 requisitos:

1) Escolha de pelo menos 5 itens para recomendação dentro de uma categoria.
2) Criar uma variável para cada um dos itens.
3) Usar o input() para perguntar ao usuário três características ou preferências.
4) Usar condicionais para selecionar dentro de uma das variáveis baseadas nas respostas do requisito 3.

O algoritmo deveria possuir pelo menos 2 variáveis compostas (compound conditionals), 
condicionais encadeadas (chained conditionals), ou condicionais aninhadas (nested conditionals).

________________________________________________________________________________________________

"""Recommends a Khan Academy course based on student preferences."""

# Course options (5 items)
grammar = "Grammar"
pixar = "Pixar in a Box"
fin_lit = "Financial Literacy"
algebra = "Algebra Basics"
coding = "Intro to Computer Programming"

# Collect user preferences (3 inputs)
grade = int(input("What grade are you in? "))
favorite_subject = input("What is your favorite subject? ")
learning_style = input("Do you prefer creative or analytical learning? ")

# Recommendation logic
rec = ""

if grade < 6:
    # Younger students
    if favorite_subject == "english":
        rec = grammar
    elif favorite_subject == "math":
        rec = algebra
    else:
        rec = pixar

elif grade <= 8:
    # Middle school students
    if favorite_subject == "computing" and learning_style == "analytical":
        rec = coding
    elif favorite_subject == "art" or learning_style == "creative":
        rec = pixar
    else:
        rec = grammar

else:
    # High school students
    if favorite_subject == "math" and learning_style == "analytical":
        rec = algebra
    elif favorite_subject == "economics":
        rec = fin_lit
    else:
        rec = coding

print("We recommend the Khan Academy course:", rec)


