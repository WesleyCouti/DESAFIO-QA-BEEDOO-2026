# DESAFIO-QA-BEEDOO-2026

## Análise inicial da aplicação

Aplicação analisada:  
https://creative-sherbet-a51eac.netlify.app/

## Objetivo da aplicação

A aplicação tem como objetivo permitir o cadastro, visualização e exclusão de cursos de forma simples, centralizando um fluxo básico de gerenciamento de registros.

Pela estrutura disponível, o sistema foi construído com foco em um fluxo direto de entrada e exibição de dados, permitindo ao usuário:

- cadastrar novos cursos;
- visualizar cursos já cadastrados;
- excluir registros existentes.

Mesmo sendo uma aplicação enxuta, ela apresenta pontos relevantes para validação de qualidade, principalmente em relação à consistência dos dados, comportamento do formulário e integridade da listagem.

---

## Principais fluxos disponíveis

Durante a exploração da aplicação, foram identificados os seguintes fluxos principais:

### 1. Cadastro de curso

Fluxo responsável pela entrada de dados no sistema.

O usuário acessa a tela de cadastro pelo menu lateral, preenche o formulário e ao concluir o envio recebe o alerta:

**"Curso cadastrado com sucesso"**

Após isso, ocorre redirecionamento automático para a listagem de cursos.

Campos identificados no formulário:

- Nome do curso
- Descrição do curso
- Instrutor
- URL da imagem de capa
- Data de início
- Data de fim
- Número de vagas
- Tipo de curso

---

### 2. Listagem de cursos

Fluxo responsável por exibir os cursos cadastrados.

Ao acessar a opção **Listar cursos**, o sistema apresenta os registros já criados anteriormente.

Cada item listado possui ação individual de exclusão.

---

### 3. Exclusão de curso

Cada curso listado possui botão **Excluir curso**.

Ao realizar a ação, o sistema exibe o alerta:

**"Curso excluido com sucesso"**

Após isso, o item é removido da listagem.

---

## Pontos mais críticos para teste

Durante a análise, os pontos considerados mais sensíveis foram:

### Validação do formulário de cadastro

Por ser a porta de entrada dos dados, qualquer falha nessa etapa impacta diretamente a confiabilidade do sistema.

Principais validações observadas:

- obrigatoriedade dos campos;
- comportamento com campos vazios;
- preenchimento com espaços em branco;
- limites de entrada;
- tipos de dados aceitos.

---

### Consistência entre cadastro e listagem

Não basta permitir o cadastro.

É necessário garantir que:

- o curso apareça corretamente na listagem;
- os dados exibidos sejam consistentes;
- não haja perda ou duplicidade indevida.

---

### Regras de datas

A relação entre data de início e data de fim é um ponto crítico, pois pode permitir registros inconsistentes.

---

### Número de vagas

Campo sensível para validação de:

- valores negativos;
- letras;
- valores decimais;
- zero;
- números fora de padrão.

---

### Exclusão de registros

Foi considerado importante validar:

- exclusão correta do item selecionado;
- remoção apenas do curso escolhido;
- alerta exibido corretamente;
- comportamento em múltiplos cliques.

---

### Robustez em cenários negativos

Também foram priorizados testes com:

- dados inválidos;
- campos incompletos;
- múltiplos cliques;
- entradas fora do comportamento esperado.

---

## Estratégia adotada para os testes

A cobertura foi construída priorizando:

- fluxo principal;
- cenários negativos;
- validações de campo;
- consistência dos dados;
- comportamento após navegação;
- observação técnica via DevTools (console, network e storage).

A intenção foi manter uma cobertura coerente com os riscos reais da aplicação, sem excesso de cenários repetitivos.

---

## Casos de teste documentados

Os cenários e casos de teste foram organizados em planilha, contendo:

- ID do teste
- funcionalidade
- prioridade
- tipo
- pré-condição
- passos em BDD
- resultado esperado
- resultado obtido
- status

🔗 **Planilha de testes:**  
[LINK_DA_PLANILHA](https://docs.google.com/spreadsheets/d/1uyb2obtfDOK1lwB1K62qiGI5JdL_vpYCRrzrU7JZbg0/edit?usp=sharing)

---

## Relatório de bugs encontrados

Os bugs encontrados foram documentados contendo:

- título;
- passos para reproduzir;
- resultado atual;
- resultado esperado;
- severidade;
- impacto;
- evidência.

🔗 **Planilha de bugs reportados:**  
[LINK_DAS_EVIDENCIAS](https://docs.google.com/spreadsheets/d/1FKsoLBawnnISl1jJ8bqUgjuU5U95SGC5bUAExDXvmY0/edit?usp=sharing)

---

## Evidências da execução

As evidências da execução (prints, gravações e arquivos complementares) foram organizadas em uma pasta específica dentro deste repositório, facilitando a consulta e a rastreabilidade dos resultados obtidos durante os testes.

Também foi disponibilizado um link externo para acesso complementar às evidências:

🔗 **Drive com evidências:**  
[[INSERIR_LINK_DO_DRIVE_AQUI]](https://drive.google.com/drive/folders/1TtlS9bJrOZeKsirOglU4--gkpaUyDiP8?usp=sharing)

Caso haja qualquer indisponibilidade no acesso ao link externo, as evidências permanecem disponíveis diretamente neste repositório como segunda alternativa para análise.

---

## Observação final

Durante a execução, além da validação funcional, também foram observados comportamentos técnicos da aplicação utilizando DevTools, com foco em:

- console do navegador;
- comportamento de armazenamento local;
- validações de front-end;
- consistência técnica após ações principais.

Essa abordagem foi adotada para ampliar a leitura de qualidade sem fugir do escopo funcional proposto no desafio.
