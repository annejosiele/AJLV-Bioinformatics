---
title: Trilha 2 - Toxicologia Computacional
permalink: /toxicologia/
meta-viewport: width=device-width, initial-scale=1.0
---
# Trilha 2 – Toxicologia Computacional
 
## Retomando Conceitos
 
Na trilha anterior, vimos que a bioinformática depende da integração entre dados biológicos, ferramentas computacionais e rigor estatístico. Agora, vamos aplicar esta lógica especificamente à toxicologia.
 
Avaliar a segurança de uma substância química tradicionalmente exige ensaios extensos. A toxicologia computacional permite triar milhares de compostos, priorizar moléculas promissoras e identificar potenciais riscos toxicológicos antes mesmo de qualquer síntese em laboratório, de modo a otimizar a escala de desenvolvimento de produtos químicos e, principalmente, medicamentos.
 
## Diferentes Abordagens em Toxicologia Computacional
 
Para prever a toxicidade de um composto in silico, utilizam-se diferentes métodos, a depender da pergunta biológica e de aspectos relativos aos dados, como a quantidade:
 
<img src="{{ '/assets/figures/abordagens_insilico.webp' | relative_url }}" width="500" alt="Diferentes abordagens em toxicologia computacional">

*Fonte: VITAL et al, 2026 [Revista Bioinfo](https://bioinfo.com.br/a-toxicologia-in-silico-no-desenvolvimento-de-farmacos-um-caminho-etico-e-inovador-na-avaliacao-de-seguranca/)*

## Como o Computador "Enxerga" uma Molécula Química?
 
Para um ser humano, a forma mais natural de representar uma molécula é por meio de um desenho bidimensional ou um modelo tridimensional. Já para computadores, são necessárias representações matemáticas e textuais bem definidas.
 
Existem diferentes formas de traduzir a química para o ambiente digital:
 
1. **Tabelas de Conexão (Formatos de Arquivo)**: Arquivos como `.mol` ou `.sdf` armazenam as coordenadas de cada átomo no espaço (x,y,z) e uma matriz que indica quais átomos estão conectados por ligações químicas.
2. **Notações de String (Texto)**: Códigos em texto puro que condensam toda a conectividade e estereoquímica da molécula em uma única linha de caracteres.

## Representação Molecular via SMILES
 
A notação textual mais amplamente utilizada na quimioinformática é o SMILES (Simplified Molecular Input Line Entry System). O SMILES converte a estrutura química em uma sequência legível por computador usando regras simples:
 
- **Átomos**: Representados por seus símbolos químicos (C para carbono, O para oxigênio, N para nitrogênio). Letras maiúsculas indicam átomos não aromáticos; letras minúsculas (c, o, n) indicam aromaticidade.
- **Ligações**: Ligações simples são implícitas; ligações duplas usam `=` (ex: C=O) e triplas usam `#` (ex: C#N).
- **Ramificações**: Enclausuradas entre parênteses. Por exemplo, o etanol é representado por `CCO`, enquanto o isopropanol é `CC(C)O`.
- **Anéis**: Indicados por números logo após os átomos onde o anel se fecha. Por exemplo, o benzeno é representado por `c1ccccc1`.

| Composto | Estrutura 2D | SMILES |
|---|---|---|
| Etanol | <img src="{{'/assets/figures/ethanol.webp' | relative_url }}" width="80"> | `CCO` |
| Isopropanol | <img src="{{'/assets/figures/isopropanol.webp' | relative_url }}" width="80"> | `CC(C)O` |
| Benzeno | <img src="{{'/assets/figures/benzene.webp' | relative_url}}" width="80"> | `c1ccccc1` |
 
 
O formato SMILES permite armazenar e recuperar milhões de estruturas em bancos de dados rapidamente, ocupando pouquíssimo espaço de memória.
 
## RDKit: A Biblioteca Essencial da Quimioinformática
 
Para manipular, converter e calcular propriedades de moléculas representadas em SMILES ou outros formatos, são utilizadas bibliotecas especializadas. O RDKit é o conjunto de ferramentas open-source amplamente aplicado na quimioinformática e na toxicologia computacional.
 
Integrado principalmente à linguagem Python, o RDKit permite:
 
- Ler e converter diferentes formatos moleculares (SMILES, MOL, SDF, PDB).
- Sanitizar estruturas (corrigir valências, padronizar cargas e remover sais).
- Gerar representações 2D e 3D de moléculas.
- Calcular descritores moleculares físico-químicos e gerar fingerprints moleculares para modelos preditivos.
Desta forma, chegou o momento de dar vida aos conceitos! Partimos agora para a nossa aula prática em toxicologia computacional, onde você verá como a teoria se traduz em linhas de código e dados reais. Nessa etapa, você irá manipular estruturas digitais e vivenciar como a inteligência computacional é aplicada na avaliação de compostos químicos.
 
<div class="nav-buttons">
  <a href="{{ site.baseurl }}/bioinformatica/" class="btn-back">← Trilha anterior</a>
  <a href="{{ site.baseurl }}/toxicologia/pratica/" class="nav-btn">Prática 1 →</a>
</div>