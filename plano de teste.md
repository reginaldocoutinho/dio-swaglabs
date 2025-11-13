O objetivo é o usuário acessar a plataforma pela pagina de Login, visualizar o catálogo de produtos, detalhes dos produtos, adicionar /remover itens ao carrinho, cadastrar endereço e dados de envio e finalizar compra.

Escopo (In)
-----------

*   **Autenticação**: login/logout, mensagens de erro.
    
*   **Catálogo**: listagem, ordenação/filtragem (se houver), detalhes do produto.
    
*   **Carrinho**: adicionar, remover, atualizar quantidades.
    
*   **Checkout**: endereço/dados de envio, pagamento simulado, confirmação.
    
*   **Mensagens e estados de UI** (erro/sucesso, loaders).
    

Fora do Escopo (Out)
--------------------

*   Integrações reais de pagamento/frete.
    
*   Testes mobile nativos (somente web responsivo).
    
*   Teste de performance e segurança (em outro plano).
    

Tipos de Teste
--------------

*   **Smoke** (fluxo compra fim-a-fim).
    
*   **Funcionais** (por módulo).
    

Ambiente
--------

*   **URL**: https://www.saucedemo.com/
    
*   **Browsers**: Chrome (principal), Firefox (sanidade).
    
*   **Dados**: usuários válidos/invalidos (ex.: standard\_user), produtos padrão, CEP/Endereço dummy.
    

Critérios de Entrada
--------------------

*   Build disponível e estável.
    
*   Ambiente acessível e credenciais válidas.
    
*   Histórias com critérios de aceite aprovados.
    

Critérios de Saída
------------------

*   **Smoke 100% aprovado**.
    
*   **Funcionais críticos ≥ 95% aprovados**.
    
*   **Bugs**: sem **bloqueadores** nem **críticos** abertos; 
    

Riscos & Mitigações
-------------------

*   **Dependência externa** (catálogo/checkout) indisponível → simular dados/usar mocks.
    
*   **Dados voláteis** → reset de massa antes dos testes.
    
*   **Flakiness** em UI → esperar por **estado** (URL/elemento) em vez de wait fixo.
    

Métricas
--------

*   Taxa de aprovação por suíte (Smoke/Funcional/Regressão).
    
*   Densidade de defeitos por módulo.
    
*   Tempo médio de execução (local/CI).