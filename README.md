# Vetorizacao_de_edificacoes
Método para vetorizar edificações a partir do plugin Deepness: Deep Neural Remote Sensing no Qgis
# Extração Automática de Edificações com o Plugin Deepness no QGIS
Este tutorial apresenta a metodologia completa para detecção e extração automática de edificações utilizando o plugin **Deepness – Deep Neural Remote Sensing** (Aszkowski et al., 2023), baseado em redes neurais profundas e integrado ao software QGIS. O processo utiliza imagens de alta resolução para identificar padrões de telhados, sombras e estruturas urbanas, permitindo quantificação precisa de ocupações urbanas.

---

##  1. Introdução
A quantificação de edificações é fundamental para estudos urbanos, planejamento territorial, regularização fundiária e delimitação de Áreas Urbanas Consolidadas (AUC). O plugin **Deepness** permite realizar esse mapeamento de forma rápida, padronizada e reprodutível, reduzindo erros humanos.

Recomendação sobre imagens:
- Utilize imagens com **resolução ≤ 1 m** (ortofotos, VANT, satélites de alta resolução).
- Em resoluções médias (Sentinel-2 / CBERS-4), recomenda-se aplicar filtros e pós-processamento.

---

##  2. Fluxograma Metodológico

![Fluxograma Metodológico](https://github.com/vitormateusgoncalves/Vetoriza-o_de_edifica-es/issues/1#issue-3704066237)

**Figura 1 – Procedimentos metodológicos**  
*Fonte: Os autores (2025)*

---

##  3. Metodologia 
### 3.1 Planejamento Inicial
- Delimitar área de estudo  
- Organizar dados e pastas  
- Carregar arquivos no QGIS  
- Definir sistema de coordenadas (preferencialmente UTM)

---

### 3.2 Aquisição da Imagem Base
A imagem deve ser atual, clara e de alta resolução.

![Imagem de alta resolução](https://github.com/vitormateusgoncalves/Vetoriza-o_de_edifica-es/issues/3#issue-3704076683)
**Figura 2 – Exemplo de imagem**  
*Fonte: Os autores (2025)*

---

### 3.3 Pré-processamento da Imagem
Etapas recomendadas:
1. Recortar área de interesse  
2. Ajustar resolução, se necessário  
3. Reprojetar para SRC adequado
4. Padronizar camadas  

---

### 3.4 Instalação do Plugin Deepness
No QGIS:  
`Complementos → Gerenciar e instalar complementos`  
Buscar por: **Deepness: Deep Neural Remote Sensing**

---

### 3.5 Carregamento do Modelo ONNX
Baixe o modelo pré-treinado:  
https://chmura.put.poznan.pl/public.php/dav/files/MwhgQNhyQF3fuBs/?accept=zip

No QGIS:  
`Deepness → Load ONNX Model`


---

### 3.6 Definição da Área de Inferência
Pode-se usar:
- Área visível  
- Área definida por shapefile  
- Extensão total da imagem  


---

### 3.7 Configuração dos Parâmetros
Ajuste:
- **Tile size**  
- **Overlap**  
- **Normalização**  
- **Uso de GPU (se houver)**  

Esses parâmetros afetam precisão e desempenho.

---

### 3.8 Execução da Inferência
O modelo irá:
- Dividir imagem em blocos  
- Avaliar cada pixel  
- Criar máscara de probabilidade de edificações  


---

### 3.9 Pós-processamento
Procedimentos do plugin:
1. Converter raster → vetor  
2. Remover ruídos  
3. Mesclar polígonos adjacentes  
4. Ajustar bordas manualmente  

---

### 3.10 Validação e Ajustes Manuais
Comparar o vetor com a imagem original para corrigir:
- Edificações não detectadas  
- Objetos falsos positivos  

Ferramentas úteis:
- Modo de edição  
- Modelador topológico  

---

### 3.11 Exportação do Resultado Final
Exportar para os formatos desejados:


Caminho:  
Botão direito na camada → **Exportar → Salvar feições como…**

![Exemplo de resultado](https://github.com/vitormateusgoncalves/Vetoriza-o_de_edifica-es/issues/2#issue-3704067757)
**Figura 3 – Exemplo de vetorização** 
*Fonte: Os autores (2025)*

---
##  4. Considerações Finais
O plugin **Deepness** é uma ferramenta moderna e robusta baseada em Deep Learning que facilita o mapeamento urbano e a identificação de edificações com alta precisão e padronização. Os resultados são aplicáveis em:

- Planejamento urbano  
- Estudos ambientais  
- Regularização fundiária  
- Delimitação de Áreas Urbanas Consolidadas (AUC)  
- Monitoramento territorial  

---

##  5. Referência
Aszkowski, A. et al. (2023). *Deep Neural Remote Sensing – Deepness Plugin for QGIS.*

---

