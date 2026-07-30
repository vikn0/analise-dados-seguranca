# Framework de Análise de Dados: Monitoramento e Segurança Patrimonial

Este projeto apresenta um padrão estruturado de etapas para análise de dados operacionais de segurança, desenvolvido de forma autônoma para transformar registros de monitoramento em insights estratégicos.

## 📊 O Padrão de Etapas Desenvolvido

### 1. Inspeção
* Levantamento inicial da estrutura da base de dados.
* Identificação de colunas críticas como `PERIODO DE GRAVAÇÃO`, `TURNO` e `AÇÃO TOMADA`.

### 2. Limpeza e Sanitização
* **Tratamento de Falsos Nulos**: Identificação e correção de textos `'NAN'` gerados por conversões na base, substituindo-os por nulos reais (`np.nan`).
* **Padronização**: Aplicação de caixa alta (`UPPERCASE`) em todas as colunas categóricas para eliminar duplicidades por digitação.

### 3. Transformação e Modelagem
* **Extração com Regex**: Uso de Expressões Regulares para separar horários de início/fim e extrair variáveis ocultas (Nomes de Vigilantes e Saídas Utilizadas).
* **Conversão de Tipos**: Ajuste de strings de tempo (incluindo formatos AM/PM) para objetos reais de duração (`Timedelta`), permitindo cálculos matemáticos na base.
* **Criação de Métricas**: Desenvolvimento da coluna `DURACAO_GRAVACAO` para medir a eficiência dos acionamentos.

### 4. Análise Exploratória e Insights
* **Ranking de Logística**: Descoberta dos principais gargalos físicos do prédio (ex: Escadaria do EDG como ponto crítico).
* **Matriz de Produtividade**: Identificação dos vigilantes mais atuantes na linha de frente através de contagem volumétrica.
* **Distribuição Volumétrica**: Análise proporcional de acionamentos por turno e tipo de ocorrência.

## 🛠️ Tecnologias Utilizadas
* Python
* Pandas e NumPy
* Matplotlib e Seaborn
