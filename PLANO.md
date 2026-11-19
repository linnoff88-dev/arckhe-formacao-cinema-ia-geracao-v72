# PLANO — Curso 1 · Geração: imagem e vídeo com IA em out/2026

Formação Cinema com IA (curso 1 de 6), INEMA Learning v7.2, PT/EN/ES. Público: quem fez o curso 0 ou já gera imagem; **sem terminal obrigatório** (a aula 7 usa ComfyUI, com janela). Toda versão de modelo aparece com "(out/2026)". Escrito em 19/10/2026, antes do conteúdo.

**Como se prova a prática (cursos 0–2):** toda prática gera um arquivo (escolha, ficha de prompt, lookbook, clipe, mapa de referências, roteiro multishot, ficha da máquina, lista de prompts) e quem confere é a **própria página** (seção `conferidor`). Texto: regras do JSON (motor 7.9.12+). **Clipe: modo vídeo do conferidor** (regra `video`, motor 7.12.15, feito em conjunto com o curso 2): o aluno escolhe o arquivo, o navegador lê duração, largura e altura sem enviar nada e responde `OK: 6,0 s · 1280×720 · 16:9`. O "pronto quando" cita a resposta literal. Ensaio sem custo = "Exemplo que passa"/"Exemplo com erro" (no vídeo, dois clipes WebM feitos com `ffmpeg` a partir de uma imagem estática, guardados em `assets/clipes/`). Opção para quem tem terminal: `python3 conferir.py <aula> arquivo` (vídeo pelo `ffprobe`). **Gerar o vídeo é do aluno**, com a ferramenta que tiver; o curso não gera vídeo nem gasta crédito.

**Exemplo que atravessa a formação:** "A primeira fornada" — Dona Lia (personagem fictícia, 58 anos) abre a padaria do bairro às 4h50. O storyboard de 30 s com 8 planos e a ficha da Dona Lia vêm prontos do curso 0 (aulas 6–8); aqui eles viram stills, clipes e a lista de prompts.

## As 8 aulas

| # | slug | título | objetivo (≤150) | diagrama | prática → "pronto quando" |
|---|---|---|---|---|---|
| 1 | geradores | O mapa dos geradores em out/2026 e como escolher | escolher o gerador de cada plano pelo que ele pede (duração, fala, referência, licença) e registrar a escolha com a data. | 5 perguntas de escolha → gerador; tabela datada como nós + bloco "geradores-out-2026.txt" | escolha.txt → `OK: escolha com 8 campos` (Sora só como estudo de caso, no texto) |
| 2 | prompt | Anatomia do prompt de vídeo: sujeito, ação, câmera, luz e som | escrever o prompt de um plano em sete partes, com o som em frase separada e o que evitar descrito sem "não". | sujeito → ação → cenário → câmera → luz → som → evitar | prompt.txt → `OK: prompt com 8 campos` |
| 3 | imagem-chave | Imagem-chave primeiro: still cinematográfico e lookbook | montar o lookbook da cena e gerar os stills dos planos-chave antes de qualquer vídeo, com o mesmo prompt-base. | decupagem → planos-chave → lookbook → still → aprovado = primeiro quadro | lookbook.txt → `OK: lookbook com 7 campos`; 3 stills na pasta |
| 4 | movimento | Da imagem ao movimento: imagem-para-vídeo e primeiro/último quadro | animar um still aprovado com um prompt só de movimento e conferir o clipe na página antes de seguir. | still → prompt de movimento → primeiro (e último) quadro → duração/som → clipe → conferência | clipe → `OK: [s] s · [w]×[h] · 16:9` (3–15 s, ≥ 1280 px) |
| 5 | referencia | Consistência por referência: personagem, objeto e estilo entre planos | ligar cada plano às imagens de referência e à trava de descrição que seguram o mesmo personagem e o mesmo look. | ficha → imagens de referência → trava de texto → look → último quadro herdado | referencias.txt → `OK: 6 planos com referência e trava` |
| 6 | multishot | Vários planos e falas numa geração: multishot e diálogo | escrever um roteiro multishot de até 15 s com planos numerados, quem fala o quê e o som de cada plano. | um pedido → planos numerados → fala com quem diz → som → limite de duração | multishot.txt → `OK: 4 planos numa geração · 12 s` |
| 7 | aberto | O caminho aberto: ComfyUI com LTX e Wan 2.2, VRAM e licença | decidir se a sua máquina roda vídeo aberto, escolher modelo e licença e registrar o template oficial que vai usar. | máquina (VRAM, disco) → modelo → licença → template oficial → clipe | maquina.txt → `OK: ficha da máquina com 7 campos` |
| 8 | lista-prompts | Seu gerador de prompts: do storyboard à lista de prompts com um agente | transformar o storyboard do curso 0 numa lista de prompts, um por plano, com um assistente de IA e conferir na página. | storyboard + ficha + look → agente com regras → lista → conferência; mapa + gerador | prompts.txt → `OK: 8 prompts prontos · 30 s` |

Cada aula: diagrama primeiro, passos curtos, blocos com copiar, conferidor (+ bloco opcional de terminal com saída real capturada), prática, teste de 4 perguntas comentadas, resumo, links. Aula 8 fecha com `mapa` + `gerador` e aponta para o curso 2 (`https://inematds.github.io/formacao-cinema-ia-producao-v72/`).

Donos de assunto (CURRICULO): este curso é dono de geradores, versões, prompt e ComfyUI/modelos abertos. Plano, ângulo, movimento, luz, ficha (o que é) e decupagem são do curso 0 (link, sem reexplicar). Som/voz/trilha/montagem/ética/rótulo são do curso 2 (link).

## Tabela de geradores (atualizada em 19/10/2026; só o que tem fonte)
Como o motor não tem tipo tabela, a aula 1 mostra cada gerador como nó do diagrama (detalhe com versão, data, duração, áudio, referência, aberto/fechado) e repete tudo num bloco copiável `geradores-out-2026.txt`.
- Veo 3.1 (Google): áudio nativo; até 3 imagens de referência ("Ingredients"); primeiro/último quadro; extensão de cena — developers.googleblog.com (~14/10/2025). Duração por clipe só em terceiros → "não confirmada".
- Kling 3.0 / 3.0 Omni (Kuaishou, fev/2026): até 15 s, áudio nativo multilíngue, diálogo com vários personagens (press release 05/02/2026); Omni com controle por plano de duração, ângulo e movimento (blog da Adobe, 15/04/2026). "Elements" e 6 cortes: relatado, não confirmado.
- Seedance 2.5 (ByteDance): até 30 s com áudio no mesmo passe; até 30 imagens, 10 vídeos e 10 áudios de referência (The Decoder, 01/08/2026).
- Runway Gen-4.5: áudio nativo, multishot, vídeos de até 1 min (TechCrunch, 11/12/2025); Aleph 2.0 edita vídeo existente (data relatada).
- Luma Ray3.14 (26/01/2026): 1080p nativo (Business Wire); Ray3 Modify com quadros inicial e final (TechCrunch, 18/12/2025).
- Wan 2.2 (Alibaba, jul/2025): último com pesos abertos, Apache 2.0; 2.6/2.7/3.0 fechados. Wan 2.2 5B cabe em 8 GB de VRAM com o offloading do ComfyUI (docs.comfy.org, consultado em 19/10/2026).
- LTX-2.3 e LTX-2.5 (Lightricks): pesos abertos sob LTX-2.x Community License (uso comercial sem custo abaixo de US$ 10 mi de receita anual; acima, licença paga); LTX-2.5 com multishot nativo e áudio (huggingface.co/Lightricks/LTX-2.5, consultado em 19/10/2026); a documentação do LTX para ComfyUI pede GPU com 32 GB+ de VRAM e 100 GB+ de disco.
- Sora 2: descontinuado (app 26/04/2026, API 24/09/2026) → estudo de caso de portabilidade, nunca opção.

## Novo / atualizado em relação aos cursos antigos (promptfilmes, seedance2, fpfilm1, skill mdd)
Conferido contra AUDITORIA-LOCAL.md e PESQUISA-ESTADO-DA-ARTE.md (19/10/2026) e, onde a pesquisa não cobria, contra fonte primária consultada em 19/10/2026.

- **Aula 1 — novo:** a "tabela de dialetos" do promptfilmes (Midjourney v7, Sora 2, Veo 3, Runway Gen-4, Kling 2.5) e o "Freepik abril/2026" do fpfilm1 saem; entra a tabela datada de out/2026 (Veo 3.1, Kling 3.0/Omni, Seedance 2.5, Runway Gen-4.5/Aleph 2.0, Luma Ray3.14, Wan 2.2, LTX-2.3/2.5), escolha por necessidade do plano, não por ranking. Sora como estudo de caso (portabilidade: prompts, referências e roteiro fora da plataforma).
- **Aula 2 — atualizado:** anatomia do promptfilmes 1.1 (sujeito/ação/ambiente, verbo vivo) + **som e fala dentro do prompt em frases separadas** e "evitar" descrito como substantivos, sem "não" (guia oficial de prompt de vídeo do Google, atualizado em 15/10/2026). Sai "diretores como atalho de estilo" (imita pessoa real) e o template de 3 beats com "frases literais medidas em 48 prompts" do seedance2 (estudo de produto de terceiro, preso ao Seedance 1.x).
- **Aula 3 — atualizado:** lookbook com 5 ingredientes (promptfilmes 2.4) **sem nome de diretor ou de filme**; still como "frame âncora" (fpfilm1 5.1) sem a regra "Flux→Mystic→Nano Banana" do Freepik. Geradores de imagem como exemplo datado: FLUX.2 [klein] (jan/2026; 4B Apache 2.0 e ~8 GB de VRAM, 9B não comercial — repositório oficial), Midjourney V8.1 (30/04/2026, documentação oficial); GPT Image 2 e Nano Banana Pro/2 só como "relatado por terceiros".
- **Aula 4 — novo:** imagem-para-vídeo e primeiro/último quadro com exemplos datados (Veo 3.1, Luma Ray3 Modify, template FLF2V do Wan 2.2 no ComfyUI, template primeiro/último quadro do LTX-2.5); "prompt só de movimento, sem redescrever" e "último quadro do plano anterior = primeiro do seguinte" (fpfilm1 4.4, sem o "Start Image" do Freepik como passo fixo). **Conferência do clipe na página** (modo vídeo, novo no motor).
- **Aula 5 — novo:** consistência como conceito (imagem de referência + trava de texto + look fixo + último quadro herdado), com exemplos datados: Ingredients do Veo 3.1 (3 imagens), Seedance 2.5 (30/10/10), multirreferência do FLUX.2 [klein] (caminho aberto para stills); "elements" do Kling como relatado. Sai a LoRA "Custom Character" do Freepik como único caminho.
- **Aula 6 — novo:** multishot e diálogo numa geração (Runway Gen-4.5, Kling 3.0/Omni, LTX-2.5 aberto); fala no formato "quem diz: texto" do guia do Google; limite de duração por exemplo datado (Kling 15 s, Seedance 30 s). Kling com 6 cortes ou 30 s: relatado, não ensinado como fato.
- **Aula 7 — novo:** caminho aberto com números de fonte oficial (Wan 2.2 5B ~8 GB com offloading; LTX 32 GB+ e 100 GB de disco), licença lida (Apache 2.0 × LTX-2.x Community × não comercial). **Desvio do CURRICULO:** "LTX-2.3" vira "LTX-2.3/2.5" porque a página oficial do Hugging Face (19/10/2026) mostra os pesos do LTX-2.5 publicados; a pesquisa marcava [incerto].
- **Aula 8 — atualizado:** o "app de prompts" do seedance2 (system prompt em 8 camadas, tool use, serverless, preso ao Seedance 2.0) vira um **pedido em camadas para o assistente de IA da sua assinatura** (papel, entrada, formato de saída, vocabulário, regras, limites), agnóstico de gerador, que lê o storyboard e a ficha do curso 0 e devolve uma linha por plano, conferida pela página. Sem nome de modelo de linguagem: "o modelo topo da sua assinatura".

## Deixado de fora (desatualizado, sem fonte ou [incerto])
- Sora como ferramenta (só estudo de caso); Seedance 2.0, Kling 2.5, Veo 3 sem ".1", Runway Gen-4, Midjourney v7 como "dialetos".
- Veo 4 (não anunciado), Hailuo H3, Grok Imagine 1.5, Gemini Omni Flash com specs, Kling 30 s/6 cortes, Seedance 720p, duração de 8 s do Veo: [incerto] → não entram como fato.
- Data de lançamento do LTX-2.5 e do Seedance 2.5 (fontes divergem): não citada.
- Ranking de geradores de imagem (Elo de arena, blogs de fornecedor): não entra.
- Nomes de diretores/filmes como atalho de estilo (promptfilmes 1.3, 2.4; seedance2 presets "Duna", "John Wick", "Blade Runner"): imitação de autor/obra real; trocado por ingredientes descritos.
- Tool use forçado, serverless, prompt caching, Google Sheets (seedance2 trilha 3): público sem terminal.
- "Lightroom", "Magnific upscale", créditos do Freepik como passo fixo; n8n.
- Exemplos com marca de terceiros (fast food "Burger King-style", carro 4x4 do fpfilm1): trocados por "A primeira fornada".
