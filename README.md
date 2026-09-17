# Projeto Integrador — Pista e Sistema de Checkpoints

## Equipe:Resenha sem tamanho

**Nome da equipe:Resenha sem tamanho 
**Turma:meca3v
**Professor técnico:Felipe Lins

### Integrantes e áreas de atuação

| Integrante | Área principal | Responsabilidades |
|---|---|---|
|luis philip| Infraestrutura da Pista | Montagem física da pista, posicionamento e fixação das câmeras |
| arthur matos e any raquel | Hardware Central e Rede | Configuração da Raspberry Pi 3 Model, roteamento e atribuição de IPs únicos |
| ana julia | Projeto e Documentação | Arquitetura do sistema, diagramas de rede, organização e relatórios |
| jose kadson| Visão e Câmeras | Configuração dos 3 celulares, transmissão do fluxo de vídeo/imagem e ajuste de ângulos |
| cauã | Software e Automação | Desenvolvimento do fluxo no Node-RED, lógica dos checkpoints e comunicação |

> As áreas acima indicam a responsabilidade principal de cada integrante, mas o trabalho pode ser compartilhado entre a equipe.

---

## 1. Objetivo do projeto

Desenvolver a infraestrutura física da pista e um **Sistema de Checkpoints** automático para monitorar a passagem dos carrinhos durante a competição. O sistema utiliza as
câmeras de 3 celulares posicionados em pontos estratégicos da pista, cada um configurado com um IP único na rede local. A central do sistema é uma placa **Raspberry Pi 3
Model** hospedando o **Node-RED**, responsável por processar os sinais/imagens dos celulares quando o carro passa por cada checkpoint e transmitir os eventos para o painel
de controle e para a organização.

---

## 2. Conceito da solução

A solução é composta por uma infraestrutura de monitoramento e cronometragem da pista baseada em Internet das Coisas (IoT) e Visão Computacional/Sensoriamento IP:

- **Placa Central:** Raspberry Pi 3 Model atuando como servidor local de automação e processamento;
- **Software Central:** Node-RED instalado na Raspberry Pi para gerenciamento de eventos, integração dos fluxos e lógica dos checkpoints;
- **Sensores de Passagem (Checkpoints):** 3 celulares com câmeras e endereços IP únicos (ex.: transmissões RTSP, servidores HTTP ou gatilhos visuais/WebRTC);
- **Estrutura da Pista:** Pista física com 3 pontos fixos de medição (Start/Checkpoint 1, Checkpoint 2 e Finish/Checkpoint 3);
- **Comunicação da Pista:** Rede Wi-Fi/IP local unificada permitindo a comunicação rápida entre os celulares, a Raspberry Pi 3 e a organização;
- **Recursos de Automação:** Algoritmo/Fluxo no Node-RED para registrar o tempo exato de passagem do veículo por cada checkpoint.

---

## 3. Arquitetura geral

Diagrama simplificado da comunicação do sistema da pista:


 [ Celular 1 - IP: xxx ] (Checkpoint 1 / Largada)
                 |
                 v (Fluxo HTTP / RTSP / Evento)
 [ Celular 2 - IP: xxx ] (Checkpoint 2)  ---> [ Rede Wi-Fi Local ] ---> [ Raspberry Pi 3 Model ]
                 ^                                                                  (Hospeda o Node-RED)
                 | (Fluxo HTTP / RTSP / Evento)                                              |
 [ Celular 3 - IP: xxx  ] (Checkpoint 3 / Chegada)                                           |
                                                                                             v
                                                                                    [ Sistema da Organização ]
                                                                                  (Painel / Telemetria MQTT/UDP)

                                                                                  
Subsistemas Infraestrutura Física: Estrutura da pista, marcações do circuito e suporte fixo para os 3 celulares.Hardware Central:
Raspberry Pi 3 Model atuando como nó central de processamento e comunicação.Câmeras / Checkpoints: 3 celulares operando com aplicativos
de câmera IP ou sensores ópticos IP dedicados.Software (Node-RED): Fluxos responsáveis pela recepção dos dados dos celulares, validação
dos checkpoints e temporização.Rede Local: Roteador Wi-Fi garantindo atribuição de IPs estáticos e baixa latência na comunicação.

---

## 4. Estado atual do desenvolvimento
Atualizar esta seção ao longo do projeto.Concluído[ ] 
Definição da arquitetura da pista e posicionamento dos 3 checkpoints[ ]
Instalação do sistema operacional e do Node-RED na Raspberry Pi 3 Model[ ] 
Configuração do roteador e atribuição deIPs estáticos para os 3 celulares[ ]
Configuração do app de transmissão/câmera nos celulares[ ]
Criação do fluxo básico de recepção de eventos no Node-RED[ ]
Teste de detecção de passagem do carro em bancada[ ]
Montagem da estrutura da pista e fixação dos suportes de celular[ ] 
Integração final do sistema com a organização (MQTT / UDP)Em desenvolvimentoDescrever as atividades em andamento.

Pendências principais:
Descrever os principais pontos ainda não resolvidos (ex.: calibração de luz da câmera, latência na comunicação IP).

---

## 5. Planejamento 
Planejamento semanal da equipe está disponível em:PLANEJAMENTO.mdO registro semanal de atividades está disponível em:PROGRESSO.md

---

## 6. Documentação técnica
Organizar a documentação técnica, preferencialmente, nas seguintes pastas:Plaintextdocs/

├── arquitetura/
├── estrutura_pista/
├── rede_e_ips/
├── node_red/
└── testes/

Documentos disponíveis:
Arquitetura geral do sistema: ____________________Planta baixa da pista e posição dos checkpoints: ____________________Tabela de endereçamento IP
e configuração de rede: ____________________Fluxos do Node-RED (flows.json): ____________________Lista de materiais: ____________________
Registros de testes de passagem: ____________________

---

## 7. Materiais e componentes (Item/Quantidade/Origem/Situação Raspberry Pi 3 Model1Equipe)
Organização disponível cartão MicroSD (Node-RED instalado)1EquipeDisponívelCelulares com câmera3EquipeDisponívelRoteador Wi-Fi (para rede de IPs únicos)1EquipeDisponívelSuportes/Tripés para
celular na pista3EquipeEm montagemEstrutura física da pista1Equipe / OrganizaçãoEm construçãoFonte de alimentação Raspberry Pi1EquipeDisponível

---

## 8. Comunicação do sistema
Envio de Checkpoint (Celular / Node-RED -> Sistema)Quando o carrinho passa por uma das 3 câmeras, a Raspberry Pi 3 (via Node-RED) processa a detecção e envia
uma notificação do checkpoint.Protocolo: UDP Unicast ou MQTT (conforme exigência do sistema da organização)Porta: 5000 (UDP) / 1883 (MQTT)Formato: JSON em UTF-8Formato
do evento de passagem no checkpoint enviado pelo Node-RED:JSON{
 
  "equipe": "Equipe XX",
  "checkpoint_id": 1,
  "camera_ip": "192.168.1.101",
  "timestamp_ms": 1726588800000,
  "status": "carro_detectado"
}

Telemetria e Tempos da PistaProtocolo: MQTT 3.1.1 sobre TCPPorta: 1883Tópico previsto: pista/<equipe>/checkpoints9. Testes realizadosRegistrar os testes relevantes do
projeto. Para registros mais detalhados, utilizar docs/testes/.DataTesteResultadoPróxima ação//2026Teste de ping e latência dos 3 celulares na redeSucessoConfigurar
streams no Node-RED//2026Teste de fluxo Node-RED na Raspberry Pi 3SucessoIntegrar gatilho visual de passagem10. ObservaçõesRegistrar aqui informações importantes que
não se encaixem nas demais seções (ex.: condições de iluminação necessárias para a câmera dos celulares, ajustes de sensibilidade da detecção).
---

### Principal alteração realizada:
1. **Foco trocado de "Veículo" para "Pista e Sistema de Checkpoints"**: Todas as seções (objetivo, áreas dos integrantes, componentes, diagramas e estado do desenvolvimento)
2.  agora refletem a criação do circuito e o monitoramento via **3 câmeras IP em celulares + Raspberry Pi 3 rodando Node-RED**.






