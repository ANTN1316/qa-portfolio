# BUG-002 - Sessão não é mantida após reabertura do aplicativo

## Resumo

Após autenticação bem-sucedida, o sistema não mantém a sessão do usuário ao fechar e reabrir o aplicativo, exigindo novo login mesmo sem ocorrência de logout ou expiração aparente da sessão.

## Caso de teste relacionado

LOGIN-SES-007

## Categoria

Sessão / Autenticação

## Severidade

Alta

## Prioridade

Alta

## Ambiente

* Android 13
* App versão 1.0.0

## Pré-condições

* Usuário cadastrado no sistema
* Login realizado com sucesso
* Conexão ativa com a internet

## Passos para reproduzir

1. Realizar login com credenciais válidas
2. Confirmar acesso à tela Home
3. Fechar completamente o aplicativo
4. Reabrir o aplicativo

## Resultado esperado

* Usuário deve permanecer autenticado
* Sessão deve ser recuperada por meio de token válido armazenado localmente
* Aplicativo deve abrir diretamente na tela Home
* Não deve ser necessário informar credenciais novamente

## Resultado obtido

* Após reabrir o aplicativo, o usuário foi redirecionado para a tela de login
* Sessão anterior não foi recuperada
* Usuário precisou informar credenciais novamente
* Nenhuma mensagem de expiração de sessão foi apresentada

## Impacto

A funcionalidade de persistência de sessão não opera conforme esperado, gerando atrito na experiência do usuário e aumento desnecessário de autenticações.

## Evidências

Adicionar screenshots ou vídeo demonstrando:

* Login realizado com sucesso
* Fechamento do aplicativo
* Reabertura direcionando para tela de login

## Status

Aberto

