# Projeto: Simulador de Zeros de Funções

**Autor:** Pedro Lucas Rodrigues Pinto

**Disciplina:** Cálculo Numérico — UNIVASF

**Semestre/ano:** 2026.2

## Descrição

Este repositório contém o código do simulador para localização de raízes de funções reais de uma variável. O programa implementa quatro métodos numéricos clássicos e compara seu desempenho (raiz encontrada, número de iterações, número de avaliações de f, tempo médio e resíduo |f(raiz)|):

- Bissecção
- Falsa Posição (Regula Falsi)
- Newton–Raphson
- Secante

O objetivo é oferecer uma ferramenta pedagógica para experimentar diferenças de convergência e robustez entre métodos abertos e fechados.

## Arquivos principais

- `simulador_zeros.py` — código-fonte principal (menu interativo, implementação dos métodos, geração de relatórios e gráficos).

## Funcionalidades

- Entrada interativa de funções (com parser seguro — sem uso direto de eval) e de parâmetros (intervalo, estimativas iniciais, precisão, critério de parada).
- Derivada numérica automática quando o usuário não fornece f'(x).
- Medição do número de avaliações de f e do tempo médio de execução (µs).
- Geração de relatório detalhado em `resultados/` (.txt com histórico de iterações) e, quando disponível, figuras em PNG com gráficos de convergência.
- Presets de exemplo para testes rápidos.

## Requisitos

- Python 3.8 ou superior
- (Opcional, para gráficos) matplotlib

Instalação rápida:

```bash
# clonar o repositório
git clone https://github.com/pedrolrp1232-star/Projeto-Zero-de-funcao-publico.git
cd Projeto-Zero-de-funcao-publico

# (opcional) criar ambiente virtual
python -m venv .venv
# macOS / Linux
source .venv/bin/activate
# Windows (PowerShell)
.\.venv\Scripts\Activate.ps1

# instalar matplotlib apenas se quiser gerar/visualizar gráficos
pip install matplotlib
```

## Como executar

No diretório do projeto, execute:

```bash
python simulador_zeros.py
```

O programa abre um menu interativo que permite escolher casos pré-definidos, digitar uma nova função, ajustar parâmetros e salvar relatórios e gráficos.

Saída:
- Relatórios detalhados em `resultados/*.txt` (com histórico de iterações)
- Gráficos em `resultados/*.png` (se matplotlib estiver disponível)

## Exemplos de uso

- Caso de teste rápido: `f(x) = cos(x) - x` (preset 1)
- Problemas de exemplo sobre resfriamento e carregamento de capacitor (presets 2 e 3)

## Boas práticas para digitar funções

- Use ponto `.` como separador decimal (ex.: `0.15`).
- Operadores: `+ - * / ^` (ou `**`)
- Funções suportadas: `sin, cos, tan, exp, ln, log, sqrt, abs`, etc. (veja a ajuda no menu do programa)
- Constantes: `pi`, `e`

## Observações acadêmicas

- O parser utiliza `ast` para validar a expressão de entrada; apenas números, UMA variável, operadores e funções aprovadas são permitidos.
- A derivada numérica usa diferenças centrais para fornecer f'(x) quando necessário.
- A medição de tempo é feita repetindo a chamada do método várias vezes para obter uma média robusta.

## Contato

Se precisar de alterações no README, formatação do relatório ou inclusão de instruções adicionais para submissão, abra uma issue ou envie uma mensagem para o autor: https://github.com/pedrolrp1232-star

## Licença

Uso acadêmico. Para permissões de distribuição e reutilização, consulte o autor.
