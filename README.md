# Arduino Memoria Sram
La memoria Sram (memoria estatica de acceso aleatorio) es el espacio donde el sketch del programa almacenan y manipulan variables al ejecutarse. La informacion guardada en esta memoria sera eliminada cuando Arduino pierda la
alimentacion, estas memorias son de acceso aleatorio, lo que significa que las posiciones en la memoria pueden ser escritas o leidas en cualquier orden


# Codigo que muestra la memoria Sram
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
