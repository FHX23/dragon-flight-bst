# 🐉 Dragon Flight Reservation System

> Sistema interactivo de gestión y reserva de vuelos implementado en **C**, utilizando una estructura de datos de **Árbol Binario de Búsqueda (BST)** con gestión dinámica de memoria.

[![Language: C99](https://img.shields.io/badge/Language-C99-blue.svg)](https://en.wikipedia.org/wiki/C99)
[![Data Structure](https://img.shields.io/badge/Data%20Structure-BST-green.svg)](#-estructura-de-datos-y-complejidad)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

---

## 📌 Descripción

El sistema simula un servicio de reserva y despacho de vuelos (temática fantástica de transporte aéreo). Cada reserva se modela como un nodo dentro de un **Árbol Binario de Búsqueda (Binary Search Tree)** ordenado por su número identificador único de reserva (`reservationNumber`).

Esto permite operaciones de búsqueda, inserción y cancelación eficientes en tiempo promedio logarítmico $\mathcal{O}(\log n)$, además de recorridos en orden ascendente $\mathcal{O}(n)$ para reportes consolidados de pasajeros.

---

## ⚙️ Características

- **Registro de Reservas:** Inserción recursiva en el BST manteniendo la propiedad de orden binario.
- **Cancelación de Reservas:** Eliminación de nodos considerando los 3 casos clásicos (nodo hoja, nodo con un solo hijo y nodo con dos hijos mediante reemplazo por el sucesor en in-orden).
- **Búsqueda por ID:** Acceso directo en tiempo logarítmico a los datos del pasajero y su destino asignado.
- **Búsqueda por Destino:** Recorrido y filtrado para mostrar pasajeros asignados a un destino en particular.
- **Listado Ordenado (In-Order Traversal):** Impresión de todas las reservas ordenadas ascendentemente por número de reserva.
- **Gestión Limpia de Memoria:** Recorrido en post-orden (`treeFree`) para liberar recursivamente todos los nodos asignados dinámicamente con `malloc`.

---

## 📊 Estructura de Datos y Complejidad

### Nodo de Reserva (`BookingNode`)

```c
struct BookingNode {
    int reservationNumber;
    char namePassanger[50];
    char destinationPassanger[50];
    struct BookingNode *left;
    struct BookingNode *right;
};
```

### Análisis de Complejidad Temporal

| Operación | Caso Promedio | Peor Caso (Árbol degenerado) |
|---|---|---|
| Inserción (`insertNode`) | $\mathcal{O}(\log n)$ | $\mathcal{O}(n)$ |
| Búsqueda por ID (`searchNode`) | $\mathcal{O}(\log n)$ | $\mathcal{O}(n)$ |
| Cancelación (`deleteNode`) | $\mathcal{O}(\log n)$ | $\mathcal{O}(n)$ |
| Búsqueda por Destino (`SearchAndPrintDestiny`) | $\mathcal{O}(n)$ | $\mathcal{O}(n)$ |
| Recorrido In-Order (`inOrder`) | $\mathcal{O}(n)$ | $\mathcal{O}(n)$ |
| Liberación de memoria (`treeFree`) | $\mathcal{O}(n)$ | $\mathcal{O}(n)$ |

---

## 🚀 Compilación y Ejecución

Puedes compilar el proyecto utilizando cualquier compilador compatible con C99 o superior (`gcc`, `clang`, MinGW, etc.):

```bash
# Compilación
gcc -Wall -Wextra -std=c99 TareaReservas.c -o reservas

# Ejecución en Linux / macOS
./reservas

# Ejecución en Windows
reservas.exe
```

---

## 👥 Autores

Desarrollado en colaboración por:
- **Matias Arenas** ([@FHX23](https://github.com/FHX23))
- **Saúl Muñoz**
