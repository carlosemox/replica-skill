# GSD 11 — Clonagem de referências públicas
Status verificado em 2026-11-06: **GitHub Actions concluído com sucesso (9/9)**.

## Execução
- Workflow: [.github/workflows/gsd11-clone-references.yml](../.github/workflows/gsd11-clone-references.yml)
- Run: https://github.com/carlosemox/replica-skill/actions/runs/42331151854
- Ref: `gsd11/clone-references-20261106`
- Artifacts: `gsd11-public-{id}`, retenção de 7 dias, acesse a seção **Artifacts** da execução.
- Cada artefato é um snapshot de código público em commit Git fixado, sem histórico Git e sem executar código baixado. Não é fork persistente nem integração no aplicativo.

## Fontes clonadas
1. Open-Source-Legal/OpenContracts
2. accordproject/concerto
3. docling-project/docling
4. openfga/openfga
5. docusealco/docuseal
6. documenso/documenso
7. paperless-ngx/paperless-ngx
8. activepieces/activepieces
9. bigcapitalhq/bigcapital (referência financeira complementar; não núcleo jurídico).

## Documentos Replica Recon
- [Recon funcional](replica/recon.md)
- [Matriz de funcionalidades](replica/features.csv)

A metodologia de `replica-recon` foi aplicada a fontes públicas das plataformas Ironclad, Icertis, netLex, Projuris, Juro, Resolve Já, Quitador e Quite Agora. As telas e fluxos são PROPOSTOS, não cópias executáveis e não foram validados em ambiente autenticado.

## Riscos e condições
- Licenças open source devem ser auditadas individualmente, sobretudo AGPL/GPL, antes da integração ou distribuição.
- Códigos proprietários, marcas, dados privados, JavaScript interno e APIs privadas de plataformas comerciais NÃO foram copiados.
- Não executar dependências de terceiros diretamente em produção.
- O GSD 11 não está implementado; nenhum dos nove projetos foi incorporado à aplicação.
- A branch `main` permaneceu inalterada.
