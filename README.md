# Fundamentos da Internet das Coisas

## O que é IoT?

Internet das Coisas é o conceito de conectar objetos físicos à internet para coletar, transmitir e processar dados.

## Componentes

- Dispositivos
- Sensores
- Atuadores
- Rede
- Plataforma Cloud
- Usuário Final

## Exemplos

- Casas inteligentes
- Agricultura inteligente
- Indústria 4.0
- Saúde conectada
- Cidades inteligentes

  # Fundamentos do Arduino

## O que é Arduino?

Arduino é uma plataforma de prototipagem eletrônica open source baseada em hardware e software.

## Estrutura

- Microcontrolador
- Pinos digitais
- Pinos analógicos
- Alimentação
- Comunicação Serial

## Exemplo

```cpp
void setup() {
  pinMode(13, OUTPUT);
}

void loop() {
  digitalWrite(13, HIGH);
  delay(1000);
  digitalWrite(13, LOW);
  delay(1000);
}
```

# Projeto: Monitoramento de Temperatura

## Objetivo

Ler temperatura usando DHT11 e exibir no monitor serial.

## Componentes

- Arduino Uno
- Sensor DHT11
- Jumpers

## Código

```cpp
#include <DHT.h>

#define DHTPIN 2
#define DHTTYPE DHT11

DHT dht(DHTPIN, DHTTYPE);

void setup() {
  Serial.begin(9600);
  dht.begin();
}

void loop() {
  float temp = dht.readTemperature();

  Serial.print("Temperatura: ");
  Serial.println(temp);

  delay(2000);
}
```

---

# 06-Comunicacao/mqtt.md

markdown
# MQTT

MQTT é um protocolo leve utilizado em IoT.

## Componentes

- Publisher
- Broker
- Subscriber

## Fluxo

Sensor → Publicação → Broker → Assinante

## Vantagens

- Baixo consumo
- Pouca largura de banda
- Alta escalabilidade

# Cloud IoT

A nuvem permite armazenar e analisar dados coletados pelos dispositivos.

## Funções

- Armazenamento
- Dashboards
- Análise
- Automação

## Plataformas

- ThingSpeak
- Firebase
- AWS IoT
- Azure IoT

  # Segurança em IoT

## Principais riscos

- Invasão de dispositivos
- Roubo de dados
- Ataques DDoS

## Boas práticas

- HTTPS
- TLS
- Atualizações OTA
- Senhas fortes
- Certificados digitais

  # Projeto Final

Sistema completo de monitoramento ambiental.

## Funcionalidades

- Leitura de temperatura
- Leitura de umidade
- Envio para nuvem
- Dashboard web
- Alertas automáticos

## Arquitetura

Sensor → Arduino/ESP32 → MQTT → Cloud → Dashboard

---

## Conclusão

A Internet das Coisas integra sensores, dispositivos embarcados, redes de comunicação e plataformas em nuvem para criar sistemas inteligentes. O fluxo de dados conecta o mundo físico ao digital, permitindo monitoramento, automação e tomada de decisão baseada em dados em tempo real.
