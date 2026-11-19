# REVISÃO independente — formacao-cinema-ia-geracao-v72 (19/10/2026)

Revisor: subagente que não escreveu o curso, com BRIEF-CURSO, CURRICULO, AUDITORIA-LOCAL e PESQUISA-ESTADO-DA-ARTE (longrun 2026-10-19-formacao-cinema-ia-v72). Só leitura; rodou `conferir.py --exemplo/--errado` nas 8 aulas e casos à mão (inclusive um clipe 1280×704); conferiu em fonte primária LTX-2.5 (Hugging Face), docs.ltx.io, docs.comfy.org (Wan 2.2), repositório do FLUX.2, guia de prompt do Google (15/10/2026) e docs.midjourney.com (V8.1, 30/04/2026). Revisão feita sobre o PT, antes da tradução.

## Rodada 1 — 7/10
Bom: toda versão com data; nenhum [incerto] como fato; Sora só como estudo de caso; sem nome de diretor/marca; links para os donos de assunto; quizzes coerentes.

Graves:
1. Aula 4: o conferidor de clipe recusava 1280×704 (720p do Wan 2.2 5B, o modelo aberto que o curso recomenda) como "1.85:1".
2. Aula 1: a data "out/2026" era partida na barra pelo motor; qualquer "2026"/"10" no arquivo satisfazia a regra (e "Sora 2" passava, contra o que o PLANO prometia).

Menores: falso positivo na câmera da aula 2; vocabulário de câmera limitado; fala sem nome aceita na aula 6; "trava: igual" aceita na aula 5; trava diferente da ficha do curso 0; "quem diz:" atribuído ao guia do Google; "8 geradores" contando o Sora; Midjourney sem link; "pronto quando" subjetivo na aula 1 e2.

## Correções
- Motor 7.13.16 (formato-curso-inema): proporção com 3 % de folga; família de termos com " / " aceita barra dentro do termo.
- Aula 1: data procurada como "out/2026" (sem "10/2026"); sub diz o que a página procura; PLANO sem a promessa sobre Sora; e2 com critério objetivo.
- Aula 2: sub diz o que é conferido e onde está o vocabulário (curso 0); "quem diz: texto" dito como adaptação do "says:" do guia.
- Aula 5: sub diz que a página só confere o formato; trava igual à linha "Nunca muda" da ficha do curso 0 (também na aula 8).
- Aula 6: fala exigida no formato "Nome diz: texto".
- Página inicial: "7 geradores (+ o caso Sora)".

## Rodada 2 — 8,5/10
Graves resolvidos. Menores aceitos: a data vale no arquivo inteiro (não só na linha Versão); só "out/2026" é aceito (o exercício pede a data da tabela da aula); vocabulário de câmera é o do curso 0; Midjourney sem link (403 para o validador).

NOTA: 8,5/10
