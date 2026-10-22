# delegacao.md — papéis e contrato

Papéis: **orquestrador** (decide, divide, revisa, integra, fala com o humano), **raciocínio pesado** (análise profunda e revisão adversarial), **executor** (implementa um artefato), **simples** (busca, triagem, extração).

## Despacho
```
DESPACHO <id>
dono: <um subagente>   modelo/esforço: <x>   ferramentas: <lista mínima>
objetivo: <1 frase>
artefato: <1 caminho de saída>   (nada fora dele)
escopo: repo/branch/commit, arquivos permitidos; fora do escopo = NÃO VERIFICADO
prova: <comando ou critério que o orquestrador vai rodar ou ler>
proibido: segredos, credentials/, push, e-mail, deploy, apagar
gate humano: <o que volta ao humano antes de seguir>
orçamento: <tempo e tokens máximos>
entrega: resumo curto + evidência (saída de comando, arquivo:linha)
```

## Handoff estruturado (retorno)
```
HANDOFF <id>
feito: <o que mudou, com caminhos>
prova: <saída de comando / arquivo:linha>
não feito / bloqueado: <motivo>
riscos e NÃO VERIFICADO: <lista>
próximo passo: <1 linha>
```

## Regras do orquestrador
1. Lê e confere toda saída contra a prova. 2. Não repassa segredo nem dado de cliente a quem não precisa. 3. Executores não têm ferramenta de envio, push, deploy ou pagamento. 4. Em C, revisor adversarial com contexto limpo e modelo diferente do executor. 5. Um dono por arquivo, profundidade 1. 6. Registra no log. 7. Dúvida de classe vira C.

## Quando delegar
Delegar: amplitude, lote repetitivo, revisão independente (sempre em C), exploração que polui contexto, trabalho paralelo com donos distintos. Inline: classe S, um arquivo, decisão, redação final de domínio, qualquer coisa que dependa do contexto da conversa.
