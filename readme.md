# 🔥 phoenixsrd — Portfólio pessoal

Portfólio pessoal de **phoenixsrd**, desenvolvido para apresentar projetos, tecnologias e experimentos voltados a automação, ferramentas web, streaming, segurança e utilitários open source.

🌐 **Acesse online:** [phoenixsrd.vercel.app](https://phoenixsrd.vercel.app/)

## O que você encontra aqui

- Apresentação profissional e área de contato.
- Stack organizada por linguagens, bibliotecas, plataformas e serviços.
- Cards dos repositórios públicos carregados diretamente pela API do GitHub.
- Filtros de projetos por linguagem, estatísticas de repositórios, stars e forks.
- Links para os projetos e para eventuais versões publicadas em produção.
- Gráfico de contribuições do GitHub.
- Interface responsiva, com navegação mobile, animações e suporte a `prefers-reduced-motion`.

## Como funciona

Este é um site estático composto por `index.html`, `sw.js` e `manifest.json`. O JavaScript embutido no `index.html` consulta o perfil e os repositórios públicos de `phoenixsrd` usando a API do GitHub, monta as seções da página e aplica os filtros sem necessidade de backend próprio.

O `sw.js` transforma o portfólio em uma PWA simples: arquivos do mesmo domínio usam cache-first, enquanto a API do GitHub e os CDNs permanecem em modo network-only para preservar dados atualizados.

## Estrutura

```text
index.html      # Página completa, estilos, conteúdo e integração com a API do GitHub
manifest.json   # Metadados da aplicação instalável
sw.js           # Service worker e cache dos arquivos estáticos
readme.md       # Documentação do projeto
```

## Rodar localmente

Como não há etapa de build, basta servir os arquivos por HTTP — isso também permite testar corretamente o service worker:

```bash
git clone https://github.com/phoenixsrd/phoenixsrd.git
cd phoenixsrd
python3 -m http.server 8080
```

Abra `http://localhost:8080` no navegador. Também é possível abrir o `index.html` diretamente, mas recursos como o service worker exigem um contexto HTTP/HTTPS.

## Personalização

As informações estáticas ficam no objeto `CONFIG` dentro do `index.html`. Ali podem ser alterados textos, destaques, stack, interesses e contatos. O objeto `DESCRIPTIONS` permite substituir a descrição recebida do GitHub para projetos específicos.

> As consultas usam a API pública do GitHub e estão sujeitas ao limite de requisições por IP. Este repositório apresenta o portfólio; cada ferramenta tem sua própria documentação e forma de execução.

⭐ Se este trabalho foi útil ou interessante, considere deixar uma estrela.