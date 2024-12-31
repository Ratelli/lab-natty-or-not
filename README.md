# Natural ou Fake Natty? Como Vencer na Era das IAs Generativas

## 🚀 Introdução

> Woooow! Look at this 👀

Olá pessoal, Venilton da DIO aqui! Inspirado na hype _"Natty or Not"_ do fisiculturismo, este Lab da DIO te convida a conhecer o mundo das IAs Generativas, explorando o potencial dessas tendências tecnológicas incríveis!

## 🎯 Bora Pro Desafio!? Você Já Venceu 💪🤓

### Objetivos

1. **Explorar IAs Generativas**: Utilize essas tecnologias para criar conteúdos que sejam o mais realista possível. Seja criativo! Você pode produzir imagens, textos, áudios, vídeos ou combinações de tudo isso!
1. **Potfólio de Projetos**:
    1. Faça o "fork" deste repositório, criando uma cópia em seu GitHub pessoal;
    2. Edite seu README com os detalhes do seu projeto, siga nosso [Template](#template) (é só copiar, colar e preencher);
    3. Submeta o link do seu repositório na plataforma da DIO. Pronto, você acabou de fortalecer seu portfólio de projetos nos perfis do GitHub e DIO 🚀
1. **Efeito de Rede**: Compartilhe seus resultados nas redes sociais com a hashtag **#LabDIONattyOrNot**. Não esqueça de nos marcar: [DIO](https://www.linkedin.com/school/dio-makethechange) e [falvojr](https://www.linkedin.com/in/falvojr).

### Template

```markd Cálculo de INSS e IR

## 📒 Descrição
Calculadora de desconto no INSS e IR com base no salário.

## 🤖 Tecnologias Utilizadas
ChatGPT

## 🧐 Processo de Criação
Solicitei que o ChatGPT criasse um programa em Python que pudesse calcular as alíquotas de INSS e IR. Ele criou com as alíquotas de 2023, continuei o chat perguntando quais eram as alíquotas de 2024, após ele me responder eu solicitei que ele atualizasse o código com as alíquotas de 2024. Após atualizado copiei o código e utilizei o PyCharm para testar se era funcional.

## 🚀 Resultados

def calcular_inss(salario_bruto):
    # Tabela de alíquotas de INSS (2024)
    faixas = [
        (1412.00, 0.075),  # Até R$ 1.412,00: 7,5%
        (2666.68, 0.09),   # De R$ 1.412,01 até R$ 2.666,68: 9%
        (4000.03, 0.12),   # De R$ 2.666,69 até R$ 4.000,03: 12%
        (7786.02, 0.14)    # De R$ 4.000,04 até R$ 7.786,02: 14%
    ]
    teto = 7786.02
    inss = 0
    salario_restante = salario_bruto

    for faixa, aliquota in faixas:
        if salario_restante > 0:
            base = min(salario_restante, faixa)
            inss += base * aliquota
            salario_restante -= base

    if salario_bruto > teto:
        inss = teto * 0.14  # Valor fixo para salários acima do teto

    return round(inss, 2)

def calcular_irrf(salario_bruto, inss):
    # Tabela de alíquotas do IRRF (2024)
    faixas_ir = [
        (2259.20, 0.0, 0.0),    # Até R$ 2.259,20: Isento
        (2826.65, 0.075, 169.44),
        (3751.05, 0.15, 381.44),
        (4664.68, 0.225, 662.77),
        (float("inf"), 0.275, 896.00)  # Acima de R$ 4.664,68
    ]

    base_ir = salario_bruto - inss
    irrf = 0

    for limite, aliquota, deducao in faixas_ir:
        if base_ir <= limite:
            irrf = base_ir * aliquota - deducao
            break

    return round(max(irrf, 0), 2)  # IRRF não pode ser negativo

def calcular_descontos(salario_bruto):
    inss = calcular_inss(salario_bruto)
    irrf = calcular_irrf(salario_bruto, inss)
    salario_liquido = salario_bruto - inss - irrf

    return {
        "Salário Bruto": salario_bruto,
        "INSS": inss,
        "IRRF": irrf,
        "Salário Líquido": salario_liquido
    }

# Exemplo de uso
salario = float(input("Digite o salário bruto: R$ "))
descontos = calcular_descontos(salario)

for key, value in descontos.items():
    print(f"{key}: R$ {value:.2f}")

## 💭 Reflexão (Opcional)
Para o cálculo bruto é funcional. Porém, há variáveis que não foram adicionadas nesse teste que pode resultar em um cálculo diferente do que é apresentado, como por exemplo dependentes de IR para já calcular o desconto em folha.

### Exemplos e Insigths

- [E-BOOK](/exemplos/E-BOOK.md)
- [Podcast](/exemplos/PODCAST.md)
- [Vídeo (Avatar Virtual)](/exemplos/VIDEO.md)

## Links Interessantes

[Base10: If You’re Not First, You’re Last: How AI Becomes Mission Critical](https://base10.vc/post/generative-ai-mission-critical/)

![Base10's Trend Map Generative AI](https://github.com/digitalinnovationone/lab-natty-or-not/assets/730492/f4df26e8-f8f7-4419-8252-c69d73ea930c)
