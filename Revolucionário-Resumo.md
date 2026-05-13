# RADAR: An In-Building RF-based User Location and Tracking System
**Bahl, P. & Padmanabhan, V. N. (2000) — IEEE INFOCOM 2000**

---

## Análise Metodológica/Tecnológica

O sistema RADAR utiliza a infraestrutura de redes Wi-Fi (padrão WaveLAN, 2.4 GHz) já existente em edifícios para localizar e rastrear usuários em ambientes internos, dispensando hardware dedicado. A metodologia combina duas abordagens: uma empírica, baseada na coleta prévia de amostras de intensidade de sinal (RSSI) em pontos conhecidos do ambiente, e uma teórica, baseada em um modelo de propagação de rádio com fator de atenuação por parede (Wall Attenuation Factor). A localização do usuário é estimada por triangulação, comparando as leituras em tempo real com o banco de dados pré-coletado através de uma busca por vizinho mais próximo no espaço de sinais (NNSS). Os experimentos, conduzidos em um andar de escritório com três estações-base, demonstraram resolução mediana de 2 a 3 metros pelo método empírico e cerca de 4,3 metros pelo modelo de propagação, avaliados por meio de funções de distribuição acumulada do erro.

---
## Análise Epistemológica

O trabalho adota uma abordagem predominantemente empirista-indutiva: parte da observação sistemática de medições de intensidade de sinal em condições controladas para inferir padrões que permitam estimar a posição do usuário. O conhecimento é construído de baixo para cima, a partir de dados coletados em campo, e não de princípios teóricos a priori — embora o modelo de propagação por paredes represente uma tentativa de generalização dedutiva. Há um pragmatismo evidente na escolha de utilizar a infraestrutura de rede já disponível, priorizando a viabilidade prática sobre a precisão máxima. O artigo reconhece explicitamente as limitações do conhecimento produzido (variabilidade por orientação do corpo, dependência do ambiente específico), posicionando seus resultados como aproximações úteis e não como verdades absolutas, o que revela uma postura epistemológica modesta e orientada à aplicação.

---

BAHL, Paramvir; PADMANABHAN, Venkata N. RADAR: an in-building RF-based user location and tracking system. In: IEEE INTERNATIONAL CONFERENCE ON COMPUTER COMMUNICATIONS (INFOCOM), 19., 2000, Tel Aviv. Proceedings [...]. New York: IEEE, 2000. p. 775–784. DOI: 10.1109/INFCOM.2000.832252.

---

Este trabalho é considerado pioneiro em localização interna baseada em sinais de radiofrequência de redes sem fio. Antes dessa publicação, os sistemas de localização indoor dependiam de infraestrutura dedicada, como transmissores infravermelhos ou sensores magnéticos. Ao demonstrar que medições de intensidade de sinal (RSSI) de access points já existentes poderiam ser utilizadas para estimar a posição de usuários em ambientes internos, o RADAR abriu caminho para todo o campo de localização interna usando WiFi. Um número expressivo de trabalhos posteriores nesta área o citam como referência fundadora.
