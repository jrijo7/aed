# 🔍 Análise Exploratória: Porto Seguro Data Challenge

> Análise exploratória completa do dataset Porto Seguro do Kaggle, investigando padrões, correlações e características das 68 variáveis explicativas para prever compra de produtos.

![Badge License](https://img.shields.io/badge/License-MIT-blue.svg)
![Badge R](https://img.shields.io/badge/Language-R-276DC3.svg)
![Badge Status](https://img.shields.io/badge/Status-Completo-success.svg)
![Badge Kaggle](https://img.shields.io/badge/Dataset-Kaggle-20BEFF.svg)

---

## 📌 Visão Geral

Este projeto realiza uma **análise exploratória de dados (EDA)** completa sobre o dataset **Porto Seguro**, buscando compreender:

- 🎯 **Objetivo**: Criar uma regra de aceitação/rejeição para novos clientes baseada em padrões de compra
- 📊 **Dados**: 70 colunas (1 ID + 68 variáveis explicativas + 1 variável resposta Y)
- 👥 **Observações**: ~59.381 clientes
- 📈 **Resultado**: Variável binária Y (0 = não comprou, 1 = comprou)

---

## 📂 Estrutura do Projeto

```
porto-seguro-eda/
│
├── 📄 README.md                           ← Você está aqui
├── 📄 LICENSE                             ← MIT License
├── 📄 .gitignore                          ← Arquivos a ignorar
├── 📄 CONTRIBUTING.md                     ← Como contribuir
├── 📄 CHANGELOG.md                        ← Histórico de versões
│
├── 📁 data/                               ← Dados (não versionar)
│   ├── train.csv                          ← Dataset principal
│   ├── metadata.csv                       ← Descrição das variáveis
│   ├── test.csv                           ← Dados de teste (não usar)
│   └── submission_sample.csv              ← Exemplo submissão (não usar)
│
├── 📁 src/                                ← Código-fonte
│   ├── Analise_Exploratoria.Rmd           ← Código RMarkdown PRINCIPAL
│   └── Analise_Exploratoria_CORRIGIDA.Rmd ← Versão sem erros CRAN
│
├── 📁 output/                             ← Saídas geradas (não versionar)
│   ├── Analise_Exploratoria.pdf           ← Relatório em PDF (378 KB)
│   ├── Analise_Exploratoria.html          ← Versão em HTML (12 KB)
│   └── graficos/                          ← Gráficos individuais (se salvar)
│
└── 📁 docs/                               ← Documentação
    ├── INSTRUCOES_COMO_USAR.md            ← Passo a passo
    └── SOLUCAO_ERRO_CRAN.md               ← Solução de erros
```

---

## 🚀 Como Começar

### 1. Estrutura Inicial (Clone)

```bash
# Clonar repositório
git clone https://github.com/seu-usuario/porto-seguro-eda.git
cd porto-seguro-eda

# Criar pasta de dados
mkdir -p data
mkdir -p output
mkdir -p src
mkdir -p docs
```

### 2. Adicionar Dados

```bash
# Baixar do Kaggle:
# https://www.kaggle.com/c/porto-seguro-data-challenge/overview

# Colocar nesta pasta:
data/
├── train.csv
├── metadata.csv
├── test.csv
└── submission_sample.csv
```

### 3. Executar Análise

```bash
# Opção A: RStudio
# 1. File → Open → src/Analise_Exploratoria_CORRIGIDA.Rmd
# 2. Clique em [Knit → Knit to PDF]
# 3. PDF será salvo em output/

# Opção B: Terminal
Rscript -e "rmarkdown::render('src/Analise_Exploratoria_CORRIGIDA.Rmd', output_dir='output/')"
```

### 4. Resultado

```
output/
├── Analise_Exploratoria.pdf  ← Seu relatório
└── Analise_Exploratoria.html ← Versão web
```

---

## 📊 Dataset

### Composição das Variáveis

| Tipo | Quantidade | Características |
|------|-----------|-----------------|
| **Qualitativo Nominal** | 35 | Categorias sem ordem |
| **Qualitativo Ordinal** | 4 | Categorias com ordem |
| **Quantitativo Discreto** | 18 | Valores inteiros |
| **Quantitativo Contínuo** | 12 | Valores em [0,1] |
| **Variável Resposta (Y)** | 1 | Binária (0 ou 1) |

### Dados Faltantes

- **Identificados como**: -999 (CSV) → NA (R)
- **Padrão**: Altamente heterogêneo
- **Críticas**: var65, var66 (~95% faltantes)
- **Recomendação**: Remover var65 e var66

---

## 🔬 O Que a Análise Inclui

### ✅ Análise Univariada
- Estatísticas descritivas de todas as variáveis
- Boxplots de quantitativas (discretas e contínuas)
- Frequências de qualitativas

### ✅ Análise Bivariada
- Matrizes de correlação (3 tipos)
- Testes chi-square para associação
- Análise estratificada por Y

### ✅ Relatório Profissional
- PDF com índice automático
- 10 seções estruturadas
- 15+ gráficos informativos
- Conclusões estratégicas
- Recomendações para modelagem

---

## 📈 Principais Achados

### 1. Dados Faltantes
```
Heterogeneidade alta entre variáveis
├─ var65, var66: ~95% faltantes → REMOVER
├─ Maioria: < 10% faltantes → Imputação KNN
└─ Impacto geral: MÍNIMO
```

### 2. Variáveis Quantitativas
```
Escalas muito diferentes
├─ Discretas: range 0-60 (var52)
├─ Contínuas: restritas a [0,1]
├─ Variabilidade: ALTA (bom!)
└─ Necessário: Padronização
```

### 3. Correlações
```
Padrão geral: BAIXA correlação
├─ Entre variáveis: próxima a zero
├─ Com Y: também baixa
└─ Implicação: Relações não-lineares
```

### 4. Relação com Y
```
Balanceamento: ~50-50
├─ Quantitativas: fraca correlação com Y
├─ Nominais: algumas associações significativas
└─ Modelo necessário: Complexo (RF, XGB)
```

---

## 🛠️ Arquivos do Projeto

### Código Principal

| Arquivo | Localização | Descrição | Status |
|---------|------------|-----------|--------|
| `Analise_Exploratoria_CORRIGIDA.Rmd` | `src/` | Versão SEM erros CRAN | ✅ Use este |
| `Analise_Exploratoria.Rmd` | `src/` | Versão original | ⚠️ Com erro |

### Saídas Geradas

| Arquivo | Localização | Tamanho | Tipo |
|---------|------------|--------|------|
| `Analise_Exploratoria.pdf` | `output/` | 378 KB | PDF com índice |
| `Analise_Exploratoria.html` | `output/` | 12 KB | Versão web |

### Documentação

| Arquivo | Localização | Conteúdo |
|---------|------------|----------|
| `INSTRUCOES_COMO_USAR.md` | `docs/` | Passo a passo |
| `SOLUCAO_ERRO_CRAN.md` | `docs/` | Troubleshooting |

---

## 🔄 Caminhos de Arquivo (IMPORTANTE!)

### Se você mantiver a estrutura recomendada:

```r
# CAMINHOS CORRETOS para o código:

# ✅ CORRETO (usar estes):
train <- read.csv("data/train.csv", na.strings = "-999")
metadata <- read.csv("data/metadata.csv")

# ❌ ERRADO (não usar):
train <- read.csv("train.csv", na.strings = "-999")  # Arquivo não encontrado!
```

### Se estiver na pasta `src/`:

```r
# Se executar o .Rmd da pasta src/
train <- read.csv("../data/train.csv", na.strings = "-999")
metadata <- read.csv("../data/metadata.csv")

# ../ = volta uma pasta (para raiz do projeto)
```

### Para salvar outputs:

```r
# Salvar PDF em output/
# (Automático quando você clica em Knit)

# Se quiser salvar gráficos individuais:
png("output/grafico_faltantes.png", width=1200, height=600)
# seu código de gráfico
dev.off()
```

---

## 📝 Configuração do Código

### Se Mudar os Caminhos

Se criar uma estrutura diferente, **MUDE ISTO NO CÓDIGO**:

```r
# NO INÍCIO DO ARQUIVO .Rmd

# LINHA ~10 (procure por):
train <- read.csv("data/train.csv", na.strings = "-999")
metadata <- read.csv("data/metadata.csv")

# Mude para seu caminho se necessário:
train <- read.csv("seu/caminho/train.csv", na.strings = "-999")
metadata <- read.csv("seu/caminho/metadata.csv")
```

**AVISO**: Se mudar os caminhos, atualize também EM TODOS OS LUGARES que usa os dados.

---

## 🎯 Workflow Recomendado

### Primeira Execução

```
1. Clone repositório
2. Crie pastas (data, src, output, docs)
3. Coloque train.csv e metadata.csv em data/
4. Abra src/Analise_Exploratoria_CORRIGIDA.Rmd
5. Clique em Knit → Knit to PDF
6. PDF será gerado em output/
7. Pronto! Envie para GitHub
```

### Atualizações Futuras

```
1. Edite o código .Rmd
2. Clique em Knit
3. Git add, commit, push
4. GitHub atualizado!
```

---

## 📊 Saídas Esperadas

### PDF Gerado

- **Tamanho**: ~2-3 MB
- **Páginas**: ~20-30 (com gráficos)
- **Tempo**: 2-5 minutos para gerar
- **Localização**: `output/Analise_Exploratoria.pdf`

### Conteúdo

```
✅ Capa (título, autor, data)
✅ Índice (clicável)
✅ 10 seções estruturadas
✅ 15+ gráficos
✅ Códigos R comentados
✅ Tabelas e estatísticas
✅ Conclusões estratégicas
```

---

## 🚀 Enviando para GitHub

### 1. Configurar .gitignore

```bash
# Já vem pronto no arquivo .gitignore
# Ignora automaticamente:
data/*.csv          # Dados brutos
output/*.pdf        # PDFs grandes
output/*.html       # HTMLs
*.Rhistory
.RData
```

### 2. Subir para GitHub

```bash
git add .
git commit -m "feat: análise exploratória completa com 10 seções"
git push origin main
```

### 3. Estrutura no GitHub

```
seu-repo/
├── README.md                    ← Exibido automaticamente
├── src/Analise_Exploratoria_CORRIGIDA.Rmd
├── data/metadata.csv            ← (gitignored)
└── docs/INSTRUCOES_COMO_USAR.md
```

---

## 📞 Troubleshooting

### Erro: "Arquivo não encontrado"

```r
# Verifique o caminho:
getwd()  # Qual pasta o R está usando?

# Se necessário:
setwd("C:/seu/caminho/do/projeto")
```

### Erro: "CRAN sem mirror definido"

```r
# Execute no console:
options(repos = c(CRAN = "https://cloud.r-project.org/"))
install.packages("corrplot")
```

### Erro: "Dados não carregados"

```r
# Verifique:
file.exists("data/train.csv")  # TRUE ou FALSE?
list.files("data/")            # Quais arquivos existem?
```

---

## 🎓 Próximos Passos

1. ✅ **Completar EDA** (você já fez!)
2. ⏳ **Pré-processamento**: Imputação, normalização, codificação
3. ⏳ **Engenharia de Features**: Interações, transformações
4. ⏳ **Modelagem**: Random Forest, XGBoost
5. ⏳ **Validação**: Cross-validation, otimização

---

## 📚 Referências

- **Kaggle**: [Porto Seguro Data Challenge](https://www.kaggle.com/c/porto-seguro-data-challenge/)
- **RMarkdown**: [rmarkdown.rstudio.com](https://rmarkdown.rstudio.com/)
- **R Documentation**: [r-project.org](https://www.r-project.org/)

---

## 📄 Licença

Este projeto está licenciado sob a [MIT License](LICENSE).

---

## 👨‍💻 Autor

**[João Victor]**

- GitHub: [@jrijo7](https://github.com/jrijo7)
- Email: joaovictor_gomes.7@hotmail.com
- LinkedIn: [jrijo7](https://www.linkedin.com/in/jrijo7/)

---

## ⭐ Se Este Projeto Ajudou

Considere dar uma ⭐ no GitHub!

---

**Última atualização**: Junho 2026  
**Status**: ✅ Análise Completa - Pronto para GitHub
