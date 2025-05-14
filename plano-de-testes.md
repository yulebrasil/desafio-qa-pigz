# Plano de Testes - Desafio QA Pigz

## Funcionalidade 1 - Cadastro de Restaurantes

| Cenário                                     | Passos                                                                                  | Resultado Esperado                                             |
|--------------------------------------------|------------------------------------------------------------------------------------------|----------------------------------------------------------------|
| Cadastro com dados válidos                 | Preencher todos os campos obrigatórios com dados corretos e clicar em "Salvar"          | Restaurante cadastrado com sucesso e redirecionamento à lista |
| CNPJ inválido                              | Informar um CNPJ inválido e tentar salvar                                               | Sistema exibe mensagem de erro sobre CNPJ inválido             |
| CNPJ duplicado                             | Cadastrar restaurante com CNPJ já existente no sistema                                  | Sistema exibe erro de CNPJ duplicado                           |
| Campo obrigatório vazio (nome, endereço…)  | Deixar um ou mais campos obrigatórios em branco e tentar salvar                         | Sistema impede o cadastro e exibe erro correspondente          |

---

## Funcionalidade 2 - Cadastro de Cardápios

| Cenário                                     | Passos                                                                                  | Resultado Esperado                                             |
|--------------------------------------------|------------------------------------------------------------------------------------------|----------------------------------------------------------------|
| Cadastro completo e válido                 | Selecionar restaurante, preencher nome, descrição e itens válidos, e clicar em "Salvar" | Cardápio salvo e redirecionado para a lista                   |
| Nome do cardápio ausente                   | Tentar cadastrar sem preencher o nome do cardápio                                       | Sistema impede o cadastro e exibe erro                        |
| Nome duplicado no mesmo restaurante        | Tentar cadastrar dois cardápios com o mesmo nome para o mesmo restaurante               | Sistema exibe erro de nome duplicado                          |
| Item sem nome ou preço inválido            | Adicionar item sem nome ou com preço inválido (ex: texto em vez de número)              | Sistema exibe erro e impede o cadastro                        |
| Campos obrigatórios vazios                 | Deixar campos obrigatórios em branco e tentar salvar                                    | Sistema impede o cadastro e mostra mensagens de erro          |

---

## Observações

- Todos os testes consideram que o usuário está autenticado e no painel de administração.
- Os testes podem ser executados manualmente através da interface do sistema.
