# Relatório de Bug - Cadastro de Entregadores

## Título
Sistema permite cadastro de entregadores com CPF inválido

## Descrição
Ao tentar cadastrar um entregador com CPF inválido, o sistema permite a conclusão do cadastro sem exibir qualquer mensagem de erro, contrariando as regras de negócio definidas.

## Passos para reproduzir
1. Acessar a página de cadastro de entregadores
2. Preencher todos os campos com dados válidos, exceto o CPF (usar por exemplo: 123.456.789-00)
3. Clicar em "Enviar"
4. Observar que o sistema cadastra o entregador mesmo com o CPF inválido

## Resultado esperado
O sistema deve validar o CPF antes de permitir o cadastro. Caso o CPF seja inválido, deve exibir uma mensagem de erro clara e impedir o envio.

## Resultado atual
O cadastro é realizado normalmente, sem bloqueio ou alerta.

## Prioridade
Alta

## Impactos
- Permite cadastro de dados inválidos no sistema
- Pode causar falhas na emissão de notas fiscais
- Afeta a credibilidade do sistema e a integridade da base de dados
- Pode comprometer integrações futuras com serviços externos

## Anexos
Prints e/ou vídeos do processo estão em anexo no cartão.

# Ações após reportar o bug

Após criar o cartão no JIRA com as evidências do problema (prints e vídeos), minhas ações seriam:

1. **Mencionar diretamente o desenvolvedor responsável** (Bruno) no próprio cartão do JIRA, utilizando @Bruno para notificá-lo automaticamente. Dessa forma, centralizamos a comunicação e aproveitamos as funcionalidades de automação e histórico da plataforma.

2. **Adicionar um comentário direcionado** no cartão, explicando o impacto do bug e sugerindo prioridade de correção, com base nas regras de negócio. Exemplo:  
   *"@Bruno, identifiquei que a validação de CPF está permitindo valores inválidos. Isso pode impactar a emissão de notas fiscais. Poderia verificar a lógica de validação no back-end?"*

3. **Alterar o status do cartão para "To Do" ou "Aguardando Dev"**, conforme o fluxo do time, para indicar que precisa ser tratado.

4. **Notificar a gerente de projeto (Carol)** também pelo JIRA, mencionando-a no comentário ou adicionando como "watcher" do cartão, para que ela acompanhe e possa reavaliar as prioridades do projeto, caso necessário.

5. **Após a correção feita por Bruno**, realizaria os testes de regressão necessários e **atualizaria o status do cartão**, além de registrar os resultados da validação com um comentário final, mantendo a rastreabilidade.

6. Se o bug exigir ajuste no plano de testes ou impactar outras áreas, também comunicaria o time de QA para alinhamento interno.

Observação: como o bug está relacionado à validação de CPF, ele foi atribuído diretamente ao Bruno, responsável pelo back-end. Caso o problema estivesse relacionado à interface (ex: ausência de máscara no campo de CPF ou botão sendo habilitado de forma incorreta), a desenvolvedora front-end, Ana, também seria envolvida.
Acredito que usar o JIRA de forma colaborativa e estruturada é essencial para que QA, desenvolvimento e gestão trabalhem de forma sincronizada e produtiva.
