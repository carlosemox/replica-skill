# GSD 11 — Replica Recon (evidências públicas)
Data da revisão: 2026-11-06
Status: descoberta documental / reconstrução independente, NÃO clonagem de software proprietário.

## Escopo
Módulo: Jurídico, Contratos e Cobrança.
Usuários: jurídico, gestores de contratos, responsáveis por recuperação de crédito, aprovadores, devedores autorizados e auditores.
Limites: GSD02 controla recebíveis e conciliação; GSD00 oferece consulta; integrações e permissões seguem serviços compartilhados. Compras e fornecedores não são responsabilidade primária do GSD11.

## Benchmark: fontes observadas
| Plataforma | Evidência pública | Capacidade a estudar |
|---|---|---|
| Ironclad | https://support.ironcladapp.com/hc/en-us/articles/24858534941079-Workflows-Overview | solicitação -> revisão -> aprovação -> assinatura |
| Icertis | https://www.icertis.com/products/platform | inteligência contratual, cláusulas e obrigações |
| netLex | https://netlex.io/solucoes/juridico | requisição, governança de modelos, assinaturas, monitoramento |
| Projuris Contratos | https://www.projuris.com.br/contratos/ | modelos, criação, revisão, reajuste, renovação |
| Juro | https://api-docs.juro.com/ | templates, estados de ciclo, assinatura, API e webhooks |
| Resolve Já | https://hub.resolveja.com.br/ | gestão da carteira e portal de autonegociação |
| Quitador | https://quitador.com.br/ | cobrança multicanal, Pix/boleto e negociação |
| Quite Agora | https://www.quiteagora.com.br/portal-quite-agora/ | consulta de pendências, simulação e quitação |

**Atenção:** capacidades da tabela são documentadas publicamente. Não foram acessadas áreas autenticadas, observadas telas internas ou utilizados dados privados.

## Inventário de telas PROPOSTAS (não observadas nas plataformas)
| ID | Tela | Propósito |
|---|---|---|
| S01 | Painel jurídico | visão de pendências e riscos |
| S02 | Solicitações contratuais | abertura e triagem |
| S03 | Detalhe da solicitação | dados, anexos e responsáveis |
| S04 | Modelos e cláusulas | biblioteca versionada |
| S05 | Editor e versões | minuta com histórico |
| S06 | Revisão e riscos | divergências, comentários, parecer |
| S07 | Aprovações | alçadas e decisões |
| S08 | Assinaturas | status e comprovantes |
| S09 | Contratos ativos | índice e busca |
| S10 | Obrigações e prazos | responsáveis, evidências e alertas |
| S11 | Aditivos e renovações | alterações e encerramento |
| S12 | Carteira de cobrança | títulos vinculados ao financeiro |
| S13 | Caso de cobrança | linha do tempo, contatos e documentos |
| S14 | Portal de negociação | propostas e aceite |
| S15 | Acordos e liquidação | cronograma, pagamento e status conciliado |
| S16 | Governança e auditoria | permissões, trilhas e retenção |

Estados a detalhar: vazio, carregando, acesso negado, erro, pendente, concluído e visualização móvel.

## Fluxos PROPOSTOS
- F01 Contratação: S02 -> S03 -> S04 -> S05 -> S06 -> S07 -> S08 -> S09.
- F02 Monitorar execução: S09 -> S10 -> S11 -> S09.
- F03 Cobrança amigável: S12 -> S13 -> S14 -> S15; pagamentos confirmados exclusivamente pelo GSD02.
- F04 Exceção: S06 -> S07 -> escalonamento humano -> decisão e registro.
- F05 Revisão de acesso: S16 -> autorização auditada -> S01.

## Modelo conceitual INFERIDO (requer engenharia e validação)
Tenant, LegalRequest, Party, Contract, ContractVersion, ClauseTemplate, ReviewFinding, Approval, SignatureEnvelope, Obligation, Deadline, Amendment, CollectionCase, DebtReference, CommunicationEvent, SettlementOffer, Agreement, PaymentReference, AuditEvent.

## Requisitos mínimos de segurança e conformidade
Isolamento tenant, RBAC/ABAC, menor privilégio, MFA/step-up para aprovação e operações sensíveis, trilha de auditoria imutável, revisão jurídica humana em decisões de risco, idempotência, versionamento, consentimento/base legal aplicável, retenção e exclusão conforme legislação vigente. Nenhuma cobrança abusiva e nenhuma confirmação automática de pagamento sem retorno autoritativo do financeiro.

## Restrições de cópia
- Não copiar: código fechado, design/ativos protegidos, textos privados, credenciais, dados de clientes, endpoints internos, marcas ou screenshots de terceiros em produção.
- Código aberto pode ser baixado e avaliado conforme licença individual, observando copyleft e obrigações de distribuição.
- A metodologia replica-recon: https://github.com/Jakeschincariol/replica-skill/blob/main/replica-recon/SKILL.md
- Próximo passo: replica-architect, após validação do escopo e das fontes. Este documento NÃO comprova implantação funcional.
