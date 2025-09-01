# Exercício 3 — Sistema de Locadora de Veículos

## 1. Contextualização

Uma empresa de locação de veículos precisa de um sistema simples para gerenciar seu catálogo de veículos, os dados de clientes e os contratos de locação. O objetivo deste exercício é modelar e implementar, em Java, os elementos essenciais de uma locadora, aplicando os princípios de orientação a objetos (OO).

## 2. Entidades e Conceitos

- **Veículo (classe abstrata)**  
  - Atributos comuns: placa, marca, modelo, ano.  
  - Métodos: cálculo de tarifa-base para locação.  
- **Tipos de Veículos (interfaces ou subclasses)**  
  - *Carro*, *Moto* e *Utilitário* devem especializar `Veículo`.  
  - Atributos específicos:  
    - Carro: quantidade de portas.  
    - Moto: cilindrada.  
    - Utilitário: capacidade de carga (em kg).  
  - Cada tipo implementa ou sobrescreve o método de cálculo da tarifa, acrescentando fatores específicos.
- **Cliente**  
  - Atributos: nome, CPF/CNPJ, endereço, telefone.  
  - Métodos: getters e setters com validação básica.
- **Contrato de Locação**  
  - Atributos: cliente, veículo, data de início, data de término, valor calculado.  
  - Métodos: emitir contrato, finalizar contrato e calcular valor total (aplicando descontos ou acréscimos conforme o tipo de veículo e tempo de locação).

## 3. Requisitos Técnicos

1. **Encapsulamento:** todos os atributos devem ser privados, com acesso controlado via métodos públicos.  
2. **Herança e interfaces:** `Veículo` deve ser abstrata e servir de base para `Carro`, `Moto` e `Utilitário`. Se julgar apropriado, crie uma interface adicional (`Tarifável`) para definir o contrato de cálculo de tarifa.  
3. **Polimorfismo:** o cálculo de tarifa em contratos deve ser feito através de referências do tipo `Veículo`/`Tarifável`, permitindo que cada tipo de veículo defina seu próprio valor.  
4. **Validações:**  
   - Verificar que a placa segue um formato válido.  
   - Não permitir contratos com datas inconsistentes (término antes do início).  
   - Garantir que um veículo disponível não seja locado duas vezes simultaneamente.

## 4. Tarefas Propostas

- **Modelagem:** elaborar um diagrama de classes (pode ser informal) indicando atributos e métodos de cada classe descrita.  
- **Implementação:** codificar as classes em Java 17 ou superior, seguindo as boas práticas de OO.  
- **Fluxo de Teste (no método `main`):**  
  1. Cadastrar alguns clientes e veículos de cada tipo.  
  2. Criar contratos de locação com diferentes durações.  
  3. Exibir a lista de veículos disponíveis e de contratos ativos.  
  4. Calcular valores de locação aplicando tarifas diferenciadas conforme o veículo.  
- **Documentação:** incluir comentários em português explicando a finalidade de cada classe e os motivos das escolhas de design.

## 5. Critérios de Avaliação

- Correção na aplicação dos pilares de OO.  
- Coerência da modelagem e clareza na separação de responsabilidades.  
- Implementação das validações e tratamento de possíveis erros.  
- Legibilidade e organização do código.

---

# Exercício 2 — Gestão de Cursos Universitários

## 1. Contextualização

Uma instituição de ensino superior deseja informatizar o controle de seus cursos, disciplinas, professores, alunos e matrículas. O objetivo deste exercício é desenvolver um sistema modular em Java que permita gerenciar esses elementos, reforçando os conceitos de orientação a objetos.

## 2. Entidades e Conceitos

- **Pessoa (classe abstrata)**  
  - Atributos: nome, e-mail institucional, CPF.  
  - Métodos: acesso aos dados e verificação de e-mail válido.  
- **Professor e Aluno (subclasses de Pessoa)**  
  - `Professor` pode ministrar disciplinas e registrar notas.  
  - `Aluno` possui matrícula e histórico de disciplinas cursadas.  
- **Disciplina (classe abstrata ou interface)**  
  - Atributos: código, nome, carga horária.  
  - Métodos: calcular média final.  
  - Possíveis especializações:  
    - *Disciplina Presencial* (possui frequência mínima).  
    - *Disciplina Virtual* (pode ter atividades assíncronas).  
- **Curso**  
  - Atributos: nome, lista de disciplinas, coordenador (professor responsável).  
  - Métodos: adicionar disciplina, listar professores e alunos vinculados.  
- **Matrícula**  
  - Atributos: aluno, disciplina, semestre, notas parciais e presença.  
  - Métodos: registrar notas, calcular média, verificar aprovação.

## 3. Requisitos Técnicos

1. **Abstração e Herança:** `Pessoa` deve ser classe base para `Professor` e `Aluno`. `Disciplina` deve definir um contrato mínimo e ser especializada conforme o tipo (presencial ou virtual).  
2. **Encapsulamento:** dados pessoais e de matrículas devem ser privados, com acesso via métodos.  
3. **Polimorfismo:** o cálculo da média final deve ser polimórfico, pois disciplinas presenciais podem exigir frequência mínima, enquanto virtuais podem ter cálculo de nota diferente.  
4. **Validações:**  
   - E-mails devem seguir um padrão institucional.  
   - Não permitir matrícula de um aluno em uma mesma disciplina mais de uma vez no mesmo semestre.  
   - Notas devem estar dentro de um intervalo definido (ex.: 0 a 10).  

## 4. Tarefas Propostas

- **Modelagem:** desenhar um diagrama de classes indicando as relações de herança e composição.  
- **Implementação:** programar as classes em Java, garantindo que todos os atributos sejam acessados de forma segura.  
- **Fluxo de Teste:**  
  1. Criar professores e alunos com dados fictícios válidos.  
  2. Criar diferentes disciplinas (presenciais e virtuais) e associá-las a um curso.  
  3. Matricular alunos nas disciplinas, registrar notas e presença (quando aplicável).  
  4. Calcular e exibir médias finais, mostrando quem foi aprovado ou reprovado.  
- **Comentários:** escrever explicações breves em português no código, justificando escolhas de herança, interfaces ou encapsulamento.

## 5. Critérios de Avaliação

- Cumprimento das especificações de modelagem e implementação.  
- Aplicação correta dos pilares da OO.  
- Tratamento de casos de erro e validações.  
- Clareza do código e qualidade dos comentários.