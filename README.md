# Calculadora de Rendimento Opea SCD

## Fluxo

### Fotografia dos saldos das contas e caixinhas
- Todo dia no horário de corte de cada conta é feita uma fotografia do saldo de todas as caixinhas e de do saldo da conta principal
- O saldo das caixinhas selecionadas das contas que possuem remuneração serão remuneradas de acoro com o valor fotografado

### Trava das contas
- A partir desta fotografia realizada, todas as movimentações de resgate das contas com rendimento deverão ser bloqueadas até o próximo dia

### Calculo da remuneração
- O saldo das caixinhas ÀS 16h do D-1 é a referência para a remuneração dela no D0. Tendo este valor de referência e o CDI, é calculada a remuneração.
- No próximo dia, aparece na caixinha um crédito referente á “Rendimento” com o valor base da fotografia feita às 16:00 do dia anterior e o resgate fica liberado
##

# Calculadora

### Valores iniciais

$Taxa\ Anual\ do\ CDI = CDI =0.1065$ - Devemos receber via API ou Inputar manualmente Backoffice

$Taxa\ de\ Rendimento\ da\ Caixinha=0.75$

$Aliquota=0.225$

$Dias\ Uteis=DU=252$

$Saldo= 2.869.867,62$

##
### Calcular o Fator DI

$=(1+ARRED((1+0,1065)^{1/252}-1;8)*0,75)$

$=(1+ARRED((x);8)*0,75)$

$x =(1 + taxaAnualCDI)^{1/diasUteis}-1$

$x=(1 + 0.1065)^{1/252}-1$

$x=(1.1065)^{0,003968253968254}-1$

$x=(1.1065)^{0,003968253968254}-1$

$x=1,000401675413898-1$

$x=0,000401675413898$

$x=0,000401675413898$

$ARRED((0,000401675413898);8)=0,00040168$

$=(1+0,00040168*0,75)$

$=(1+0,00030126)$

$fatorDI=1,00030126$

    Se o resultado do Fator DI tiver mais que 16 casa decimais, o valor deve ser TRUNCADOO na 16 casa.

    TRUNCAR = Cortar o valor na casa descimal específicar
    ARRED = Arredondar o valor na casa específica

##
### Calcular o Rendimento Bruto da Caixinha

$z= ARRED(fatorDI;8)$

$z=1,00030126$

$y= Saldo*(z-1)$

$y= 2869867,62*(1,00030126-1)$

$y= 2869867,62*0,00030126$

$y= 864,5763192012$

$x=TRUNCAR(y;8)$

$x=TRUNCAR(864,5763192012;8)$

$x=864,57631920$

$w=ARRED(x;2)$

$w=ARRED(864,57631920;2)$

$Rendimentp\ Bruto\ Caixinha=864,58$

##
### Calcular o Rendimento Liquido da Caixinha

$=ARRED(rendimentoBruto*(1-aliquota);2)$

$=ARRED(864,57631920*(1-0.225);2)$

$=ARRED(864,57631920*(0,775);2)$

$=ARRED(670,04664738;2)$

$Rendimento\ Liquido\ Caixinha=670,05$

##
### IRRF

$=ARRED(rendimentoBruto*aliquota;2)$

$=ARRED(864,57631920*0.225;2)$

$=ARRED(194,52967182;2)$

$Imposta\ Retido\ na\ Fonte=194,53$

##
### Calcular o Rendimento Bruto do 100% CDI

$=(1+ARRED((1+0,1065)^{1/252}-1;8)$

$=(1+ARRED((x);8))$

$x =(1 + taxaAnualCDI)^{1/diasUteis}-1$

$x=(1 + 0.1065)^{1/252}-1$

$x=(1.1065)^{0,003968253968254}-1$

$x=(1.1065)^{0,003968253968254}-1$

$x=1,000401675413898-1$

$x=0,000401675413898$

$ARRED((0,000401675413898);8)=0,00040168$

$Rendimento\ Bruto\ 100=0,00040168 * 2869867,62$

$Rendimento\ Bruto\ 100=1152,7684256016$

$Rendimento\ Bruto\ 100=1152,76842560$

$Rendimento\ Bruto\ 100=1152,77$

##
### Calcular o Rendimento Bruto da SCD de 99% CDI

$=(1+ARRED((1+0,1065)^{1/252}-1;8)*0,99)$

$=(1+ARRED((x);8)*0,99)$

$x =(1 + taxaAnualCDI)^{1/diasUteis}-1$

$x=(1 + 0.1065)^{1/252}-1$

$x=(1.1065)^{0,003968253968254}-1$

$x=(1.1065)^{0,003968253968254}-1$

$x=1,000401675413898-1$

$x=0,000401675413898$

$x=0,000401675413898$

$ARRED((0,000401675413898);8)=0,00040168$

$=(1+0,00040168*0,99)$

$=(1+0,0003976632)$

$fatorDI99=1,0003976632$

$=2869867,62*0,0003976632$

$=1141,240741345584$

$=1141,24074134$

$Rendimento\ Bruto\ 99=1141,24$

##
### Calcular o Spread

$=1141,24 - 864,58$

$Valor\ do\ Spread=276,66$

$=99 - 75$

$=24$
