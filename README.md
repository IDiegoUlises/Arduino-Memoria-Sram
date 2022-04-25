# Arduino Memoria Sram
Como ver la memoria sram del arduino y como ahorrar la memoria volatil

Encontre este codigo mira la memoria ram pero no es preciso pero se acerca al valor buscar otra forma que sea exacta

```c++
void setup(){
  Serial.begin(9600);
  Serial.println("Comienza...");
}

void loop(){
  Serial.println(freeRam());
  
  delay(30000);
}

int freeRam () 
{
  extern int __heap_start, *__brkval; 
  int v; 
  return (int) &v - (__brkval == 0 ? (int) &__heap_start : (int) __brkval); 
}
```
