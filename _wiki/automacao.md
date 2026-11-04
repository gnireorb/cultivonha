---
title: "Automação da estufa: timer, termostato e Home Assistant"
titulo_curto: "Automação"
description: "Do timer de tomada ao Home Assistant: como automatizar luz, exaustão e umidade, criar alertas e montar tudo de um jeito que não falhe quando a internet cair."
atualizado: '2026-10-26'
revisao: "Página criada na revisão de outubro de 2026."
fontes_acesso: 2026-10-16
fontes:
  - abnt: "HOME ASSISTANT. **Generic thermostat**. [S. l.], [20--]a. Disponível em: <https://www.home-assistant.io/integrations/generic_thermostat/>."
    nota: "Termostato virtual que liga e desliga um aparelho por um sensor de temperatura."
  - abnt: "HOME ASSISTANT. **Generic hygrostat**. [S. l.], [20--]b. Disponível em: <https://www.home-assistant.io/integrations/generic_hygrostat>."
    nota: "Controle de umidificador ou desumidificador por um sensor de umidade."
  - abnt: "HOME ASSISTANT. **Understanding automations**. [S. l.], [20--]c. Disponível em: <https://www.home-assistant.io/docs/automation/basics/>."
    nota: "Gatilho, condição e ação de uma automação."
  - abnt: "ESPHOME. **SHT3X-D temperature+humidity sensor**. [S. l.], [20--]. Disponível em: <https://esphome.io/components/sensor/sht3xd/>."
    nota: "Sensor de temperatura e umidade montado com ESP32 e o efeito do aquecedor interno nas leituras."
---

Automação na estufa serve para duas coisas: **fazer sozinho o que é repetitivo** (acender a luz, ligar o exaustor) e **avisar quando algo sai do normal** (calor, umidade, luz que não acendeu). Não é preciso começar pelo mais complexo: um timer bem escolhido já resolve o principal.

## Os níveis de automação

| Nível | O que faz | Para quem |
|---|---|---|
| **Timer de tomada** | Liga e desliga a luz no horário | Todo mundo. É o mínimo. |
| **Controlador com sonda** (termostato ou higrostato digital) | Liga o exaustor, o aquecedor ou o desumidificador conforme a temperatura ou a umidade | Quem tem calor, frio ou umidade fora da faixa |
| **Tomadas e sensores inteligentes** (Wi-Fi ou Zigbee) | Controle e gráficos pelo celular, alertas | Quem quer acompanhar de longe |
| **Home Assistant** | Junta tudo, com regras próprias, gráficos de VPD e alertas | Quem gosta de mexer e quer controle total |

## Timer

A luz é a única coisa que **não pode falhar** na floração: uma noite com a luz acesa, ou um horário que muda, pode estressar a planta e até causar hermafroditismo (veja [Sexagem]({{ '/sexagem/' | relative_url }})).

- **Timer digital** é mais preciso e permite vários horários. Prefira um com **bateria**, que não perde a programação quando falta energia.
- **Timer mecânico** (de pinos) é simples e confiável, mas tem resolução de 15 minutos e atrasa se faltar energia, porque para de girar.
- Confira a **corrente máxima** na etiqueta e deixe folga para a potência da luminária. Veja [Segurança elétrica]({{ '/seguranca-eletrica/' | relative_url }}).

## Termostato e higrostato

Um controlador com sonda liga e desliga um aparelho para manter a temperatura ou a umidade numa faixa. Para o aparelho não ficar ligando e desligando a cada segundo, ele trabalha com uma **tolerância** (histerese): por exemplo, liga o exaustor a 28 °C e só desliga a 26 °C.

Usos comuns:

- **Exaustor por temperatura:** sobe a exaustão quando esquenta. Deixe sempre uma **exaustão mínima** ligada, porque a planta precisa de ar novo mesmo quando a temperatura está boa. Veja [Ventilação]({{ '/ventilacao/' | relative_url }}).
- **Desumidificador por umidade**, no fim da floração, quando a umidade alta favorece o mofo. Veja [Temperatura e umidade]({{ '/temperatura_umidade/' | relative_url }}).
- **Aquecedor** pequeno, no inverno do Sul, com a sonda na altura das plantas.

## Home Assistant

O Home Assistant é um programa gratuito de automação residencial que roda num computador ou num Raspberry Pi em casa. Como montar o servidor, escolher sensores e mostrar o gráfico de VPD está na página [VPD e automação com Home Assistant]({{ '/vpdchart/' | relative_url }}). Aqui estão as automações mais úteis para a estufa.

<figure class="imagem">
  <a href="{{ '/assets/img/wiki/home-assistant-5pf8Ltj.png' | relative_url }}"><img src="{{ '/assets/img/wiki/home-assistant-5pf8Ltj.png' | relative_url }}" width="1580" height="655" loading="lazy" alt="Painel do Home Assistant com botões para ligar a estufa e a iluminação externa, gráficos de umidade e temperatura dos últimos minutos e as leituras atuais: 60,8% e 27,6 °C"></a>
  <figcaption>Um painel simples: botões para ligar a estufa e a iluminação externa, e os gráficos e leituras atuais de umidade e temperatura de um Sonoff THR316. Captura: <a href="https://www.reddit.com/user/tediousrock" rel="noopener">u/tediousrock</a>, 29 jan. 2023.</figcaption>
</figure>

### Sensores

Qualquer sensor de temperatura e umidade integrado ao Home Assistant serve. Quem gosta de montar pode usar um ESP32 com o **ESPHome** e um sensor Sensirion SHT3x, que se liga por I²C. O sensor tem um aquecedor interno opcional, que ajuda em ambientes com condensação, mas **sobe a temperatura lida e baixa a umidade** quando está ligado; ele vem desligado por padrão (ESPHome, [20--]).

### Exaustor como termostato

A integração **Generic thermostat** transforma um sensor de temperatura e uma tomada inteligente num termostato. Com a opção `ac_mode`, ela liga o aparelho quando a temperatura **passa** do alvo, como um ar-condicionado. É o que se quer para um exaustor. A tolerância padrão é de 0,3 °C para cima e para baixo, e dá para definir um tempo mínimo entre uma troca e outra, para poupar o motor (Home Assistant, [20--]a).

Ela pode ser criada pela interface em *Configurações → Dispositivos e serviços → Ajudantes*, ou em YAML, que tem mais opções:

```yaml
climate:
  - platform: generic_thermostat
    name: Exaustor da estufa
    heater: switch.tomada_exaustor      # a tomada que liga o exaustor
    target_sensor: sensor.estufa_temperatura
    ac_mode: true                       # liga quando passar do alvo
    target_temp: 26
    hot_tolerance: 1
    cold_tolerance: 1
    min_cycle_duration:
      minutes: 5
```

Cada termostato controla **uma tomada só**; para aquecer e esfriar, crie dois (Home Assistant, [20--]a).

### Desumidificador

A integração **Generic hygrostat** faz o mesmo com a umidade. Defina o tipo como `dehumidifier` para ligar o aparelho quando a umidade passar do alvo. A tolerância padrão é de 3 pontos percentuais (Home Assistant, [20--]b).

### Alertas

Uma automação tem um **gatilho** (o que dispara), **condições** opcionais (o que precisa ser verdade) e **ações** (o que fazer) (Home Assistant, [20--]c). Alertas que valem a pena:

- **Calor:** temperatura acima de 30 °C por mais de 10 minutos → notificação no celular.
- **Umidade alta na floração:** acima de 60% por mais de 30 minutos → notificação e liga o desumidificador.
- **Luz que não acendeu ou não apagou:** com uma tomada que mede consumo, compare a potência com o horário do timer. Potência perto de zero no horário de luz, ou acima de zero no escuro, é sinal de problema.
- **Sensor sem dados** há mais de uma hora: bateria fraca ou sensor fora do ar.

## Para não falhar

A automação tem que continuar funcionando quando a internet, o Wi-Fi ou o servidor caírem:

- **Luz no timer, não no servidor.** Use um timer físico ou uma tomada que guarde a programação nela mesma. O Home Assistant pode só vigiar.
- **O que acontece quando a energia volta?** Muitas tomadas inteligentes deixam escolher se voltam ligadas, desligadas ou no último estado. Para a luz na floração, o mais seguro é seguir o timer; para o exaustor, voltar **ligado**.
- **Exaustão mínima sempre ligada**, fora da automação ou com uma regra que nunca desliga de vez.
- **Teste:** desligue o servidor ou o roteador por um tempo e veja o que a estufa faz.
- **Tomadas inteligentes também têm limite de corrente.** Confira na etiqueta e não ligue a luminária, o aquecedor e o exaustor na mesma tomada. Veja [Segurança elétrica]({{ '/seguranca-eletrica/' | relative_url }}).

Com exaustor no termostato e luz no horário certo, a automação também ajuda a [gastar menos energia]({{ '/custo-energia/' | relative_url }}).
