# Luz para Cada Dia — página de vendas

Página de vendas estática (HTML + CSS, sem build) do produto **Luz para Cada Dia**:
365 cards bíblicos de leitura diária para imprimir.

## Estrutura

| Arquivo | Função |
|---|---|
| `index.html` | A página inteira — HTML, CSS e JS inline, sem dependências externas |
| `Dockerfile` | Imagem nginx alpine servindo o HTML na porta 80 |
| `nginx.conf` | Gzip, headers de segurança, cache de 5 min e rota `/health` |

## Rodar local

```bash
docker build -t luz-para-cada-dia .
docker run --rm -p 8080:80 luz-para-cada-dia
# http://localhost:8080
```

Sem Docker, basta abrir `index.html` no navegador.

## Deploy (EasyPanel)

App do tipo **App** com origem GitHub e build por **Dockerfile**.
Porta interna: `80`. Sem variáveis de ambiente.

## Antes de anunciar — pendências

- [ ] Trocar `href="#"` dos botões com `data-checkout` pelo link real do checkout (2 ocorrências)
- [ ] Ajustar ou remover o contador de lote (`.lot`) em `#ofertas`
- [ ] Substituir as estrelas do hero por avaliações reais, ou remover o bloco `.rating`
- [ ] Atualizar `canonical` e `og:url` para o domínio final
- [ ] Instalar o pixel do Meta / Google Ads antes de subir tráfego
