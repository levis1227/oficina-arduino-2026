

<p align="center">
  <img width="1600" height="488" alt="image (1)" src="https://github.com/user-attachments/assets/e9de7492-486d-4702-9dfe-d948977b3472" />
</p>


# Oficina Arduino 


## Slides

Caso vocês queiram acompanhar a aula ou rever alguma informação, segue abaixo o link da apresentação:

[Canvas: Oficina Arduino](https://www.canva.com/design/DAHCkH_S40c/RCqKfZIpbqiSRn1-AoyYZQ/edit?utm_content=DAHCkH_S40c&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)

## Códigos 

Para agilizar o processo, deixamos abaixo todos os códigos que seram dados na segunda parte da aula, após a explicação dos materiais.

### 🚨 Exemplo 01: Piscar LED (Blink)

<p align="center">
<img width="600" height="450" alt="image" src="https://github.com/user-attachments/assets/f555c9aa-3744-4f23-a3d7-61b1993b7d86" />
<p>

#### 💻 Código Fonte

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

**Comentário**: O resistor é essencial aqui para não queimar o LED. Conecte o terminal longo (anodo) do LED ao resistor e o resistor ao pino 13.

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
