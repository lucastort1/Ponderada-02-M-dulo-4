# Ponderada-02-M-dulo-4

```
int ledVerde = 11; 
int ledAmarelo = 10;
int ledVermelho = 9;
int buzzer = 8;  // Define o pino do buzzer

void setup() {
  pinMode(ledVerde, OUTPUT);
  pinMode(ledAmarelo, OUTPUT);
  pinMode(ledVermelho, OUTPUT);
  pinMode(buzzer, OUTPUT);  // Configura o pino do buzzer como saída
}

void loop() {
  // Liga o LED vermelho
  digitalWrite(ledVermelho, HIGH);
  delay(6000);
  digitalWrite(ledVermelho, LOW);

  // Liga o LED amarelo e faz o buzzer apitar continuamente
  digitalWrite(ledAmarelo, HIGH);
  for (int i = 0; i < 20; i++) {  // 20 ciclos para cobrir 2 segundos (100ms por ciclo)
    digitalWrite(buzzer, HIGH);
    delay(50);  // Buzzer ligado por 50ms
    digitalWrite(buzzer, LOW);
    delay(50);  // Buzzer desligado por 50ms
  }
  digitalWrite(ledAmarelo, LOW);

  // Liga o LED verde por 2 segundos
  digitalWrite(ledVerde, HIGH);
  delay(2000);
  digitalWrite(ledVerde, LOW);

  delay(500);  // Atraso de 0,5 segundo

  // Liga o LED verde novamente por 2 segundos
  digitalWrite(ledVerde, HIGH);
  delay(2000);
  digitalWrite(ledVerde, LOW);

  // Liga o LED amarelo novamente por 2 segundos, com o buzzer apitando
  digitalWrite(ledAmarelo, HIGH);
  for (int i = 0; i < 20; i++) {  // 20 ciclos para cobrir 2 segundos
    digitalWrite(buzzer, HIGH);
    delay(50);  // Buzzer ligado por 50ms
    digitalWrite(buzzer, LOW);
    delay(50);  // Buzzer desligado por 50ms
  }
  digitalWrite(ledAmarelo, LOW);
}
```
<img title="Print Código" src="/imagem prototipo.png">

Vídeo de funcionamento disponível no repositório

&nbsp;&nbsp;&nbsp;&nbsp;A montagem desse protótipo foi realizada primeiro com o uso do tinkercad, para que pudesse ser testado sem nenhum risco de danificar algum componente físico e posteriormente foi passado para um modelo físico parecido com o online. Para o desenvolvimento deste projeto, foi montado um sistema de semáforo com três LEDs (verde, amarelo e vermelho) e um buzzer para emitir um alerta sonoro quando o LED amarelo é aceso, assim indicando ao motorista que o semáfaro vai fechar ou abrir.

&nbsp;&nbsp;&nbsp;&nbsp;Para realizar a montagem do sistema de semáforo com alerta sonoro, começamos configurando os LEDs. O LED verde foi conectado ao pino digital 11 do Arduino, o LED amarelo ao pino digital 10 e o LED vermelho ao pino digital 9. Para proteger os LEDs, foi adicionado um resistor de 220Ω ao terminal positivo (ânodo) de cada um, limitando a corrente e evitando danos. Os terminais negativos (cátodos) foram conectados ao terra (GND) do Arduino, utilizando uma protoboard para facilitar as conexões e organização do circuito.

&nbsp;&nbsp;&nbsp;&nbsp;Em seguida, conectamos o buzzer ao Arduino, utilizando o pino digital 8. O terminal positivo do buzzer foi ligado diretamente a esse pino, enquanto o terminal negativo foi conectado ao GND, permitindo o controle do buzzer através da programação.

&nbsp;&nbsp;&nbsp;&nbsp;Com o hardware montado, passamos para a programação do Arduino. O código foi desenvolvido para controlar o tempo de ativação de cada LED e a intermitência do buzzer. Quando o LED vermelho acende, ele permanece ativo por 6 segundos. Após esse período, o LED amarelo acende por 2 segundos enquanto o buzzer emite bipes intermitentes. Em seguida, o LED verde acende por 2 segundos, apaga brevemente por 0,5 segundo e acende novamente por mais 2 segundos. Essa sequência é repetida continuamente, simulando um ciclo de semáforo com sinalização sonora no estado vermelho.

&nbsp;&nbsp;&nbsp;&nbsp;Essa montagem, além de ilustrar o funcionamento de um semáforo básico, oferece uma experiência completa de sinalização visual e sonora, útil para diversos contextos de controle de tráfego e segurança em áreas controladas.

| Materiais | Quantidade | 
| --------- | ---------- |
| Arduino Uno |     1     |
| LED Vermelho |     1     |
| LED Verde |     1     |
| LED Amarelo |     1     |
| Resistores (220) |     3     |
| Buzzer |     1     |
| Fios Jumpers |     12    |
| Protoboard |     1     |
