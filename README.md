# Arduino Memoria Sram

```c++
int freeRam()
{
  extern int __heap_start, *__brkval;
  int v;
  return (int) &v - (__brkval == 0 ? (int) &__heap_start : (int) __brkval);
}

void setup()
{
  Serial.begin(9600);
  Serial.println(freeRam());
}

void loop()
{
}
```

<img src="https://github.com/IDiegoUlises/Arduino-Memoria-Sram/blob/main/Images/Son-Diferentes.jpg" width="1000" height="600" />
