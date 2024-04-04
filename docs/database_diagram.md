# Database Diagram

### Tabela `events`

| Campo            | Tipo         | Restrições               |
|------------------|--------------|--------------------------|
| id               | TEXT         | NOT NULL, PRIMARY KEY    |
| title            | TEXT         | NOT NULL                 |
| details          | TEXT         |                          |
| slug             | TEXT         | NOT NULL                 |
| maximum_attendees| INTEGER      |                          |

### Tabela `attendees`

| Campo      | Tipo        | Restrições                                             |
|------------|-------------|--------------------------------------------------------|
| id         | INTEGER     | NOT NULL, PRIMARY KEY, AUTOINCREMENT                  |
| name       | TEXT        | NOT NULL                                               |
| email      | TEXT        | NOT NULL                                               |
| event_id   | TEXT        | NOT NULL                                               |
| created_at | DATETIME    | NOT NULL, DEFAULT CURRENT_TIMESTAMP                   |

### Tabela `check_ins`

| Campo      | Tipo        | Restrições                                             |
|------------|-------------|--------------------------------------------------------|
| id         | INTEGER     | NOT NULL, PRIMARY KEY, AUTOINCREMENT                  |
| created_at | DATETIME    | NOT NULL, DEFAULT CURRENT_TIMESTAMP                   |
| attendeeId | INTEGER     | NOT NULL                                               |

## Explicação

O banco de dados escolhido para esse projeto foi o Postgres.<br>
A esquematização foi projetada para fornecer suporte à gestão de participantes em eventos. Ele consiste em três tabelas principais: events, attendees e check_ins.

A tabela events armazena informações sobre os eventos, como título, detalhes, identificador único (id), um identificador legível para humanos (slug) e o número máximo de participantes permitidos (maximum_attendees).

A tabela attendees registra os participantes que se inscreveram nos eventos. Ela inclui campos para o nome, email, um identificador único autoincremental (id) e o event_id que está relacionado ao evento específico em que o participante está inscrito. Além disso, há um registro de data e hora de quando o participante foi registrado (created_at).

Por fim, a tabela check_ins rastreia os check-ins dos participantes nos eventos. Ela registra a data e hora do check-in (created_at) e o attendeeId que está associado ao participante específico que realizou o check-in.

Essa estrutura de banco de dados foi projetada para suportar um sistema eficiente de gerenciamento de eventos, permitindo o registro de eventos, inscrições de participantes e acompanhamento dos check-ins, fornecendo assim uma visão abrangente do envolvimento dos participantes em cada evento.


Obs.: Links dos arquivos .sql e schema.prisma seguem abaixo.
- [migration.sql](https://github.com/JhonataAugust0/devops_nlw/blob/master/prisma/migrations/20240401194747_setup/migration.sql)
- [schema.prisma](https://github.com/JhonataAugust0/devops_nlw/blob/master/prisma/schema.prisma)