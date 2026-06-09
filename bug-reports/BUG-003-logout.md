# BUG-003 - Logout não invalida completamente a sessão do usuário

## Resumo

Após realizar logout, o sistema redireciona o usuário para a tela de login, porém ainda permite acesso a áreas protegidas através de navegação interna ou utilização do botão "voltar", indicando que a sessão permanece válida.

## Caso de teste relacionado

LOGIN-SES-008

## Categoria

Sessão / Segurança / Autenticação

## Severidade

Crítica

## Prioridade

Alta

## Ambiente

* Android 13
* App versão 1.0.0

## Pré-condições

* Usuário autenticado no aplicativo
* Sessão ativa

## Passos para reproduzir

1. Realizar login com credenciais válidas
2. Acessar uma área protegida do aplicativo (Perfil, Pedidos ou Conta)
3. Executar a ação de logout
4. Confirmar o redirecionamento para a tela de login
5. Utilizar o botão "voltar" do dispositivo ou acessar diretamente uma área protegida

## Resultado esperado

* Sessão deve ser encerrada completamente
* Token de autenticação deve ser invalidado
* Áreas protegidas devem exigir nova autenticação
* Botão "voltar" não deve permitir acesso a conteúdo autenticado
* Usuário deve permanecer deslogado até realizar novo login

## Resultado obtido

* Sistema redirecionou corretamente para a tela de login
* Ao utilizar o botão "voltar" ou navegar para áreas protegidas, o acesso foi permitido sem nova autenticação
* Sessão aparentemente permaneceu ativa em segundo plano
* Token de autenticação não foi invalidado corretamente

## Impacto

Falha de segurança que permite acesso não autorizado a áreas protegidas após o encerramento da sessão.

Usuários que compartilham dispositivos ou utilizam equipamentos públicos podem ter suas informações expostas mesmo após realizar logout.

## Evidências

Adicionar:

* Capturas de tela da navegação após logout
* Vídeo demonstrando o acesso indevido
* Logs da sessão (se disponíveis)

## Status

Aberto

