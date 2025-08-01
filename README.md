# 👋 Desafio Técnico - LAE Cartórios

Seja bem-vindo ao **Desafio Técnico da LAE Cartórios** para a vaga de **Desenvolvedor Fullstack Júnior**.

O objetivo deste desafio é avaliar seu conhecimento técnico, sua organização e a forma como você lida com diferentes tipos de problemas em um tempo reduzido. O desafio pode parecer complexo à primeira vista, mas fique tranquilo: tudo foi pensado para que um desenvolvedor júnior consiga implementar após compreender bem as tarefas.

Ao final deste documento, deixei alguns **links úteis** que vão te ajudar a navegar pelo desafio com mais tranquilidade.

---

## 🚧 Estrutura do Desafio

O desafio é dividido em duas partes: **backend** e **frontend**.
Mas, por enquanto, vamos focar **apenas no backend**, certo?

---

## 🔍 Desafio

> Desenvolva uma API utilizando **Bun + Fastify + PostgreSQL**, que receba um arquivo PDF, imagem JPEG ou PNG de uma conta comum (ex: água, energia, internet) e utilize **IA (Inteligência Artificial)** para extrair automaticamente os principais campos do documento.
>
> As informações extraídas devem ser **salvas no banco PostgreSQL**.

---

### 📦 O projeto deve rodar com Docker

Você deve entregar:
- Um `Dockerfile` configurando a aplicação
- Um `docker-compose.yml` com:
  - O serviço da aplicação rodando com Bun
  - O banco de dados PostgreSQL
  - Variáveis de ambiente corretamente definidas
- Um README com instruções claras de como subir o projeto com `docker compose up`

---

### 📚 O que você precisará saber:

```
- Bun
- Fastify
- PostgreSQL
- Integração com IA (LLM)
- Docker e Docker Compose
```

**Dica:**
Recomendamos usar a **API do Gemini**, que é gratuita e possui uma ótima documentação.
Mas sinta-se livre para usar o modelo de IA de sua preferência, como o **GPT-3.5** ou **GPT-4 da OpenAI**.

---

## 📌 Endpoints esperados

### `POST /bills`
Recebe o arquivo (PDF ou imagem em base64) e retorna os dados extraídos:

```json
{
  "file": "base64string"
}
```

### `GET /bills`
Retorna todos os registros salvos:

```json
[
  {
    "id": "uuid",
    "nome_cliente": "João da Silva",
    "vencimento": "2025-08-01",
    "valor": 143.76,
    "tipo": "AGUA",
    "descricao": "Fatura referente ao mês 06/2025"
  }
]
```

### `GET /bills/:id`
Retorna um único registro:

```json
{
  "id": "uuid",
  "nome_cliente": "João da Silva",
  "vencimento": "2025-08-01",
  "valor": 143.76,
  "tipo": "AGUA",
  "descricao": "Fatura referente ao mês 06/2025"
}
```

### `DELETE /bills/:id`
Remove o registro informado.

---

## 🧱 Organização sugerida

Queremos avaliar sua familiaridade com **Clean Code** e os princípios **SOLID**, então sugerimos a seguinte estrutura de projeto:

```
src/
├── application/
│   └── usecases/
├── domain/
│   └── entities/
├── infra/
│   ├── http/
│   ├── controllers/
│   ├── routes/
│   ├── database/
│   └── ia/
├── main.ts
```

Você pode adaptar ou usar sua própria estrutura, desde que mantenha uma separação clara entre as camadas da aplicação.

---

## 📝 Observações importantes

- Na LAE, seguimos o padrão de **conventional commits**. Se você usar esse padrão nos seus commits, será um **diferencial positivo**.
- **Testes automatizados** não são obrigatórios, mas sua presença também conta como diferencial.
- O Bun possui suporte nativo ao PostgreSQL — você pode usar a dependência oficial sem bibliotecas externas adicionais.
- É **obrigatório** que o projeto esteja totalmente rodando via Docker e com instruções claras no `README`.

---

## 🔗 Links úteis

### 🧠 Tecnologias

- [Bun](https://bun.sh)
- [Fastify](https://fastify.dev)
- [PostgreSQL (Documentação oficial)](https://www.postgresql.org/docs/)
- [Gemini – Criar chave de API](https://ai.google.dev)
- [Gemini – Documentação](https://ai.google.dev/gemini-api/docs)

### 📦 Docker

- [Docker (Instalação e Introdução)](https://docs.docker.com/get-docker/)
- [Docker Compose (Visão geral)](https://docs.docker.com/compose/)
- [Guia prático: Dockerfile](https://docs.docker.com/engine/reference/builder/)
- [Guia prático: docker-compose.yml](https://docs.docker.com/compose/compose-file/)

### 💡 Boas práticas

- [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)
- [Resumo: Clean Code e SOLID](https://www.linkedin.com/pulse/resumindo-clean-code-architecture-e-solid-bernardo-rodrigues/)

---

## 🤖 Sobre o uso de IA

Por favor, **não use IA para resolver o desafio por completo**. Isso não é justo com os demais candidatos e... sim, eu vou perceber 😂

Claro, o uso moderado de IA **como apoio** é permitido — especialmente para documentação, correção de erros ou sugestões. Mas o desafio deve refletir **o seu próprio raciocínio e organização**.

---

## ⚠️ **Atenção:**

> Você tem até a **segunda-feira, às 23:59**, para enviar sua solução.

Se tiver qualquer dúvida, sinta-se à vontade para entrar em contato. Boa sorte! 🚀
