Estudo de Caso em uma universidade, como parte do desenvolvimento da disciplina **ES42E - Banco de Dados** ministrada pelo **Professor Giovani Volnei Meinerz** na **Universidade Tecnológica Federal do Paraná - Campus Cornélio Procópio**.

SGBD utilizado: **MySQL**

### Diagrama Entidade Relacionamento (DER):

<img src="images\DER_EC_universidade.png" width="600">

### Regras de Negócios:

1. **RN01** - Possibilitar o cadastramento dos departamentos acadêmicos da UTFPR. Cada departamento possui uma identificação exclusiva, além de nome e sigla (atributos obrigatórios).
2. **RN02** - Possibilitar o cadastramento dos cursos. Um curso possui uma identificação exclusiva, além de um nome (atributo obrigatório). Um curso pertence a um único departamento, enquanto um departamento poderá ser composto por vários cursos, ao menos um.
3. **RN03** - Possibilitar o cadastramento das disciplinas ofertadas por um determinado curso. Uma disciplina possui uma identificação exclusiva, além de um nome, como atributo obrigatório. Uma disciplina é ofertada por um, e somente um, curso, enquanto um curso oferece várias disciplinas, ao menos uma.
4. **RN04** - Possibilitar o cadastramento das turmas $^{1}$. Uma turma possui uma identificação exclusiva, além do período letivo $^{2}$ da turma (atributo obrigatório). Uma turma pertence a um, e somente um, curso, enquanto que um curso possui várias turmas $^{3}$, ao menos uma.
5. **RN05**Possibilitar o cadastramento dos professores. Um professor possui uma identificação exclusiva, além de nome $^{4}$, bem como campo para atribuir o valor de seu salário e telefone de contato (ddd+número). Todos estes, atributos obrigatórios, com exceção do telefone. Um professor pode ser empregado por um departamento, não obrigatoriamente, enquanto que um departamento pode empregar vários professores, ao menos um.
6. **RN06** - Possibilitar o cadastramento das turmas/disciplinas, onde uma turma pode estar vinculada a várias disciplinas, inclusive nenhuma, e uma disciplina associada a várias turmas, inclusive nenhuma. É obrigatório informar o ano e o semestre que a turma/disciplina cadastrada será oferecida. Cada turma/disciplina é ensinada por um único professor, enquanto um professor ensina várias turmas/disciplinas, inclusive nenhuma. Também é obrigatório informar o tipo de modalidade $^{5}$ da turma/disciplina cadastrada. A identificação exclusiva deve ser definida adequadamente.
7. **RN07** - Possibilitar o cadastramento dos prédios. Um prédio possui uma identificação exclusiva, além de nome (atributo obrigatório).
8. **RN08** - Possibilitar o cadastramento das salas. Uma sala possui uma identificação exclusiva $^{6}$ e a informação sobre o tipo da sala $^{7}$. Também deve permitir o cadastramento da informação sobre quantidade de posições disponíveis na sala, bem como a quantidade de computadores disponíveis (que pode ser igual ou menor a quantidade de posições). Ambos os atributos são obrigatórios. Uma sala está localizada em um único prédio, enquanto um prédio possui várias salas, ao menos uma.
9. **RN09** - Possibilitar o ensalamento das turmas/disciplinas, indicando obrigatoriamente dia $^{8}$, horário e sala alocada. Quanto ao horário, deve ser considerada a distribuição das horas aula ao longo dos três turnos de um dia, conforme mostra a figura a seguir:

    <img src="images\EC_universidade_ensalamento.png" width="100">
    
    Uma turma/disciplina requer vários, inclusive nenhum ensalamento (caso da modalidade à distância), enquanto que um ensalamento está vinculado a uma, e somente uma, turma/disciplina. Por outro lado, uma sala poderá ser utilizada para ensalar várias turmas/disciplinas, inclusive nenhuma, enquanto que um ensalamento utiliza uma, e somente uma sala.

1 - Cada curso possui as suas turmas, criadas para cada um dos períodos letivos.

2 - A quantidade de períodos letivos depende do curso. Ex.: Engenharia de Computação possui 10 períodos, Engenharia de Software, 8 e TADS, 6.

3 - Normalmente uma turma para cada período letivo.

4 - Atributo composto por: primeiro e último nome.

5 - Podendo ser: Presencial, Distância ou Semipresencial.

6 - Exemplo: I205, P104, A143, etc.

7 - Especial, Teórica, Laboratório, Desenho, Pesquisa, Monitoria, etc.

8 - Onde 2 = 2ª feira; 3 = 3ª feira; 4 = 4ª feira; 5 = 5ª feira; e 6 = 6ª feira.