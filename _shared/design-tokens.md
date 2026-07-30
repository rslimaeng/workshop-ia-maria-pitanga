# Design tokens · Workshop IA Maria Pitanga

Referência humana dos tokens usados nas páginas HTML. Cada página replica esses tokens no `<style>` inline (mantém single-file portable).

## Cores

```css
/* Fundo e superfícies */
--bg:            #F0EEE6;   /* creme Claude — fundo principal */
--bg-elev:       #FFFFFF;   /* elevação (cards) */
--bg-warm:       #E8E6DC;   /* creme mais escuro (chips, código sutil) */
--bg-code:       #F5F3EA;   /* fundo de bloco de código */

/* Texto */
--text:          #141413;   /* corpo principal */
--text-muted:    #3D3D3A;   /* secundário */
--text-dim:      #87867F;   /* metadados, labels */

/* Bordas */
--border:        rgba(20,20,19,.10);
--border-strong: rgba(20,20,19,.18);

/* Accent — roxo Açaí Maria Pitanga */
--accent:        #6B2E7A;   /* accent principal */
--accent-dark:   #4A1F55;   /* hover */
--accent-soft:   #F0E3EF;   /* fundo tingido pra callout accent */
--accent-line:   rgba(107,46,122,.20);

/* Semânticas */
--success:       #2E7D32;
--success-soft:  #F5F9F5;   /* fundo tingido verde bem sutil */
--warning:       #B8860B;
--warning-soft:  #FCF7E8;   /* fundo tingido âmbar sutil */
--danger:        #B85C5C;
--danger-soft:   #FBF5F5;   /* fundo tingido rosé sutil */
```

## Tipografia

```css
--font-body: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
--font-mono: 'JetBrains Mono', ui-monospace, 'SF Mono', 'Menlo', monospace;
```

Fontes carregadas via Google Fonts CDN:
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
```

## Radius e sombras

```css
--radius-sm: 6px;
--radius:    10px;
--radius-lg: 14px;

--shadow-sm: 0 1px 2px rgba(20,20,19,.04), 0 1px 3px rgba(20,20,19,.06);
--shadow-md: 0 4px 12px rgba(20,20,19,.06), 0 2px 4px rgba(20,20,19,.04);
```

## Regras de estilo (aprendidas no M1)

- **Nunca** border-left grossa colorida em card/callout. Preferir fundo tingido derivado da cor semântica + dot colorido pequeno via `::before` no título/label
- Emoji só em callout curto pontual, nunca em card decorativo
- Header sticky com `backdrop-filter: blur(10px)` sobre `rgba(240,238,230,.92)`
- Nav lateral sticky à esquerda em desktop (>=900px), vira topo em mobile
- Scroll-spy JS puro por `pageYOffset` (não IntersectionObserver — mais previsível)
- localStorage sempre com prefixo `mp-` (evita colisão com outros sites)
- Grid responsivo: colapsa em `900px` (nav vira topo) e `720px` (2 colunas viram 1)

## Componentes prontos (M1)

| Classe | Uso | Onde ver |
|---|---|---|
| `.card` | Card base branco com border | Blocos genéricos |
| `.card-accent` | Card com fundo `#FBF7FB` (roxo bem tingido) | Destaques accent |
| `.card-highlight` | Card com fundo `--accent` e texto branco | Destaque forte (poucos) |
| `.callout` + `.callout-info` / `.callout-warn` | Bloco com título uppercase mono + dot colorido | Aviso/regra |
| `.table-wrap` | Wrapper com overflow-x pra tabela responsiva | Qualquer tabela |
| `.matriz` | Grid 2×2 responsiva (Impacto × Rotina) | M1 seção 4 |
| `.compare` | 2 colunas lado a lado (vago × situado) | M1 seção 5 |
| `.prompt-box` | Bloco de código monoespaçado com scroll | Prompt exemplo |
| `.gen` | Gerador PCTFL+ com localStorage + preview ao vivo | M1 seção 9 |
| `.chip` | Pílula pequena com texto curto | Header, meta |
| Header sticky | `.site-header` + `.brand` + `.chip` | Todas as páginas |
| Nav lateral | `.side-nav` com scroll-spy | Módulos longos |

Fonte da verdade: `m1/index.html` (copiar e adaptar).
