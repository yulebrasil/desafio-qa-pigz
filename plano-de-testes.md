# Plano de Testes - Desafio QA Pigz

## Introdução

Este plano de testes foi elaborado com base na descrição das funcionalidades fornecida no desafio. Como ainda não tive acesso ao sistema real, baseei a estrutura em fluxos típicos de sistemas de cadastro, levando em conta minha vivência anterior com QA e com equipes de desenvolvimento. Busquei pensar como um usuário final e também como alguém preocupado com a integridade dos dados do sistema.

O objetivo é cobrir tanto os **cenários felizes** (em que tudo ocorre como o esperado) quanto os **cenários de exceção**, que podem gerar erros ou inconsistências se não forem bem tratados.

---

## Funcionalidade 1 - Cadastro de Restaurantes

| Cenário                                     | Passos                                                                                  | Resultado Esperado                                             |
|--------------------------------------------|------------------------------------------------------------------------------------------|----------------------------------------------------------------|
| Cadastro com dados válidos                 | Preencher todos os campos obrigatórios com dados corretos e clicar em "Salvar"          | Restaurante cadastrado com sucesso e redirecionamento à lista |
| CNPJ inválido                              | Informar um CNPJ inválido e tentar salvar                                               | Mensagem de erro informando CNPJ inválido                     |
| CNPJ duplicado                             | Tentar cadastrar restaurante com CNPJ já existente no sistema                           | Sistema exibe erro de CNPJ duplicado                          |
| Campo obrigatório vazio                    | Deixar um ou mais campos obrigatórios em branco (ex: telefone, endereço) e salvar       | Sistema impede cadastro e informa quais campos faltam         |
| Formato incorreto no telefone              | Inserir telefone fora do padrão e tentar salvar                                         | Sistema exibe erro ou impede o cadastro                       |

📝 *Observação:* vale verificar se o botão “Salvar” só está habilitado após todos os campos obrigatórios estarem preenchidos corretamente. Essa pequena lógica evita erros de fluxo.

---

## Funcionalidade 2 - Cadastro de Cardápios

| Cenário                                     | Passos                                                                                  | Resultado Esperado                                             |
|--------------------------------------------|------------------------------------------------------------------------------------------|----------------------------------------------------------------|
| Cadastro completo e válido                 | Selecionar restaurante, preencher nome, descrição e itens válidos, e clicar em "Salvar" | Cardápio salvo com sucesso e redirecionamento à lista         |
| Nome do cardápio ausente                   | Tentar salvar sem preencher o nome do cardápio                                          | Sistema bloqueia o cadastro e exibe mensagem de erro          |
| Nome duplicado no mesmo restaurante        | Cadastrar dois cardápios com o mesmo nome no mesmo restaurante                         | Sistema exibe mensagem de erro de duplicidade                 |
| Item sem nome ou preço inválido            | Adicionar item sem nome ou com texto no campo de preço (ex: “dez reais”)               | Cadastro bloqueado e mensagens de erro exibidas               |
| Campo de preço com número negativo         | Inserir preço como -5 ou 0 em um item.                                               | Sistema bloqueia ou avisa sobre valor inválido                |
| Cadastro com campos vazios                 | Tentar salvar o cardápio sem preencher os campos dos itens                              | Sistema bloqueia e informa os campos que faltam               |
| Inserção de preço com vírgula              | Preencher o preço de um item usando vírgula como separador decimal            | Sistema interpreta corretamente ou exibe erro claro de formatação |
| Inserção de preço com ponto                | Preencher o preço de um item usando ponto como separador decimal              | Sistema interpreta corretamente como valor monetário          |

📝 *Observação:* também seria interessante testar o comportamento de edição de cardápios já cadastrados. Por exemplo, o sistema permite alterar o nome para um duplicado?

---

## Considerações Finais

Todos os testes foram pensados para simular o comportamento de um usuário utilizando o sistema via interface administrativa, assumindo que o mesmo esteja autenticado e tenha permissão de acesso.

Se eu tivesse acesso ao ambiente real, incluiria também testes exploratórios e de usabilidade, como verificar mensagens de erro em diferentes tamanhos de tela, uso por teclado, e responsividade.

---

**Elaborado por Yule Brasil - maio/2025**  
Este plano faz parte do desafio para a vaga de QA na Pigz.  
Minha experiência com QA começou durante um projeto em 2021, onde atuei diretamente com uma analista da área e participei da construção de testes para validar fluxos críticos em uma plataforma SaaS.  
Desde então, mantenho o olhar crítico com foco na experiência do usuário e integridade dos dados.

