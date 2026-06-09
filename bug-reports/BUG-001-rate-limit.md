# BUG-001 - Ausência de proteção contra força bruta no login

## Resumo

O sistema permite múltiplas tentativas consecutivas de autenticação com credenciais inválidas sem aplicar qualquer mecanismo de proteção contra ataques de força bruta.

## Caso de teste relacionado

LOGIN-SEC-006

## Categoria

Segurança

## Severidade

Alta

## Prioridade

Alta

## Ambiente

* Android 13
* App versão 1.0.0

## Pré-condições

* Usuário cadastrado no sistema
* Tela de login disponível
* Conexão ativa com a internet

## Passos para reproduzir

1. Acessar a tela de login
2. Informar um e-mail válido
3. Informar uma senha incorreta
4. Repetir o processo 5 vezes consecutivas
5. Realizar uma 6ª tentativa

## Resultado esperado

Após múltiplas tentativas inválidas, o sistema deve aplicar proteção contra força bruta, como:

* Bloqueio temporário
* CAPTCHA
* Atraso progressivo entre tentativas
* Limitação de requisições

## Resultado obtido

O sistema continuou processando todas as tentativas normalmente.

Nenhum mecanismo de proteção foi ativado.

A 6ª tentativa foi executada sem qualquer restrição.

## Impacto

Um invasor pode realizar um grande número de tentativas de autenticação, aumentando o risco de ataques de força bruta e comprometimento de contas.

## Evidências

Adicionar screenshots ou gravações da execução do teste.

## Status

Aberto

