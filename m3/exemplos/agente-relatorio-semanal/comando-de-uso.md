# Comando de uso · Agente Relatório Semanal MP

> Depois que o agente está montado (system prompt + contexto colados), o gerente
> só precisa deste comando curto pra rodar. Ele copia, cola junto com o excel,
> e o agente devolve o relatório.

---

## Comando padrão (semana normal)

```
Segue o excel de fechamento da semana. Gera o relatório.
```

Sim, é isso. **Uma frase.** O agente já sabe o papel, já conhece o modelo do
relatório. Não precisa repetir nada.

---

## Variações úteis

### Se quiser recorte específico
```
Segue o excel. Foca a análise na semana 3 (20/07 a 26/07).
```

### Se quiser comparar com semana anterior manualmente
```
Segue o excel. A semana atual é a S3. Compare tudo contra a S2.
```

### Se quiser destacar um ângulo
```
Segue o excel da semana. Quero atenção especial no comportamento do
Cupuaçu Sertanejo — ele acabou de entrar na loja.
```

### Se quiser um formato diferente da entrega padrão
```
Segue o excel. Em vez de HTML, entrega só o resumo em markdown pra eu
copiar no e-mail da segunda de manhã.
```

---

## O que NÃO precisa dizer

O agente já sabe:
- Que ele é Head de Operações da rede
- Que precisa comparar semanas
- Que tem que citar produto pelo nome exato
- Que precisa terminar com 3 recomendações específicas
- Que entrega em HTML

**Se você tá repetindo isso no comando, o agente tá mal configurado** — arruma
o system prompt uma vez e nunca mais precisa dizer.

---

## Como levar o excel pro agente

- **Claude Projects (pago):** botão de anexo no chat → seleciona o `.xlsx`
- **Custom GPT (pago):** mesmo caminho, anexa no chat
- **Chat gratuito:** cola o conteúdo relevante da aba `resumo-semanal` como tabela
  no próprio chat (a aba `vendas` tem 3 mil linhas — não cola inteira, deixa o
  agente trabalhar com o resumo)
