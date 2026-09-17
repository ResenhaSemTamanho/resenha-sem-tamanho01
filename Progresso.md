# Registro de Progresso — Projeto Integrador

**Equipe:** Equipe Resenha_Sem_Tamanho
**integrantes:** Arthur Matos, Any Raquel, José Kadson, Ana Júlia, Luís Philip, Cauã
**Turma:** MECA3V
**Professor técnico:** Felipe Lins

Este arquivo deve registrar, de forma objetiva, o andamento semanal do projeto. A equipe não deve apagar registros anteriores. Caso o planejamento mude, a alteração 
deve ser descrita e justificada.

---

# Semana 1 — 16/09/2026 a 22/09/2026

## Planejamento

- Definir a arquitetura geral da pista e o posicionamento dos 3 checkpoints de medição.
- Configurar a rede local para atribuição de IPs únicos a cada um dos 3 celulares.
- Instalar e configurar o ambiente Node-RED na placa Raspberry Pi 3 Model.
- Criar a estrutura inicial do repositório de documentação do projeto.

## Concluído

- Arquitetura do sistema de monitoramento da pista definida.
- Servidor Node-RED instalado e em execução na Raspberry Pi 3 Model.
- Repositório organizado com a documentação base (`README.md`, `PLANEJAMENTO.md` e `PROGRESSO.md`).

## Não concluído

- Validação da velocidade de resposta na transmissão do evento entre o celular e o Node-RED.
- Roteamento e reserva de endereços IP estáticos concluídos para as 3 câmeras dos celulares.

## Decisões técnicas da semana

- Definida a Raspberry Pi 3 Model como centralizadora do sistema de checkpoints via Node-RED.
- Estabelecido que cada checkpoint usará um celular fixado na pista com IP individual via servidor de câmera IP/webhook.

## Testes realizados

- ____________________

## Próximas ações

- Criar os fluxos no Node-RED para receber o sinal quando o carro passar por cada câmera.
- Projetar a estrutura física dos suportes dos celulares ao longo do percurso da pista.
- Realizar o primeiro teste de gatilho de passagem em bancada.

---

# Semana 2 — 23/09/2026 a 29/09/2026

## Planejado

- ____________________
- ____________________
- ____________________

## Concluído

- ____________________
- ____________________

## Não concluído

- ____________________

## Problemas ou impedimentos

- ____________________

## Decisões técnicas da semana

- ____________________

## Testes realizados

| Teste | Resultado |
|---|---|
| ____________________ | ____________________ |

## Próximas ações

- ____________________
- ____________________

---

# Semana 3 — 30/09/2026 a 06/10/2026

## Planejado

- ____________________

## Concluído

- ____________________

## Não concluído

- ____________________

## Problemas ou impedimentos

- ____________________

## Decisões técnicas da semana

- ____________________

## Testes realizados

| Teste | Resultado |
|---|---|
| ____________________ | ____________________ |

## Próximas ações

- ____________________

---

# Semana 4 — 07/10/2026 a 13/10/2026

## Planejado

- ____________________

## Concluído

- ____________________

## Não concluído

- ____________________

## Problemas ou impedimentos

- ____________________

## Decisões técnicas da semana

- ____________________

## Testes realizados

| Teste | Resultado |
|---|---|
| ____________________ | ____________________ |

## Próximas ações

- ____________________

---

# Semana 5 — 14/10/2026 a 16/10/2026

## Planejado

- Preparar a demonstração mínima do sistema de checkpoints para a Avaliação de Progresso 1.
- Revisar a documentação do repositório.
- Comparar o cronograma planejado com o desenvolvimento realizado

## Concluído

- ____________________

## Não concluído

- ____________________

## Problemas ou impedimentos

- ____________________

## Decisões técnicas da semana

- ____________________

## Demonstração preparada para a AP1

Descrever qual subsistema ou conjunto de subsistemas da pista/checkpoints será demonstrado na bancada (ex.: envio de evento de 1 celular para o Node-RED na Raspberry Pi
ao detectar a passagem do carro).

## Situação geral na AP1

### Entregas concluídas

- ____________________

### Entregas parcialmente concluídas

- ____________________

### Entregas não concluídas

- ____________________

### Principais alterações em relação ao planejamento original

- Alteração do escopo principal: transição do desenvolvimento do veículo para o projeto da pista e sistema de monitoramento/checkpoints via câmeras IP e Raspberry Pi 3.

### Justificativas

- Reorganização do foco da equipe para viabilizar o sistema de detecção e cronometragem oficial da pista.

---

# Modelo para semanas posteriores

Copiar o bloco abaixo sempre que uma nova semana for iniciada.

```markdown
# Semana X — DD/MM/AAAA a DD/MM/AAAA

## Planejado

- ...

## Concluído

- ...

## Não concluído

- ...

## Problemas ou impedimentos

- ...

## Decisões técnicas da semana

- ...

## Testes realizados

| Teste | Resultado |
|---|---|
| ... | ... |

## Próximas ações

- ...
