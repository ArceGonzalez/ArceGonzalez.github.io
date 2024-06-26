---
title: Patron Estrategia
date: '2024-06-25 22:15:22'
comments: true
categories: [Programacion]
tags: [DesignPatterns]
---


## Que es el patron estrategia?
- es un patron de disenio de comportamiento que te permite definir una familia de algoritmos, ponerlos en clases separadas y hacer sus objetos intercambiables
- El patrón estrategia es como tener diferentes maneras de hacer una tarea y poder elegir cuál usar según la situación. Es como tener varias estrategias guardadas y poder cambiar entre ellas sin problema.

**Ejemplo del patrón Estrategia:**

Imagina que estás jugando un juego de estrategia donde puedes elegir cómo quieres atacar a tus enemigos. Puedes usar diferentes tácticas según el tipo de enemigo o la situación en el juego. Por ejemplo:

1. **Estrategia de Ataque Directo:** Envías a tus tropas directamente al frente para enfrentar al enemigo sin rodeos.
   
2. **Estrategia de Emboscada:** Envías a un grupo pequeño de unidades para rodear al enemigo y atacar desde varios lados.

3. **Estrategia de Defensa:** En lugar de atacar, fortificas tus posiciones y esperas a que el enemigo se acerque para contraatacar.

En este ejemplo, cada estrategia (ataque directo, emboscada, defensa) es como una "estrategia" en el patrón estrategia. Dependiendo de cómo evoluciona el juego o qué tipo de enemigo te enfrentas, puedes cambiar entre estas estrategias para adaptarte mejor a la situación y mejorar tus probabilidades de ganar.

## Ejemplo de aplicacion del patron estrategia en caso de comercio electronico

Imagina que estás desarrollando el sistema de pago para un sitio web de comercio electrónico. Tienes diferentes opciones de pago disponibles para los clientes: tarjeta de crédito, PayPal y transferencia bancaria. Cada método de pago tiene su propio algoritmo de procesamiento y validación específico.

En lugar de implementar cada método de pago directamente en el código principal del sistema de compras, puedes aplicar el patrón Strategy de la siguiente manera:

1. **Definición de la interfaz Strategy:**
   Define una interfaz común llamada `PaymentStrategy` que declara un método `processPayment(amount)` que todos los métodos de pago deben implementar.

   ```java
   public interface PaymentStrategy {
       void processPayment(double amount);
   }
   ```

2. **Implementación de las estrategias concretas:**
   Crea clases concretas que implementen esta interfaz para cada método de pago específico.

   ```java
   public class CreditCardPaymentStrategy implements PaymentStrategy {
       @Override
       public void processPayment(double amount) {
           // Implementación específica para pagos con tarjeta de crédito
           System.out.println("Procesando pago con tarjeta de crédito por $" + amount);
           // Lógica adicional para procesar el pago con tarjeta de crédito
       }
   }

   public class PayPalPaymentStrategy implements PaymentStrategy {
       @Override
       public void processPayment(double amount) {
           // Implementación específica para pagos con PayPal
           System.out.println("Procesando pago con PayPal por $" + amount);
           // Lógica adicional para procesar el pago con PayPal
       }
   }

   public class BankTransferPaymentStrategy implements PaymentStrategy {
       @Override
       public void processPayment(double amount) {
           // Implementación específica para pagos con transferencia bancaria
           System.out.println("Procesando pago con transferencia bancaria por $" + amount);
           // Lógica adicional para procesar el pago con transferencia bancaria
       }
   }
   ```

3. **Contexto que utiliza la estrategia:**
   En la clase principal del sistema de compras, puedes tener un campo que sea del tipo `PaymentStrategy` para almacenar la estrategia de pago seleccionada por el cliente.

   ```java
   public class ShoppingCart {
       private PaymentStrategy paymentStrategy;

       public void setPaymentStrategy(PaymentStrategy paymentStrategy) {
           this.paymentStrategy = paymentStrategy;
       }

       public void checkout(double amount) {
           // Aquí se usa la estrategia de pago seleccionada
           paymentStrategy.processPayment(amount);
       }
   }
   ```

Con esta implementación:

- Puedes cambiar dinámicamente entre los diferentes métodos de pago sin alterar el código del sistema de compras principal.
- Facilita la adición de nuevos métodos de pago en el futuro sin afectar el código existente, siempre y cuando sigan la interfaz `PaymentStrategy`.
- Cada método de pago encapsula su propia lógica, promoviendo la cohesión y el principio de responsabilidad única.

En resumen, el patrón Strategy en este ejemplo permite manejar diferentes algoritmos de procesamiento de pago de manera flexible y mantenible en un sistema de comercio electrónico.

 