# Wi-Fi RTT Indoor Positioning Using Visibility Matching With NLOS Receptions
**Lyu, Z., Bai, S., Wang, X., Li, L. & Zhang, G. (2025) — IEEE Internet of Things Journal**

---
## Análise Metodológica/Tecnológica

O artigo propõe um método de posicionamento indoor baseado em Wi-Fi RTT (Round-Trip Time) que enfrenta o problema das recepções NLOS (sem linha de visada) por meio de uma técnica chamada visibility matching. A abordagem tecnológica se apoia em três pilares: um modelo de ranging multiwall que corrige os erros de medição de distância introduzidos pela penetração do sinal em paredes (considerando constante dielétrica e refração); a construção de um mapa de visibilidade simulada a partir da planta baixa digitalizada do ambiente; e a comparação entre a visibilidade observada (inferida pela relação RSSI × RTT) e a simulada para restringir os candidatos à posição do usuário. Experimentos foram conduzidos em três cenários reais distintos (corredor estreito, corredor amplo e suíte) usando APs Google Nest e ground truth obtido por LiDAR, alcançando precisão mediana entre 0,64 e 0,80 m — desempenho superior a métodos como trilateração, filtro de partículas e regressão por processos gaussianos.

---
## Análise Epistemológica

Este trabalho adota uma postura epistemológica hipotético-dedutiva: parte de modelos teóricos sobre propagação de ondas eletromagnéticas (perda em espaço livre, atenuação por paredes) e formula hipóteses sobre como a visibilidade dos APs pode ser inferida e utilizada como restrição adicional para o posicionamento. O conhecimento é construído pela interação entre modelagem teórica e validação experimental, num ciclo de conjectura e refutação controlada. A incorporação da planta baixa como informação a priori revela uma epistemologia que valoriza o conhecimento contextual estruturado — não se limita a dados brutos, mas os interpreta à luz de uma representação geométrica do ambiente. O artigo também demonstra consciência das fronteiras do conhecimento produzido, reconhecendo que o método falha quando todos os sinais são NLOS (como em salas fechadas), o que aponta para uma honestidade epistêmica sobre os limites de validade da abordagem.

---

LYU, Zhen; BAI, Shiyu; WANG, Xin; LI, Lin; ZHANG, Guohao. Wi-Fi RTT indoor positioning using visibility matching with NLOS receptions. IEEE Internet of Things Journal, v. 12, n. 12, p. 18779-18790, 15 jun. 2025. DOI: 10.1109/JIOT.2025.3559065.

---

O artigo foi escolhido por utilizar o protocolo Wi-Fi FTM (IEEE 802.11mc) para posicionamento indoor, mesma base tecnológica da minha pesquisa, e por apresentar uma técnica de classificação LOS/NLOS baseada na correlação RSSI-RTT que pode ser incorporada ao algoritmo em desenvolvimento para aprimorar a detecção e o tratamento de condições de multipercurso.