---
name: registradores_info_conta-mcp
description: Skill da REST API do Registradores (ARISP): Consulta de Informações da Conta na MCP.AI: 1 endpoint em /api/registradores_info_conta. Registradores (ARISP): Consulta de Informações da Conta, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Registradores (ARISP): Consulta de Informações da Conta — REST API skill

Você tem acesso à **Registradores (ARISP): Consulta de Informações da Conta** REST API na MCP.AI.

> Registradores (ARISP): Consulta de Informações da Conta, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/registradores_info_conta
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/registradores_info_conta/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/registradores_info_conta/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `registradores_info_conta_consultar`

Registradores (ARISP): Consulta de Informações da Conta, consulta em fonte oficial. _(POST /api/registradores_info_conta/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `email` | string | Não | Parâmetro de consulta "email". |
| `senha` | string | Não | Parâmetro de consulta "senha". |
| `pkcs12_cert` | string | Não | Parâmetro de consulta "pkcs12_cert". |
| `pkcs12_pass` | string | Não | Parâmetro de consulta "pkcs12_pass". |
| `tipo_login` | string | Não | Parâmetro de consulta "tipo_login". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_registradores_info_conta` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
