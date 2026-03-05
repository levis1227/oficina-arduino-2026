# Oficina Arduino 

<p align="center">
  <img width="600" height="396" alt="image" src="https://github.com/user-attachments/assets/0f837d47-9287-4db0-b57a-9f863492b424" />
</p>

## Slides

Caso vocês desejem acompanhar a aula ou rever alguma informação, segue abaixo o link da apresentação:

[Canvas: Oficina Arduino](https://www.canva.com)

## Códigos 

Para agilizar o processo, deixamos abaixo todos os códigos que serão dados na segunda parte da aula, após a explicação dos materiais.

### 🚨 Exemplo 01: Piscar LED (Blink)

<p align="center">
<img width="600" height="450" alt="image" src="https://github.com/user-attachments/assets/f555c9aa-3744-4f23-a3d7-61b1993b7d86" />
<p>

#### 💻 Código Fonte

```zsh
/*******************************************************/
/* Exemplo 0 - Portas Digitais                         */
/* Programação de ligar e desligar um LED              */
/* utilizando uma porta PWM.                           */
/*******************************************************/

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

**Comentário**: O resistor é essencial aqui para não queimar o LED. Conecte o terminal longo (anodo) do LED ao resistor e o resistor ao pino 13.


#### 💻 Código Fonte

```zsh

/*******************************************************/
/* Exemplo 02 - Portas PWM                                */
/* Programação da intensidade do brilho de um LED      */
/* utilizando uma porta PWM.                           */
/*******************************************************/

/* Define a porta PWM 11 como pino do LED.             */
int pinoLed = 11; 

void setup() {
  /* Define o pino do LED como saída. */
  pinMode(pinoLed, OUTPUT);
}
void loop() {
  /* Alterna o brilho do LED com as intensidades       */
  /* definidas (0 à 255) em intervalos de 1 segundo.   */
  analogWrite(pinoLed, 5);
  delay(1000);
  analogWrite(pinoLed, 50);
  delay(1000);
  analogWrite(pinoLed, 100);
  delay(1000);
  analogWrite(pinoLed, 255);
  delay(1000);
}


```

### 🏃‍♂️ Exemplo 02: Sensor de Presença PIR (Digital Input)


<p align="center">
<img width="600" height="364" alt="image" src="https://github.com/user-attachments/assets/5d3e9aea-9885-4a7f-86b4-a673620913d0" />
</p>

#### 💻 Código Fonte

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

**Comentário**: Este código monitora o sensor. Quando ele detecta movimento, acende um LED de aviso.

### 🔊 Exemplo 03: Alarme com Buzzer (PWM/Tones)

<p align="center">
<img width="600" height="337" alt="image" src="https://github.com/user-attachments/assets/4c797582-f761-47b7-a6fd-612615d6072c" />
<p>

#### 💻 Código Fonte

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
**Comentário**: Aqui vamos fazer algo mais interessante que apenas um "bipe" contínuo: vamos variar a frequência para parecer uma sirene.

### ⚙️ Exemplo 04: Servo Motor

<p align="center">
<img width="600" height="410" alt="image" src="https://github.com/user-attachments/assets/d237e38c-e441-440b-aa03-61dab8ef3e94" />
<p>


#### 💻 Código Fonte

```zsh

#include <Servo.h>
Servo meuServo;

void setup() {
  meuServo.attach(9);
}

void loop() {
  meuServo.write(90);
  delay(1000);
  meuServo.write(0);
  delay(1000);
}

```

**Comentário**: Controle de posição de 0 a 180 graus.
