# 📚 Conecta Pesquisa — Plataforma de Integração Acadêmica

A Conecta Pesquisa é uma plataforma web projetada para aproximar discentes e docentes da UFAM, facilitando a criação de conexões acadêmicas para pesquisa, extensão e inovação.  
O objetivo é romper a barreira informacional que impede alunos de encontrar oportunidades e professores de encontrar talentos, formando equipes interdisciplinares com base em interesses, habilidades e objetivos reais.

---

## 🎯 Propósito

Hoje, muitos estudantes desejam participar de projetos científicos, mas não sabem por onde começar. Por outro lado, docentes possuem ideias, linhas de pesquisa e demandas, mas encontram dificuldade em atrair perfis adequados.  
O resultado é um ambiente onde:

- A pesquisa permanece concentrada em pequenos grupos.
- Alunos iniciantes sentem-se desmotivados ou "excluídos".
- A inovação se torna fragmentada e pouco interdisciplinar.

A Conecta Pesquisa nasce para mudar esse cenário, transformando o processo em algo acessível, transparente e colaborativo.

---

## 👥 Público-Alvo

### Docentes  
Professores que buscam divulgar oportunidades e encontrar estudantes com competências específicas.

### Discentes  
Estudantes interessados em engajar-se em pesquisa científica, extensão ou projetos inovadores alinhados à sua trajetória acadêmica.

---

## 🧩 Funcionalidades

### Para Docentes
- Criar e gerenciar projetos.
- Avaliar candidaturas de alunos.
- Pesquisar perfis acadêmicos filtrando por: áreas, habilidades, campus, curso etc.
- Encerrar projetos e controlar participação.

### Para Discentes
- Criar e manter perfil acadêmico com habilidades, interesses e links públicos (ex: CV Lattes, GitHub).
- Explorar oportunidades disponíveis.
- Inscrever-se com mensagem personalizada.
- Acompanhar status das candidaturas.

---

## ⚙️ Requisitos Funcionais

### 🧑‍🏫 Docentes

| Código | Nome | Descrição | Critérios de Aceite |
|--------|------|-----------|--------------------|
| RF-DOC-01 | Criar projeto | Cadastro com título, descrição, objetivos, requisitos, tipo, prazo, campus, carga horária e vagas. | - Não salvar sem título.<br>- Status inicial: `ABERTO` *(RN-01)* |
| RF-DOC-02 | Editar projeto | Permite ajustes enquanto o status ≠ `CONCLUÍDO`. | - Só editar status ≠ `CONCLUÍDO`.<br>- Prazo novo ≥ data atual *(RN-02)* |
| RF-DOC-04 | Gerenciar participantes | Adicionar/remover alunos aprovados. | - Apenas candidaturas com status `ACEITA`. |
| RF-DOC-05 | Avaliar candidaturas | Aceitar ou recusar. | - Status se torna `ACEITA` ou `RECUSADA`. |
| RF-DOC-07 | Pesquisar perfis | Busca por nome de aluno. | - Filtro mínimo: nome. |
| RF-DOC-08 | Encerrar projeto | Fecha candidaturas e define status final. | - Candidaturas pendentes → `NÃO_AVALIADA_ENCERRADA`. |


### 🎓 Discentes

| Código | Nome | Descrição | Critérios de Aceite |
|--------|------|-----------|--------------------|
| RF-DIS-01 | Criar/Atualizar perfil | Preencher curso, campus, período, áreas, habilidades, links. | - Campos mínimos: curso e período. |
| RF-DIS-02 | Buscar projetos | Listar apenas projetos `ABERTO`. | - Exibir vagas + prazo restante. *(RN-03)* |
| RF-DIS-03 | Ver detalhes | Página completa do projeto. | - Mostrar status, vagas, prazo, docente responsável, modalidade. |
| RF-DIS-04 | Enviar candidatura | Botão “Quero participar” + mensagem. | - Bloquear duplicatas *(RN-09)*.<br>- Status inicial: `PENDENTE`. |
| RF-DIS-05 | Acompanhar status | Ver histórico de candidaturas. | - Status possíveis: `PENDENTE`, `ACEITA`, `RECUSADA`, `NÃO_AVALIADA_ENCERRADA`. |
| RF-DIS-07 | Acesso ao projeto | Após aprovação, participar da equipe. | - Acesso ao mural.<br>- Remoção exclui acesso. |

---

## 🧠 Regras de Negócio

### Estados & Transições
- `ABERTO → EM_ANDAMENTO → CONCLUÍDO`
- Prazo mínimo: ≥ D+1
- Candidaturas permitidas apenas com status `ABERTO` + prazo válido.

### Limites & Integridade
- Candidatura única por projeto.
- Perfil mínimo para se inscrever: curso + período.
- Links até 5 URLs válidas.
- Vagas possuem controle automático de lotação.
- Remoções geram histórico (não apagamos nada).

### Auditoria & Persistência
- Todas as decisões são registradas.
- Exclusões são **lógicas**, nunca físicas.

---

## 🧱 Requisitos Não-Funcionais

- Sistema deve ser responsivo e acessível.
- Auditoria completa por ação.
- Estrutura escalável para múltiplos campi.
- Segurança na validação de links e dados sensíveis.
- Persistência com exclusão reversível (soft delete).

---

## 🏗️ Visão de Futuro

A primeira versão foca na conexão.  
A próxima será sobre inteligência: recomendações automáticas, trilhas de pesquisa, chatbot orientador, histórico de carreira acadêmica e integração com plataformas governamentais.

---

## 💬 Conclusão

A Conecta Pesquisa não é apenas um software — é uma ponte. Uma ponte entre quem quer aprender e quem pode orientar; entre ideias dispersas e projetos transformadores; entre potencial e impacto.

A estrada se abre agora.

> Ciência é colaboração. Inovação é encontro. Esta plataforma existe para unir os dois.

---

📌 *Documento versão inicial — passível de expansão conforme escopo e roadmap.*
```markdown
