ADR 02: Implementação da arquitetura hexagonal

Status: Aceita

Contexto: Contexto: O EduVerse deve coexistir com o LMS institucional (Moodle) sem substituílo. A sincronização de dados é crítica: matrículas, notas históricas e progresso do
aluno devem fluir bidirecionalmente entre os sistemas. Sem uma camada deisolamento, mudanças na API do Moodle ou na estrutura de dados do LMS quebrariamo Motor de Recomendação Adaptativo, violando o RNF de Manutenibilidade. 

Decisão: Foi escolhido adotar a Arquitetura Hexagonal, esta escolha baseia-se na necessidade de isolar o núcleo do sistema onde residem o motor de IA e as regras de aprendizado adaptativo, de quaisquer dependências de infraestrutura ou sistemas externos.

A escolha justifica-se pela garantia da manutenibilidade (RNF 5), permitindo que o núcleo do sistema evolua de forma independente de tecnologias externas. O isolamento das regras de negócio através de portas e adaptadores facilita atualizações e protege
o motor de IA contra mudanças na infraestrutura ou na API do Moodle. Além disso, devido à sua modularidade, a arquitetura torna mais fácil a integração de novas ferramentas, garantindo que o sistema esteja preparado para o futuro caso o Moodle seja substituído 
por uma tecnologia mais recente.
