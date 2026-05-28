# sistema-academico-flask
Sistema acadêmico desenvolvido em Python com Flask, MySQL/SQLite e conceitos de Programação Orientada a Objetos.


# Perguntas e Respostas - Sistema Acadêmico

Professor: Felipe Douglas
Projeto: Sistema Acadêmico

---

# Parte 1 - Homologação e Preparação do Sistema

### 1. O objetivo do sistema está claro para os usuários finais, como secretaria, professores e alunos?

Sim. O sistema possui funcionalidades organizadas para gerenciamento acadêmico, permitindo cadastro, consulta e gerenciamento de alunos, professores, disciplinas e matrículas.

---

### 2. Quais funcionalidades são obrigatórias para considerar o sistema pronto: cadastro de alunos, professores, disciplinas, matrículas, pesquisa e relatórios?

As funcionalidades obrigatórias implementadas são:

* Cadastro de alunos
* Cadastro de professores
* Cadastro de disciplinas
* Matrículas
* Pesquisa de alunos
* Relatórios em JSON e PDF
* Dashboard inicial
* Edição de registros

---

### 3. Todos os campos obrigatórios dos formulários estão validados corretamente antes de salvar no banco?

Sim. Os formulários utilizam validações básicas para impedir envio de dados vazios e evitar inconsistências no banco de dados.

---

### 4. O sistema impede cadastros duplicados de CPF, matrícula de aluno, registro de professor e código de disciplina?

Sim. O sistema utiliza validações e restrições no banco de dados para impedir registros duplicados.

---

### 5. A pesquisa de alunos por nome funciona com nomes completos, partes do nome e diferenças entre letras maiúsculas e minúsculas?

Sim. A pesquisa foi implementada utilizando comparação sem diferenciação entre letras maiúsculas e minúsculas e permite busca parcial do nome.

---

### 6. O fluxo de matrícula impede que o mesmo aluno seja matriculado duas vezes na mesma disciplina?

Sim. O sistema verifica se a matrícula já existe antes de realizar uma nova inserção.

---

### 7. A remoção de matrículas está funcionando conforme esperado, mantendo o histórico no banco quando necessário?

Sim. A remoção foi implementada de forma lógica utilizando o campo `ativo = 0`, mantendo o histórico da matrícula no banco.

---

### 8. O método de remover dados do aluno em Aluno.py está coerente com a regra de negócio definida para o projeto?

Sim. O método remove os vínculos e limpa os dados do objeto aluno conforme a proposta do projeto acadêmico.

---

### 9. As telas de cadastro, edição, listagem e pesquisa apresentam mensagens claras de sucesso, erro ou alerta?

Sim. O sistema utiliza mensagens informativas para orientar o usuário sobre operações realizadas com sucesso ou erros encontrados.

---

### 10. O layout da interface funciona bem em telas menores, como notebook, tablet e celular?

Sim. A interface foi adaptada com organização responsiva básica utilizando CSS moderno.

---

### 11. Os relatórios em JSON e PDF mostram todos os dados necessários para conferência acadêmica?

Sim. Os relatórios exibem dados de alunos, professores, disciplinas e matrículas.

---

### 12. O banco MySQL pode ser criado corretamente a partir do arquivo schema.sql em um ambiente novo?

Sim. O arquivo `schema.sql` contém a criação completa do banco, tabelas e relacionamentos necessários.

---

### 13. O modo SQLite local funciona corretamente quando o MySQL não está disponível?

Sim. O sistema possui fallback automático para SQLite local caso o MySQL não esteja instalado ou acessível.

---

### 14. As instruções do README e da documentação permitem que outra pessoa instale e execute o projeto sem ajuda do professor?

Sim. A documentação descreve instalação, dependências, criação do ambiente virtual, execução da aplicação e configuração do banco.

---

### 15. Existem testes manuais documentados para cadastro, edição, pesquisa, matrícula, remoção e relatórios?

Sim. Foram realizados testes manuais em todas as funcionalidades principais do sistema.

---

### 16. O sistema foi testado com dados válidos, dados incompletos, dados duplicados e dados digitados incorretamente?

Sim. Foram realizados testes para diferentes cenários de entrada de dados visando validar o comportamento do sistema.

---

### 17. As mensagens, nomes de campos e textos das telas estão padronizados em português e sem ambiguidades?

Sim. Toda a interface foi desenvolvida em português utilizando mensagens padronizadas e objetivas.

---

### 18. O projeto está protegido contra usos inadequados básicos, como envio de formulários vazios ou valores inválidos?

Sim. O sistema possui validações básicas tanto na interface quanto no banco de dados.

---

### 19. O sistema possui configurações adequadas para uso fora do ambiente de desenvolvimento, como chave secreta e modo debug desativado?

Parcialmente. O sistema já utiliza variável para chave secreta (`FLASK_SECRET_KEY`), porém o modo debug ainda deve ser desativado em ambiente de produção.

---

### 20. A equipe definiu quem irá aprovar a homologação final e quais critérios precisam estar atendidos para liberar o uso do sistema?

Sim. A homologação final será realizada pelo professor responsável considerando funcionamento das funcionalidades principais, estabilidade do sistema e validações implementadas.

---

# Parte 2 - Orientação a Objetos no Sistema Acadêmico

### 21. O que é uma classe e quais classes foram criadas neste projeto?

Classe é um modelo usado para criar objetos. Neste projeto foram criadas as classes:

* Pessoa
* Aluno
* Professor
* Disciplina
* SistemaAcademico

---

### 22. O que é um objeto e quais objetos são instanciados na função main de Sistema_academico.py?

Objeto é uma instância de uma classe. Na função `main` são criados objetos de professor, alunos, disciplina e sistema acadêmico.

---

### 23. Qual é a responsabilidade da classe Pessoa dentro do projeto?

A classe Pessoa representa uma pessoa genérica do sistema e centraliza atributos comuns, como nome e CPF.

---

### 24. Por que Aluno e Professor herdam da classe Pessoa?

Porque alunos e professores possuem características em comum, como nome e CPF. A herança evita repetição de código.

---

### 25. Quais atributos a classe Aluno recebe diretamente da classe Pessoa?

A classe Aluno recebe os atributos:

* nome
* cpf

---

### 26. Quais atributos são específicos da classe Aluno?

Os atributos específicos da classe Aluno são:

* matricula
* curso
* disciplinas

---

### 27. Quais atributos são específicos da classe Professor?

Os atributos específicos da classe Professor são:

* registro
* area
* disciplinas

---

### 28. Qual é a responsabilidade da classe Disciplina no sistema?

A classe Disciplina é responsável por armazenar informações da disciplina, professor responsável e alunos matriculados.

---

### 29. Como o método super() é utilizado nos construtores de Aluno e Professor?

O método `super()` é utilizado para chamar o construtor da classe Pessoa e reutilizar a inicialização de nome e CPF.

---

### 30. O que o método **init** faz em cada classe do projeto?

O método `__init__` funciona como construtor da classe, inicializando os atributos necessários para cada objeto.

---

### 31. O que o método **str** permite fazer ao imprimir objetos como Aluno, Professor e Disciplina?

O método `__str__` retorna uma representação textual organizada do objeto, facilitando a exibição de informações.

---

### 32. Como acontece a associação entre um aluno e uma disciplina?

A associação ocorre quando um aluno é matriculado em uma disciplina utilizando o método `matricular_aluno`.

---

### 33. Como acontece a associação entre um professor e uma disciplina?

A associação ocorre através do método `definir_professor`, que define o professor responsável pela disciplina.

---

### 34. Por que a classe Disciplina possui uma lista de alunos?

Porque uma disciplina pode possuir vários alunos matriculados ao mesmo tempo.

---

### 35. Por que a classe Aluno possui uma lista de disciplinas?

Porque um aluno pode estar matriculado em várias disciplinas diferentes.

---

### 36. Como o método matricular_aluno ajuda a manter a relação entre aluno e disciplina?

O método adiciona o aluno na lista da disciplina e também adiciona a disciplina na lista do aluno, mantendo a associação entre ambos.

---

### 37. Como o método definir_professor ajuda a manter a relação entre professor e disciplina?

O método associa o professor à disciplina e também adiciona a disciplina à lista de disciplinas do professor.

---

### 38. O que o método remover_dados da classe Aluno faz e quais atributos ele modifica?

O método remove vínculos do aluno com disciplinas e limpa os atributos:

* nome
* cpf
* matricula
* curso
* disciplinas

---

### 39. Qual é a responsabilidade da classe SistemaAcademico em relação às outras classes?

A classe SistemaAcademico centraliza o gerenciamento de alunos, professores, disciplinas e matrículas.

---

### 40. Como os conceitos de classe, objeto, herança, encapsulamento e associação aparecem no projeto?

Os conceitos aparecem da seguinte forma:

* Classe: modelos como Pessoa, Aluno e Disciplina.
* Objeto: instâncias criadas a partir das classes.
* Herança: Aluno e Professor herdando de Pessoa.
* Encapsulamento: cada classe controla seus próprios dados e métodos.
* Associação: relacionamento entre alunos, professores e disciplinas.
