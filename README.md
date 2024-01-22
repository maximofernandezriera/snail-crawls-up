# Kata: Snail Crawls Up
https://www.codewars.com/kata/5b93fecd8463745630001d05

 - Clase y Solución

## Introducción
El kata "Snail Crawls Up" de Codewars, un problema clásico de simulación matemática. El objetivo es calcular el número de días que una caracola tardará en alcanzar la cima de una columna, subiendo durante el día y deslizándose un poco hacia abajo durante la noche.

## Descripción del Problema
Dados tres valores:
1. **Altura de la columna** (en metros).
2. **Distancia que la caracola sube durante el día** (en metros).
3. **Distancia que la caracola se desliza hacia abajo durante la noche** (en metros).

El reto es calcular el número de días necesarios para que la caracola alcance o supere la altura de la columna.

## Pseudocódigo
```plaintext
función díasParaAlcanzarCima(alturaColumna, subidaDiaria, deslizamientoNocturno)
    si subidaDiaria >= alturaColumna
        devolver 1
    fin si

    alturaActual = 0
    días = 0

    mientras alturaActual < alturaColumna
        días = días + 1
        alturaActual = alturaActual + subidaDiaria

        si alturaActual >= alturaColumna
            devolver días
        fin si

        alturaActual = alturaActual - deslizamientoNocturno
    fin mientras
fin función
```

## Código en Java
```java
public class SnailClimb {

    public static int daysToReachTop(int columnHeight, int dayClimb, int nightSlide) {
        if (dayClimb >= columnHeight) {
            return 1;
        }

        int currentHeight = 0;
        int days = 0;

        while (currentHeight < columnHeight) {
            days++;
            currentHeight += dayClimb;

            if (currentHeight >= columnHeight) {
                return days;
            }

            currentHeight -= nightSlide;
        }

        return days;
    }

    public static void main(String[] args) {
        int columnHeight = 10; // ejemplo: altura de la columna
        int dayClimb = 3;     // ejemplo: subida diaria
        int nightSlide = 1;   // ejemplo: deslizamiento nocturno

        int result = daysToReachTop(columnHeight, dayClimb, nightSlide);
        System.out.println("La caracola alcanzará la cima en " + result + " días.");
    }
}
```

Esta solución en Java sigue la lógica del pseudocódigo para calcular el número de días que la caracola tarda en alcanzar la cima, utilizando un bucle `while`.

---
