# 🔍 Análise Exploratória: Porto Seguro Data Challenge

Análise completa de 59.381 clientes e 68 variáveis explicativas para prever compra de produtos.

---

## 📁 Arquivos na Pasta

Você tem **6 arquivos**:

```
📄 Analise_Exploratoria.html      (12 KB)  ← Relatório em HTML
📄 Analise_Exploratoria.pdf       (378 KB) ← Relatório em PDF
📊 train.csv                      (4.8 MB) ← Dados para modelagem
📋 metadata.csv                   (2 KB)   ← Descrição das variáveis
📊 test.csv                       (7.2 MB) ← Dados de teste (não usar)
📋 submission_sample.csv          (160 KB) ← Exemplo (não usar)
```

---

## 🎯 O Que Fazer

### 1. VER O RELATÓRIO

**Opção A: Abrir HTML (no navegador)**
```
Clique duplo em: Analise_Exploratoria.html
→ Abre no seu navegador
```

**Opção B: Abrir PDF (imprimível)**
```
Clique duplo em: Analise_Exploratoria.pdf
→ Abre no leitor de PDF
```

### 2. ENTENDER OS DADOS

**Arquivo: metadata.csv**
- Mostra o tipo de cada variável (nominal, ordinal, discreto, contínuo)

**Arquivo: train.csv**
- 59.381 linhas (clientes)
- 70 colunas:
  - Coluna 1: ID
  - Colunas 2-69: Variáveis (var1 a var68)
  - Coluna 70: Y (comprou ou não)

---

## 📊 O Que a Análise Mostra

✅ **Distribuição das variáveis**
- Quantitativas: histogramas e boxplots
- Qualitativas: frequências

✅ **Correlações**
- Entre variáveis quantitativas
- Com a variável resposta (Y)

✅ **Dados faltantes**
- Quais variáveis têm dados faltantes
- Quanto faltam

✅ **Recomendações**
- Quais variáveis remover
- Como preparar os dados
- Quais modelos usar

---

## 💡 Principais Descobertas

### Variáveis Importantes

| Achado | Ação |
|--------|------|
| var65, var66 têm 95% de dados faltantes | Remover |
| Maioria das variáveis < 10% faltantes | Imputar com KNN |
| Escalas muito diferentes entre variáveis | Normalizar |
| Baixa correlação geral | Usar Random Forest ou XGBoost |

### Recomendações para Modelagem

```
1. PREPARAR DADOS
   ├─ Remover var65 e var66
   ├─ Imputar dados faltantes
   └─ Normalizar variáveis

2. ESCOLHER MODELO
   ├─ Random Forest (simples)
   ├─ XGBoost (melhor)
   └─ LightGBM (mais rápido)

3. VALIDAR
   └─ Cross-validation 5-fold
```

---

## 📈 Estrutura do Relatório

O arquivo HTML/PDF tem **10 seções**:

1. **Introdução** - O que é a análise
2. **Dados** - Tipo de cada variável
3. **Faltantes** - Onde faltam dados
4. **Variáveis Discretas** - Gráficos boxplot
5. **Variáveis Contínuas** - Distribuições
6. **Qualitativas** - Frequências
7. **Correlações** - Relações entre variáveis
8. **Relação com Y** - O que afeta compra
9. **Testes Estatísticos** - Chi-square
10. **Conclusões** - Recomendações finais

---

## 🚀 Próximos Passos

Depois de ler o relatório:

### Curto Prazo (Esta semana)
- [ ] Ler o relatório HTML/PDF
- [ ] Entender as recomendações
- [ ] Explorar train.csv com Python/R

### Médio Prazo (Próximas 2 semanas)
- [ ] Remover var65, var66
- [ ] Imputar dados faltantes
- [ ] Normalizar variáveis
- [ ] Testar modelos

### Longo Prazo (Próximo mês)
- [ ] Otimizar hiperparâmetros
- [ ] Criar features novas
- [ ] Fazer submissão no Kaggle

---

## ❓ Dúvidas?

**P: Por onde começo?**
R: Abra `Analise_Exploratoria.html` (mais fácil) ou `Analise_Exploratoria.pdf`

**P: Qual arquivo uso para treinar modelo?**
R: `train.csv`

**P: Para que serve metadata.csv?**
R: Mostra o tipo de cada variável

**P: Posso ignorar test.csv?**
R: Sim, use ele só para submissão no Kaggle depois

**P: Onde vejo o código?**
R: Está no apêndice do PDF (arquivo .Rmd que gerou tudo)

---

## 📊 Resumo dos Dados

- **Clientes**: 59.381
- **Variáveis**: 69 explicativas + 1 ID + 1 Y = 71 colunas
- **Y balanceada**: ~50% comprou, ~50% não comprou
- **Tipos**: 35 nominais, 4 ordinais, 18 discretas, 12 contínuas

---

## ✨ Resultado Final

Você tem um **relatório profissional** com:
- ✅ 10 seções detalhadas
- ✅ 15+ gráficos
- ✅ Análises estatísticas
- ✅ Recomendações claras

**Pronto para usar como base para modelagem!**

---

**Criado em**: Junho 2026  
**Status**: Análise Exploratória Completa ✅
