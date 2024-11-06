# Calculadora de Rendimento

## Fluxo

1. Fotografia dos saldos das contas e caixinhas
- Todo dia no horário de corte de cada conta é feita uma fotografia do saldo de todas as caixinhas e de do saldo da conta principal
- O saldo das caixinhas selecionadas das contas que possuem remuneração serão remuneradas de acoro com o valor fotografado

2. Trava das contas
- A partir desta fotografia realizada, todas as movimentações de resgate das contas com rendimento deverão ser bloqueadas até o próximo dia

3. Calculo da remuneração
- O saldo das caixinhas ÀS 16h do D-1 é a referência para a remuneração dela no D0. Tendo este valor de referência e o CDI, é calculada a remuneração.
- No próximo dia, aparece na caixinha um crédito referente á “Rendimento” com o valor base da fotografia feita às 16:00 do dia anterior e o resgate fica liberado

## Calculadora

1. Valores iniciais

- *taxaAnualCDI:* 10.65% aa (18/10/2024);
- taxaRendimentoCaixinha: 75%;
- aliquota: 22.5%;
- diasUteis: 252;