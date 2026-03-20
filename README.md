# Deck de Estudo Interativo

Aplicacao web em ficheiro unico para estudo ativo com cartoes de pergunta/resposta, modo de revisao e retoma automatica de progresso.

## Visao geral

Este projeto foi pensado para estudo rapido e focado:

- Deck principal com 50 questoes sobre Psicologia na Transicao Digital.
- Deck de revisao personalizado com as perguntas que o aluno marca como mais dificeis.
- Persistencia local automatica com `localStorage`.
- Interface otimizada para leitura em desktop (incluindo 1080p) e responsiva para mobile.

## Funcionalidades principais

- Inicio com duas opcoes claras:
  - `Comecar a Estudar` (inicia sempre na pergunta 1).
  - `Continuar onde fiquei` (retoma o ponto guardado).
- Modo de revisao dedicado.
- Botao de ecra inteiro com estado visual.
- Botao para fechar sessao de estudo com ecra de despedida.
- Notificacoes visuais (toast) para feedback imediato.

## Como executar

1. Abrir o ficheiro [`deck-estudo-ptd.html`](./deck-estudo-ptd.html) num navegador moderno.
2. Escolher no menu inicial:
   - `Comecar a Estudar`, ou
   - `Continuar onde fiquei`.
3. Navegar pelas perguntas e marcar as que quer rever.
4. Alternar para o modo de revisao quando quiser consolidar as perguntas guardadas.

## Atalhos de teclado

| Tecla | Acao |
|---|---|
| `->` (Seta Direita) | Proxima pergunta |
| `<-` (Seta Esquerda) | Pergunta anterior |
| `+` | Adicionar pergunta ao deck de revisao |
| `-` | Remover pergunta do deck de revisao |
| `R` | Alternar entre deck principal e modo de revisao |
| `F` | Entrar/sair de ecra inteiro |
| `?` | Abrir instrucoes/ajuda |

## Regras de progresso

- O app guarda automaticamente:
  - perguntas marcadas para revisao;
  - pergunta atual;
  - modo atual (principal ou revisao).
- Se escolher `Continuar onde fiquei`, retoma exatamente o ponto guardado.
- Se escolher `Comecar a Estudar`, inicia do zero (pergunta 1).
- Se o deck de revisao ficar vazio, o app volta para a pergunta do deck principal onde o aluno estava antes de entrar em revisao.

## Persistencia local

As chaves usadas no `localStorage` sao:

- `psicologiaReviewDeck`
- `psicologiaProgressoSessao`

Notas importantes:

- Os dados sao guardados por navegador/perfil/dispositivo.
- Limpar dados do site ou usar modo privado/incognito pode apagar o progresso.

## Estrutura do projeto

```text
Deck-Estudo/
  deck-estudo-ptd.html   # Aplicacao completa (HTML + CSS + JavaScript + banco de questoes)
  README.md              # Documentacao do projeto
```

## Personalizacao

- Conteudo: editar o array `BANK` dentro de `deck-estudo-ptd.html`.
- Estilo: ajustar o bloco `<style>` para tipografia, espacamento e cores.
- Textos da interface: atualizar labels, titulos e subtitulos no HTML.

## Compatibilidade

Recomendado usar versoes recentes de Chrome, Edge ou Firefox com suporte a:

- `localStorage`
- Fullscreen API

## Resolucao de problemas

**O botao "Continuar onde fiquei" esta desativado**
- Ainda nao existe progresso guardado neste navegador/perfil.

**O ecra inteiro nao abre automaticamente**
- Alguns navegadores bloqueiam fullscreen sem gesto adicional; use o botao no topo ou a tecla `F`.

**A tecla `?` nao abre a ajuda**
- Em alguns teclados, `?` exige `Shift`; use a combinacao equivalente do teu layout.
- Alternativa: clique no botao `?` no topo.

**Perdi o progresso**
- Verifique se nao esta em modo privado/incognito e se os dados do site nao foram limpos.

---

Se quiseres, posso criar tambem:

1. Uma versao em ingles do README.
2. Uma secao de deploy para GitHub Pages.
3. Um changelog inicial (`CHANGELOG.md`) com as melhorias ja feitas.
