# BUG-004 - Sistema rejeita OTP válido durante autenticação

## Resumo

O sistema rejeita códigos OTP válidos recebidos por SMS, impedindo a autenticação do usuário mesmo quando o código informado corresponde ao código enviado pelo sistema.

## Caso de teste relacionado

LOGIN-OTP-010

## Categoria

Autenticação / OTP

## Severidade

Crítica

## Prioridade

Alta

## Ambiente

* Android 13
* App versão 1.0.0

## Pré-condições

* Aplicativo instalado e atualizado
* Conexão ativa com a internet
* Número de telefone válido
* Serviço de envio de SMS operacional

## Passos para reproduzir

1. Abrir o aplicativo
2. Selecionar a opção "Entrar com SMS"
3. Informar um número de telefone válido
4. Solicitar envio do OTP
5. Aguardar recebimento do SMS
6. Inserir o código recebido
7. Confirmar autenticação

## Resultado esperado

* Sistema deve validar o código OTP recebido
* Usuário deve ser autenticado com sucesso
* Aplicativo deve redirecionar para a tela Home
* Sessão deve ser iniciada normalmente

## Resultado obtido

* SMS foi recebido corretamente
* Código informado correspondia ao código recebido
* Sistema exibiu a mensagem:

"Código inválido ou expirado"

* Nova tentativa utilizando o mesmo código apresentou o mesmo erro
* Novo OTP foi solicitado
* Novo código também foi rejeitado
* Usuário não conseguiu concluir a autenticação

## Impacto

A funcionalidade de login por OTP torna-se inutilizável.

Usuários que dependem desse método de autenticação não conseguem acessar suas contas.

O defeito impacta diretamente a taxa de login, experiência do usuário e conversão de acesso à plataforma.

## Evidências

Adicionar:

* Screenshot do SMS recebido
* Screenshot da mensagem de erro
* Vídeo completo da reprodução do problema
* Logs de validação do OTP (caso disponíveis)

## Status

Aberto

