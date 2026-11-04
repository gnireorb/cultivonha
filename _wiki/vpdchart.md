---
title: VPD e automação com Home Assistant
titulo_curto: VPD
description: O que é o VPD, as faixas ideais em cada fase, como medir certo e como automatizar o acompanhamento com o Home Assistant.
atualizado: '2026-10-26'
origem:
  url: "https://www.reddit.com/r/Cultivonha/wiki/index/vpdchart"
  titulo: Wiki r/Cultivonha — index/vpdchart
  licenca: Conteúdo da comunidade r/Cultivonha
  importado_em: 2026-10-16
editores:
- tediousrock
revisado: false
revisao: Texto revisado e ampliado em outubro de 2026, com base nas referências listadas.
fontes_acesso: '2026-10-16'
fontes:
- abnt: "DAVIS, D. VPD chart & calculator: optimize every growth stage. **Hydrobuilder Learning Center**, [S. l.], 7 jul. 2026. Disponível em: <https://learn.hydrobuilder.com/vapor-pressure-deficit-vpd/>."
  nota: Definição, faixas por fase e efeitos de VPD baixo ou alto.
- abnt: "VPDCHART. **vpdchart-card**: VPD chart card for Home Assistant. [S. l.]: GitHub, [20--]. Disponível em: <https://github.com/vpdchart/vpdchart-card>."
- abnt: "HOME ASSISTANT COMMUNITY STORE. **Download HACS**. [S. l.], [20--]. Disponível em: <https://hacs.xyz/docs/use/download/download/>."
---

## O que é

VPD é a sigla em inglês para *vapor pressure deficit*, ou **déficit de pressão de vapor**. Ele mostra quanto o ar está "puxando" água da planta e é medido em quilopascal (kPa).

O VPD junta temperatura e umidade num número só. A temperatura define quanta água o ar consegue segurar; a umidade diz quanta ele já segura. A diferença é o que a planta sente (Davis, 2026):

- **VPD baixo** (ar úmido demais): a planta transpira pouco, absorve menos nutrientes, cresce devagar e fica mais sujeita a fungos.
- **VPD alto** (ar seco demais): a planta fecha os estômatos para não perder água, a fotossíntese para e aparecem pontas queimadas e folhas murchas.

## Faixas por fase

| VPD | Uso |
|---|---|
| abaixo de 0,4 kPa | Perigo: transpiração muito baixa |
| 0,4 a 0,8 kPa | Clones, mudas e começo do vegetativo |
| 0,8 a 1,2 kPa | Fim do vegetativo e começo da floração |
| 1,2 a 1,6 kPa | Meio e fim da floração |
| acima de 1,6 kPa | Perigo: transpiração excessiva |

Exemplos com a folha 2 °C mais fria que o ar:

- 25 °C e 70% de umidade dão cerca de 0,6 kPa (bom para clones);
- 26 °C e 60% de umidade, cerca de 1,0 kPa (bom para o vegetativo);
- 26 °C e 50% de umidade, cerca de 1,3 kPa (bom para a floração).

## Medir certo

- O sensor fica **na altura do topo das plantas**, solto no ar.
- **Nunca no solo nem perto dos vasos**: a evaporação do substrato faz a umidade aparecer alta demais, e o VPD calculado sai errado.
- **Longe do vento direto** do ventilador, que distorce a leitura de umidade.
- **Sem luz direta** no sensor, que esquenta e mostra uma temperatura maior que a real.

Mais detalhes em [Temperatura e umidade]({{ '/temperatura_umidade/' | relative_url }}).

## Calcular sem automação

1. Anote a temperatura e a umidade do ar.
2. Estime a temperatura da folha. Com a luz bem posicionada, ela costuma ficar **2 °C a 3 °C abaixo** do ar. Um termômetro infravermelho mede isso direto; faça algumas leituras em pontos diferentes da copa e use a média.
3. Coloque os três valores no site [vpdchart.com](https://vpdchart.com/) ou no [aplicativo](https://vpdchart.com/apps.html).

## Automatizar com o Home Assistant

Esta seção mostra como acompanhar o VPD. Para controlar o exaustor e o desumidificador e criar alertas, veja [Automação]({{ '/automacao/' | relative_url }}).

### Sensores

Qualquer sensor de temperatura e umidade integrado ao Home Assistant funciona. Dois usados pela comunidade:

- **Sonoff SNZB-02**: precisa de um hub ou adaptador Zigbee (Zemismart foi o recomendado).
- **Sonoff THS01**: Wi-Fi. Foi o mais preciso nos testes de quem escreveu esta seção.

### Programas

- **Home Assistant OS**, rodando num Raspberry Pi, num computador ou notebook antigo ou num servidor de casa.
- **[HACS](https://hacs.xyz/docs/use/download/download/)**, a loja de integrações da comunidade para o Home Assistant.
- **[AlexxIT/SonoffLAN](https://github.com/alexxit/sonofflan?tab=readme-ov-file#installation)**, para dispositivos Sonoff que só funcionam com o app eWeLink.
- **[Zigbee2MQTT](https://github.com/zigbee2mqtt/hassio-zigbee2mqtt)** (ou a integração ZHA, que já vem no Home Assistant), para sensores Zigbee.
- **[vpdchart-card](https://github.com/vpdchart/vpdchart-card)**, que desenha o gráfico de VPD no painel.

### Resultado

Depois de instalar o HACS e o vpdchart-card, adicione os sensores ao cartão:

![Gráfico de VPD no Home Assistant OS, com a leitura atual de temperatura e umidade marcada sobre as faixas de VPD](/assets/img/wiki/9foy13o353ga1.jpg)

### Exemplo de configuração do cartão

```yaml
title: Estufa vegetativo
crop: Cannabis

air_temp: sensor.snzb_02_temperature
air_rh: sensor.snzb_02_humidity

# Sem sensor de folha separado: usa a temperatura do ar com 2 °C a menos
leaf_temp: sensor.snzb_02_temperature
leaf_temp_offset: -2
```

Troque os nomes `sensor.snzb_02_...` pelos nomes dos seus sensores no Home Assistant.
