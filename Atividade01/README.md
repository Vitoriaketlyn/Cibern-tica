# Demonstrativo de Vulnerabilidades e Proteções em PHP

Este repositório apresenta dois exemplos simples em PHP com foco na segurança de aplicações web, abordando ataques comuns como **SQL Injection** e **força bruta em login**.

## 📘 Descrição dos Arquivos

- `inseguro.php`: Script sem medidas de segurança, suscetível a manipulação de consultas SQL e tentativas ilimitadas de acesso.
- `seguro.php`: Código aprimorado com práticas recomendadas de segurança:
  - Implementação de consultas preparadas com `PDO`.
  - Controle de acesso baseado em contagem de tentativas armazenadas na sessão.
  - Validação de senha utilizando `password_verify()`.

## 🔍 Comparativo de Segurança

| Risco de Segurança       | Solução Adotada                                |
|--------------------------|------------------------------------------------|
| Injeção de comandos SQL  | Uso de `prepare()` e `bindParam()`             |
| Login automatizado       | Limitação por sessão (`$_SESSION`)             |
| Senhas não protegidas    | Hash com `password_hash()` e verificação segura |

## ✅ Recomendações

Para proteger as senhas dos usuários, utilize sempre hashing seguro:

```php
$hash = password_hash($senha, PASSWORD_DEFAULT);
