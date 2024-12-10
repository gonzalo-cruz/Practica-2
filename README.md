# Práctica 2: Inferencia Estadística

**Grado en Ciencia e Ingeniería de Datos, Universidad Rey Juan Carlos**  
Autor: Isaac Martín  
Fecha: 2024-11-13

---

## Introducción

Esta práctica aborda diferentes métodos para calcular el tamaño muestral necesario al comparar una proporción con un valor de referencia. Seguiremos los argumentos presentados por Whitehead (1983) para derivar fórmulas a partir de una teoría unificada, aplicable en diseños experimentales.

---

## Objetivos

### Parte 1: Derivaciones teóricas

1. **Log-verosimilitud para una proporción**  
   - Demostrar que la log-verosimilitud de \( p \) basada en \( n \) observaciones sigue la fórmula:
     \[
     \ell(p) = r \cdot \log\left(\frac{p}{1-p}\right) + n \cdot \log(1-p)
     \]
     Donde \( r \) es la suma de las respuestas en \( n \) observaciones.

   - Determinar la distribución de la suma de \( n \) variables aleatorias Bernoulli \( i.i.d. \).

2. **Información de Fisher**  
   - Probar que la información de Fisher para una muestra de tamaño \( n \) en una variable Bernoulli con parámetro \( p \) es igual a:
     \[
     \frac{n}{p(1-p)}
     \]

3. **Cálculo de \( Z \) y \( V \)**  
   Derivar las expresiones de \( Z \) y \( V \) para las siguientes parametrizaciones:
   - \( \theta = \log\left(\frac{p(1-p_0)}{p_0(1-p)}\right) \)
   - \( \theta = p - p_0 \)
   - \( \theta = \arcsin(\sqrt{p}) - \arcsin(\sqrt{p_0}) \)

### Parte 2: Contraste de hipótesis

4. Implementar un código en R para calcular \( Z \) y \( V \) en cada una de las parametrizaciones propuestas.

5. Simular el siguiente contraste de hipótesis con una muestra de tamaño 1000:
   - \( H_0 : p = 0.3 \)
   - \( H_1 : p > 0.3 \)

### Parte 3: Tamaño muestral

6. Derivar una fórmula para el tamaño muestral necesario para un contraste con nivel de significancia \( \alpha \) y potencia \( 1-\beta \) utilizando:
   \[
   V = \left(\frac{z_{\alpha/2} + z_{\beta}}{\theta_R}\right)^2
   \]

7. Calcular el tamaño muestral necesario para detectar una diferencia entre \( p_0 = 0.003 \) y \( p = 0.006 \) con:
   - \( \alpha = 0.025 \)
   - Potencia = 0.80

### Parte 4: Evaluación de potencia y error

8. Estimar los errores tipo I y la potencia del contraste basado en \( Z \) y \( V \) para los tamaños muestrales y parametrizaciones calculados anteriormente.

9. Aplicar los siguientes métodos de contraste:
   - Test de chi-cuadrado sin corrección de continuidad (`chisq.test`).
   - Prueba exacta (`binom.test`).

10. Proponer y escribir el código en R para una prueba no paramétrica adecuada para comparar una proporción con un valor de referencia.

---

## Referencias

Whitehead, J., & Stratton, I. (1983). *Group sequential clinical trials with triangular continuation regions*. Biometrics, 227-236.

---

## Notas adicionales

- Cada ejercicio debe incluir explicaciones claras y concisas del razonamiento matemático y estadísticas utilizadas.
- Proveer comentarios detallados en el código R implementado para asegurar su comprensión y replicabilidad.
