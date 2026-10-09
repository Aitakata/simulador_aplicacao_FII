# Simulador de Investimentos em FIIs

## 📖 Sobre o Projeto

Este projeto foi desenvolvido como parte do desafio da DIO com o objetivo de criar uma ferramenta em Excel para simulação de investimentos em Fundos de Investimento Imobiliário (FIIs).

A planilha permite projetar a evolução do patrimônio ao longo do tempo com base em aportes mensais, taxa de rendimento e perfil de investidor, além de calcular os dividendos mensais estimados e sugerir a distribuição do capital entre diferentes tipos de FIIs.

---

## 🎯 Perguntas de Negócio Respondidas

A ferramenta foi desenvolvida para responder às seguintes perguntas:

### 1. Quanto investir por mês?
O usuário informa o valor do aporte mensal que deseja realizar.

### 2. Por quantos anos investir?
O usuário define o prazo do investimento em anos.

### 3. Qual a taxa de rendimento mensal?
A taxa mensal esperada é informada pelo usuário para realizar as projeções.

### 4. Qual será o patrimônio acumulado?
A planilha calcula automaticamente o patrimônio futuro utilizando a função `VF()` do Excel.

### 5. Qual será o valor dos dividendos mensais?
Com base no patrimônio acumulado e na taxa de rendimento informada, a ferramenta estima o valor dos dividendos mensais.

---

## 🧮 Como os Cálculos foram Implementados

### Função VF (Valor Futuro)

A função `VF()` foi utilizada para calcular o patrimônio acumulado ao longo do período de investimento.

Exemplo da estrutura utilizada:

```excel
=VF(taxa_mensal; prazo*12; -aporte; 0; 0)
```

Onde:

- `taxa_mensal` = rendimento mensal esperado;
- `prazo*12` = total de meses investidos;
- `aporte` = valor investido mensalmente;
- `0` = valor inicial do investimento;
- `0` = aportes realizados no final de cada período.

O resultado representa o valor acumulado ao final do prazo informado.

### Dividendos Mensais

Os dividendos estimados são calculados por:

```excel
Patrimônio Acumulado × Taxa Mensal
```

---

## 📊 Projeção de Cenários

Além da simulação principal, a ferramenta gera projeções para diferentes horizontes de investimento:

- 2 anos
- 5 anos
- 10 anos
- 20 anos
- 30 anos

Para cada cenário são apresentados:

- Patrimônio acumulado
- Dividendos mensais estimados

---

## 🏷️ Intervalos Nomeados Utilizados

Para tornar as fórmulas mais organizadas e fáceis de manter, foram utilizados intervalos nomeados para os principais parâmetros da simulação, tais como:

- `aporte`
- `taxa_mensal`
- `prazo`
- `salario`

O uso de nomes reduz a complexidade das fórmulas e melhora a legibilidade da planilha.

---

## 👤 Perfis de Investidor

A ferramenta possui três perfis de investidor:

### Conservador

| Tipo de FII | Percentual |
|------------|------------|
| Papel | 30% |
| Tijolo | 50% |
| Híbridos | 10% |
| FOFs | 10% |
| Desenvolvimento | 0% |
| Hotelaria | 0% |

### Moderado

| Tipo de FII | Percentual |
|------------|------------|
| Papel | 32% |
| Tijolo | 35% |
| Híbridos | 8% |
| FOFs | 5% |
| Desenvolvimento | 10% |
| Hotelaria | 10% |

### Agressivo

| Tipo de FII | Percentual |
|------------|------------|
| Papel | 50% |
| Tijolo | 10% |
| Híbridos | 5% |
| FOFs | 5% |
| Desenvolvimento | 20% |
| Hotelaria | 10% |

Todos os perfis totalizam 100% da carteira.

---

## 🔍 Uso de Chave Composta e PROCV

Para localizar automaticamente o percentual correspondente a cada tipo de fundo dentro do perfil selecionado, foi utilizada uma chave composta.

Exemplo:

```text
Agressivo-Papel
Moderado-Tijolo
Conservador-FOFs
```

A chave composta combina:

```text
Perfil + Tipo de FII
```

Dessa forma, a função `PROCV()` consegue localizar corretamente o percentual na tabela de apoio.

---

## 💰 Sugestão Automática de Investimento

A planilha também calcula uma sugestão de investimento baseada em 30% do salário informado pelo usuário.

Exemplo:

```text
Salário: R$ 2.000,00
Sugestão de investimento: R$ 600,00
```

---

## 📸 Evidências

### Tela Principal

<img width="605" height="672" alt="image" src="https://github.com/user-attachments/assets/c057d590-203d-43ad-ae9b-acc97ad6336d" />


### Perfil Conservador

<img width="606" height="587" alt="image" src="https://github.com/user-attachments/assets/2aee45aa-cb00-4ddf-9292-1ab05d4c6617" />


### Perfil Moderado

<img width="607" height="582" alt="image" src="https://github.com/user-attachments/assets/3ed365b3-503b-4ada-9a9c-1f366d151a2b" />

Perfil Agressivo

<img width="607" height="586" alt="image" src="https://github.com/user-attachments/assets/500574c9-6f7c-4a2b-b922-e7938f521f69" />


---

## 🚀 Tecnologias e Recursos Utilizados

- Microsoft Excel
- Função VF()
- PROCV()
- Validação de Dados
- Intervalos Nomeados
- Formatação Condicional
- Tabelas de Apoio
- Chave Composta
