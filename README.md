# Resgate de ex-clientes · Vem Pra Uno

Página simples para trabalhar o relatório de contratos cancelados do IXC: filtra por motivo de saída e época, mostra só quem vale a pena contatar, abre o WhatsApp já com a mensagem (6 modelos, com teste A/B) e registra quem respondeu e quem voltou.

## Como publicar no GitHub Pages
1. Crie um repositório (prefira **privado**) e envie `index.html`, `README.md` e `.gitignore`.
2. Em **Settings → Pages**, escolha **Deploy from a branch**, branch `main`, pasta `/ (root)`.
3. Abra o link gerado, arraste o CSV do relatório para a página e pronto.

## Cuidado com os dados (LGPD)
- **Nunca envie o CSV para o repositório.** Ele tem nome, telefone e CEP de milhares de pessoas. O `.gitignore` já bloqueia `.csv`.
- O CSV é lido só no navegador; nada é enviado a servidor algum.
- O registro de contatos fica salvo no navegador usado (não sincroniza entre computadores). Use "Baixar lista filtrada" para guardar uma cópia.

## Como o relatório é interpretado
- Cada cliente aparece uma vez, pelo contrato cancelado mais recente.
- O motivo é classificado a partir de "Obs. cancelamento":
  - **Pode contatar:** saída sem pendências, mudança, outro provedor, insatisfação, preço, desistência etc.
  - **Saiu com pendência:** inadimplência, débito ou equipamento não devolvido (fica oculto até marcar a opção).
  - **Provável cliente ativo:** migração, upgrade, troca de titularidade, roteador adicional (contrato antigo encerrado, cliente segue na Uno). Fica fora da lista.
- O relatório só traz contratos inativos, então confira no IXC se a pessoa não tem um contrato ativo novo antes de abordar.
- Datas de cancelamento inválidas (ex.: 01/01/0001) aparecem como "data inválida".
- Valores e condições de retorno devem seguir a política comercial vigente.
