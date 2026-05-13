# Análise Epistemológica do artigo Evolucionário

---

## Slide 1 — Capa

Boa tarde. Vou apresentar uma análise epistemológica do artigo *Wi-Fi RTT Indoor Positioning Using Visibility Matching With NLOS Receptions*, de Zhen Lyu e colegas, publicado em junho de 2025 no *IEEE Internet of Things Journal*.

O objetivo da apresentação não é repetir o conteúdo técnico do artigo. É olhar para ele com as lentes da disciplina: que tipo de problema o artigo enfrenta, que hipótese ele propõe, em que sentido a evidência sustenta as conclusões, e onde estão os limites epistemológicos da contribuição. Em uma frase: queremos entender que tipo de ciência este artigo faz.

---

## Slide 2 — Juízo central

Começo pela conclusão, para deixar claro o ponto de chegada. Este é um artigo *evolucionário*. Na linguagem de Kuhn, ele é *ciência normal* bem feita: refina o paradigma vigente de posicionamento por rádio em ambientes internos, mas não inaugura um paradigma novo.

Por que evolucionário? Porque a *ideia central* — usar a sombra do sinal como informação espacial — já existia. Veio do *shadow matching* aplicado a GNSS em cânions urbanos, de Groves em 2011. O que os autores fazem é transportar essa ideia para Wi-Fi RTT em ambiente interno, combinando-a com um modelo *multiwall* de propagação e com uma planta digital. A genealogia é rastreável: RADAR, em 2000, abriu o problema; depois vieram fingerprinting, RTT, modelos NLOS, e agora o *visibility matching*.

O ganho quantitativo é forte — vou mostrar os números mais à frente — mas é da ordem do *refinamento técnico*, não de uma ruptura. E isso não diminui o valor científico do trabalho. Como discutimos na disciplina, engenharia avança principalmente por *aproximações sucessivas* dentro de um paradigma estável.

---

## Slide 3 — Motivação e relevância

Sobre o lugar do artigo no campo: foi publicado em junho de 2025, no *IEEE Internet of Things Journal*, periódico Q1, fator de impacto 8,9 — alto impacto. É continuidade direta do trabalho do IPN-Lab, em Hong Kong, e o autor-âncora é o Guohao Zhang, com h-index 27 e mais de 2.300 citações.

A frente técnica também é ativa. *NLOS identification* combinada com Wi-Fi RTT é uma fronteira recente, e o artigo de 2023 do mesmo grupo, que propõe o modelo *multiwall*, é uma das bases que ele estende.

Em termos bibliométricos, ainda há poucas citações — entre cinco e seis. Mas isso é compatível com a curta janela de circulação: o artigo tem menos de um ano. O ponto forte, por ora, é a posição em uma frente técnica recente, não uma influência já consolidada. Para usar o vocabulário das aulas: temos um trabalho que se insere no *consenso ativo* da comunidade, mas ainda não testado por ela em escala.

---

## Slide 4 — Problema e situação de contorno

Agora vou mapear o artigo pelo recorte epistemológico que usamos em sala. A *pergunta que organiza o artigo* é: como posicionar um usuário em ambiente interno por Wi-Fi RTT quando há NLOS severo, poucos APs e medições com outliers?

Decompondo: o *objeto* é o conjunto dispositivo, APs Wi-Fi, medidas de RTT e RSSI, e planta digital. O *fenômeno* é a propagação do sinal sob condições de linha de visada e não-visada, com atenuação, multipercurso e erro de alcance. O *domínio* são ambientes internos com infraestrutura Wi-Fi e planta conhecida.

A *situação de contorno* é importante para entender o alcance da contribuição. O método assume NLOS severo, poucos APs — três no experimento —, posições dos APs conhecidas e planta digital disponível. Fora dessa situação, o método pode não valer. As *condições de operação* envolvem RTT, RSSI, candidatos em grade e cálculo de visibilidade por interseção entre a linha AP-candidato e as paredes. E a *métrica* é o erro de posição em metros: média, mediana, desvio padrão e CDF.

Reparem que esse mapeamento já antecipa onde o artigo pode ser criticado: na sensibilidade à situação de contorno e à qualidade da planta digital.

---

## Slide 5 — O deslocamento epistemológico

Aqui está, na minha leitura, o coração do trabalho. É um *deslocamento de estatuto* do NLOS.

Antes deste artigo, a literatura tratava o NLOS como erro. O sinal bloqueado ou refletido degrada o RTT, gera erro de alcance, e a tarefa principal é mitigar, corrigir ou atenuar essa perturbação. O NLOS é ruído.

Neste artigo, o NLOS muda de papel. Em vez de ser apenas perturbação, ele passa a revelar uma *característica saliente*: a visibilidade dos APs. Em outras palavras, saber que um AP é invisível, do ponto de vista do receptor, é informação útil — porque indica que entre o usuário e aquele AP existe uma parede. E a planta digital transforma essa informação em uma restrição espacial sobre onde o usuário pode estar.

Usando a linguagem da Aula 9: o que era *pregnante* no quadro — o NLOS, escondido como erro — torna-se *saliente*. A figura-fundo se inverte. Esse tipo de movimento, transformar uma fraqueza experimental em pista informacional, é um padrão clássico de avanço por aproximações sucessivas dentro de um paradigma.

---

## Slide 6 — Hipótese e ensaio de solução

A hipótese central do artigo pode ser decomposta em quatro camadas, que se encaixam.

A *hipótese física* é que paredes alteram RTT e RSSI de modo informativo — não são apenas ruído, carregam estrutura. A *hipótese geométrica* é que a planta digital permite prever, para cada posição candidata, quais APs estariam visíveis. A *hipótese estatística* é que, a partir das medições de RTT e RSSI, é possível inferir a visibilidade observada de cada AP no ponto onde o usuário está. E a *hipótese computacional* costura tudo: a melhor posição é aquela que maximiza a coerência entre o alcance estimado e a visibilidade observada.

O *ensaio de solução*, no sentido popperiano, é a combinação: modelo *multiwall* de RTT, mais visibilidade simulada a partir da planta, mais visibilidade observada via RSSI versus RTT, mais busca em grade para encontrar o candidato que melhor satisfaz todas as restrições. É uma articulação, não uma única ideia.

---

## Slide 7 — Conteúdo lógico e empírico

Esta divisão é diretamente da Aula 9. *Conteúdo lógico* é o que pode ser deduzido formalmente. *Conteúdo empírico* é o que pode ser observado e medido.

No artigo, o conteúdo lógico aparece nas equações: o modelo *multiwall* de RTT com termo de penetração por parede, a interseção linha-parede usada para decidir visibilidade, a função XNOR que compara visibilidade simulada e observada, e a função de pontuação que combina restrição de alcance e restrição de visibilidade.

O conteúdo empírico aparece nos três ambientes reais coletados na PolyU, em Hong Kong: um corredor estreito, um lounge espaçoso e uma suíte. Três APs Google Nest Wi-Fi, dados de RTT e RSSI a 3 Hz, *ground truth* obtido por LiDAR e comparação contra cinco baselines.

O ponto importante, e a aula reforça isso, é que a *validade* do trabalho não nasce do modelo formal sozinho nem da medição sozinha. Ela nasce da articulação entre os dois — o que aproxima o artigo de um sistema de inquirição *kantiano*: teoria e dados se sustentam mutuamente.

---

## Slide 8 — Evidência experimental

Agora os números. Em todos os três cenários, o método proposto, chamado VM de *Visibility Matching*, supera os baselines clássicos.

No corredor estreito, a mediana do erro de posição cai de cerca de 1,19 metros, da trilateração, para 0,67 metros. No lounge, cai de 1,47 metros do SMACOF, que era o melhor baseline, para 0,79 metros. Na suíte, cai de 1,77 metros para 0,82 metros. O artigo resume essa melhora afirmando que a acurácia mediana passou, no agregado, de 2,3 metros para 0,64 metros.

Mas, atenção, e isso vem direto de Popper: evidência é *corroboração*, não prova. Os dados sustentam fortemente a vantagem do VM nos cenários testados. Eles não autorizam concluir superioridade universal. Três ambientes em um único prédio, em Hong Kong, com três APs e plantas específicas, não esgotam o espaço de aplicação. A teoria fica corroborada — permanece provisoriamente válida — mas continua aberta à refutação por novos experimentos.

---

## Slide 9 — Falseabilidade e reprodutibilidade

Pela definição popperiana, uma boa teoria deve permitir que se imagine como falseá-la. Aqui o artigo está em situação razoável.

*Como falsear*: basta testar em layouts e materiais diferentes, alterar quantidade e distribuição de APs, usar plantas incompletas ou desatualizadas, ou comparar com métodos posteriores que surgirem. Cada uma dessas vias é um experimento que pode derrubar o ganho relativo do método.

*Como reproduzir*: o artigo informa equipamentos, frequência de amostragem, métricas, equações e os baselines usados. Mas faltam o código, o dataset e o conjunto completo de parâmetros calibrados. A réplica exata depende fortemente da planta e do ambiente físico — não basta rodar o mesmo software.

Em chave popperiana: o artigo oferece uma teoria operacional *criticável*, e isso é bom. É ciência. Mas a reprodução estrita ainda depende de condições auxiliares que não estão totalmente abertas. Estamos no terreno que Lakatos chamaria de falseabilidade *não-ingênua*: o teste exige acordo da comunidade sobre quando o método foi posto à prova de verdade.

---

## Slide 10 — Análise crítica

Resumindo o artigo por dimensões.

O *problema* está bem delimitado: NLOS severo, poucos APs, outliers de distância. A *hipótese* é plausível e elegante: o NLOS deixa de ser apenas erro e passa a carregar informação espacial. O *método* é coerente, embora dependa de planta digital correta e de ajuste cuidadoso de parâmetros, em especial a tolerância da restrição de alcance.

A *evidência* é boa nos três cenários testados, com comparação contra cinco baselines. A *generalização*, por outro lado, é limitada: outros edifícios, outros materiais, outras densidades de APs e mudanças ambientais podem alterar a visibilidade esperada. E a *reprodutibilidade* é parcial — temos equações e métricas, mas não código, dataset nem parâmetros completos.

A crítica central, portanto, não é que o método não funcione. Funciona, e bem, onde foi testado. A crítica é que o artigo ainda não demonstra robustez geral para ambientes internos variados.

---

## Slide 11 — Limites e alcance da contribuição

Resumo o que considero força e o que considero limite.

A *força epistemológica* é mudar o estatuto do NLOS, de perturbação experimental para pista informacional. Esse tipo de movimento, embora dentro do paradigma, expande o vocabulário disponível para o campo. A *força metodológica* é a articulação clara entre modelo físico de propagação, geometria da planta, inferência LOS-NLOS por RSSI e validação empírica controlada por LiDAR.

Os limites também são claros. Há um *limite de representação*: o ambiente real é reduzido à planta digital, aos APs, às paredes e aos candidatos em grade. Móveis, pessoas, portas abertas ou fechadas, refrigeradores, ficam de fora do modelo. Há um *limite operacional*: variações nesses elementos, ou erros na planta, podem alterar a visibilidade esperada e degradar o método. E há a questão do *impacto*. Por o artigo ser muito recente, o baixo número de citações não é fraqueza científica; apenas impede afirmar uma influência já consolidada.

---

## Slide 12 — Síntese final

Para fechar. O artigo avança por aproximação sucessiva, não por ruptura. O centro epistemológico está na mudança de estatuto do NLOS, de erro para informação. A evidência é forte para os cenários testados e limitada para generalização. E a crítica principal recai sobre o alcance externo, a dependência da planta, a calibração e os artefatos de reprodução.

A frase que resume minha leitura é esta: o artigo não muda a pergunta da área. Ele melhora a resposta. E faz isso ao transformar uma fraqueza experimental — o NLOS — em uma pista epistemologicamente útil.

