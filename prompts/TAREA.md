# Tarea: Mi prompt avanzado

## Tarea elegida
Voy a crear un sistema para calcular el promedio de notas y saber si el estudiante aprueba o reprueba.

## Versión 1: Prompt básico

> **Le envié:**
Hazme un programa que calcule promedios de notas.

> **Me respondió:**
Claro, aquí tienes un ejemplo sencillo:

```python
nota1 = 10
nota2 = 12
promedio = (nota1 + nota2) / 2
print(promedio)
```

## Qué mejoró: 
Funciona, pero nada más.
## Qué faltó:
No dijo en qué lenguaje, no hay reglas de aprobación, no guarda el nombre del estudiante. Fue muy general.


## Versión 2 — Agrego rol y contexto
> **Le envié:**
Actúa como programador en Java.

Contexto: Una escuela necesita calcular promedios. Se aprueba con nota mayor o igual a 11.
Diseña las clases para gestionar estudiantes y calcular si aprueban.
> **Me respondió:**

Aquí tienes la estructura:
```
public class Estudiante {
    private String nombre;
    private double nota1, nota2, nota3, nota4;

    public double calcularPromedio() {
        return (nota1 + nota2 + nota3 + nota4) / 4;
    }

    public boolean aprueba() {
        return calcularPromedio() >= 11;
    }
}
```
## Qué mejoró:
 Ya usa Java, sabe que aprueba con 11 y tiene la clase bien pensada.
## Qué faltó:
 No tiene constructor para poner los datos, no muestra mensajes, no hay ejemplo de cómo usarlo.

## Versión 3 — Prompt final con 3 técnicas 
> **Le envié:**
<rol>Actúa como desarrollador Java con experiencia en sistemas escolares.</rol>
<contexto>El sistema registra nombre y 4 notas por estudiante. Promedio = suma / 4. Se aprueba con ≥ 11.</contexto>
<tarea>Piensa paso a paso: primero define la clase Estudiante, luego el cálculo del promedio, y al final el programa completo con un ejemplo de uso.</tarea>
<formato>Devuelve solo el código Java listo para copiar. Sin explicaciones extra.</formato>

> **Me respondió:**

public class Estudiante {
    private String nombre;
    private double n1, n2, n3, n4;

    public Estudiante(String nombre, double n1, double n2, double n3, double n4) {
        this.nombre = nombre;
        this.n1 = n1;
        this.n2 = n2;
        this.n3 = n3;
        this.n4 = n4;
    }

    public double calcularPromedio() {
        return (n1 + n2 + n3 + n4) / 4;
    }

    public String verResultado() {
        double prom = calcularPromedio();
        return prom >= 11 ? nombre + " aprueba con " + prom : nombre + " reprueba con " + prom;
    }

    public static void main(String[] args) {
        Estudiante e = new Estudiante("María", 12, 14, 10, 13);
        System.out.println(e.verResultado());
    }
}


| Parte del prompt | Técnica aplicada |
|---|---|
| Actúa como desarrollador Java | Rol específico |
| Piensa paso a paso | Descomposición / Chain of Thought |
| Devuelve solo el código | Formato definido |


| ¿Qué revisar? | Cumple (Sí / No) |
|---|---|
| ¿El código es en Java? | Sí |
| ¿Calcula el promedio correctamente? | Sí |
| ¿Verifica si aprueba o reprueba? | Sí |
| ¿El código es claro y legible? | Sí |