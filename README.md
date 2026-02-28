# Oficina Arduino 
<p align="center">
<img width="300" height="300" alt="image" src="https://github.com/user-attachments/assets/c740f886-f07c-46d6-9779-dca299c9b21c" />
<p>

## Slides

Caso vocês queiram acompanhar a aula ou rever alguma informação, segue abaixo o link da apresentação:

[Canvas: Oficina Arduino](https://www.canva.com/design/DAHCkH_S40c/RCqKfZIpbqiSRn1-AoyYZQ/edit?utm_content=DAHCkH_S40c&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)

## Códigos 

Para agilizar o processo, deixamos abaixo todos os códigos que seram dados na segunda parte da aula, após a explicação dos materiais.

### Exemplo 01: Piscar LED (Digital Output)

O resistor é essencial aqui para não queimar o LED. Conecte o terminal longo (anodo) do LED ao resistor e o resistor ao pino 13.

<p align="center">
<img width="600" height="450" alt="image" src="https://github.com/user-attachments/assets/f555c9aa-3744-4f23-a3d7-61b1993b7d86" />
<p>



```zsh

void setup() {
  pinMode(13, OUTPUT); // Define o pino 13 como saída
}

void loop() {
  digitalWrite(13, HIGH); // Liga o LED
  delay(1000);            // Espera 1 segundo
  digitalWrite(13, LOW);  // Desliga o LED
  delay(1000);            // Espera 1 segundo
}

```

### Exemplo 02: Sensor de Presença PIR (Digital Input)

Este código monitora o sensor. Quando ele detecta movimento, acende um LED de aviso.

```zsh

int pinoSensor = 2;
int pinoLED = 13;

void setup() {
  pinMode(pinoSensor, INPUT);
  pinMode(pinoLED, OUTPUT);
}

void loop() {
  int movimento = digitalRead(pinoSensor); // Lê o estado do sensor
  
  if (movimento == HIGH) {
    digitalWrite(pinoLED, HIGH); // Acende se houver movimento
  } else {
    digitalWrite(pinoLED, LOW);  // Apaga se estiver tudo parado
  }
}

```

### Exemplo 03: Alarme com Buzzer (PWM/Tones)

Aqui vamos fazer algo mais interessante que apenas um "bipe" contínuo: vamos variar a frequência para parecer uma sirene.


```zsh

int pinoBuzzer = 8;

void setup() {
  pinMode(pinoBuzzer, OUTPUT);
}

void loop() {
  // Faz um som de 1000Hz (agudo) por 500ms
  tone(pinoBuzzer, 1000); 
  delay(500);
  
  // Faz um som de 500Hz (mais grave) por 500ms
  tone(pinoBuzzer, 500);
  delay(500);
  
  noTone(pinoBuzzer); // Para o som (opcional)
}

```
