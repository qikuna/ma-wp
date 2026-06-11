# Tabla de Transformadas de Fourier (Convención Simétrica Unitaria)

Definiciones base empleadas para construir las tablas:

* **Transformada Directa:** $\hat{f}(\omega) = \mathcal{F}\{f(t)\} = \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{\infty} f(t) e^{-i\omega t} dt$
* **Transformada Inversa:** $f(t) = \mathcal{F}^{-1}\{\hat{f}(\omega)\} = \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{\infty} \hat{f}(\omega) e^{i\omega t} d\omega$

---

## 1. Propiedades Operacionales

| Propiedad | Función en el tiempo $f(t), g(t)$ | Transformada en frecuencia $\hat{f}(\omega), \hat{g}(\omega)$ |
| :--- | :--- | :--- |
| **Linealidad** | $a f(t) + b g(t)$ | $a \hat{f}(\omega) + b \hat{g}(\omega)$ |
| **Desplazamiento temporal** | $f(t - t_0)$ | $e^{-i\omega t_0} \hat{f}(\omega)$ |
| **Desplazamiento frecuencial** | $e^{i\omega_0 t} f(t)$ | $\hat{f}(\omega - \omega_0)$ |
| **Escalamiento** | $f(at)$ | $\frac{1}{\vert a \vert} \hat{f}\left(\frac{\omega}{a}\right)$ |
| **Simetría (Dualidad)** | $\hat{f}(t)$ | $f(-\omega)$ |
| **Conjugación** | $f^*(t)$ | $\hat{f}^*(-\omega)$ |
| **Derivación en el tiempo** | $f^{(n)}(t) = \frac{d^n}{dt^n}f(t)$ | $(i\omega)^n \hat{f}(\omega)$ |
| **Derivación en frecuencia** | $(-it)^n f(t)$ | $\hat{f}^{(n)}(\omega) = \frac{d^n}{d\omega^n}\hat{f}(\omega)$ |
| **Integración temporal** | $\int_{-\infty}^{t} f(\tau) d\tau$ | $\frac{1}{i\omega} \hat{f}(\omega) + \pi \hat{f}(0) \delta(\omega)$ |
| **Convolución** | $(f * g)(t)$ | $\sqrt{2\pi} \hat{f}(\omega) \hat{g}(\omega)$ |
| **Multiplicación** | $f(t) g(t)$ | $\frac{1}{\sqrt{2\pi}} (\hat{f} * \hat{g})(\omega)$ |
| **Teorema de Parseval** | $\int_{-\infty}^{\infty} \vert f(t) \vert^2 dt$ | $\int_{-\infty}^{\infty} \vert \hat{f}(\omega) \vert^2 d\omega$ |

---

## 2. Pares Comunes de Transformadas

*Nota: En esta sección, $a > 0$ es una constante real, $\delta(t)$ representa el impulso de Dirac y $u(t)$ es la función escalón de Heaviside.*

| Función en el tiempo $f(t)$ | Transformada de Fourier $\hat{f}(\omega)$ | Notas / Condiciones |
| :--- | :--- | :--- |
| $\delta(t)$ | $\frac{1}{\sqrt{2\pi}}$ | Impulso de Dirac (Espectro plano) |
| $\delta(t - t_0)$ | $\frac{1}{\sqrt{2\pi}} e^{-i\omega t_0}$ | Impulso desplazado en el tiempo |
| $1$ | $\sqrt{2\pi} \delta(\omega)$ | Constante / Componente de continua (DC) |
| $e^{i\omega_0 t}$ | $\sqrt{2\pi} \delta(\omega - \omega_0)$ | Exponencial compleja pura |
| $\cos(\omega_0 t)$ | $\sqrt{\frac{\pi}{2}} [\delta(\omega - \omega_0) + \delta(\omega + \omega_0)]$ | Función Coseno |
| $\sin(\omega_0 t)$ | $-i\sqrt{\frac{\pi}{2}} [\delta(\omega - \omega_0) - \delta(\omega + \omega_0)]$ | Función Seno |
| $\text{sgn}(t)$ | $\sqrt{\frac{2}{\pi}} \frac{1}{i\omega}$ | Función signo |
| $u(t)$ | $\sqrt{\frac{\pi}{2}} \delta(\omega) + \frac{1}{i\omega\sqrt{2\pi}}$ | Escalón unitario |
| $e^{-at} u(t)$ | $\frac{1}{\sqrt{2\pi}(a + i\omega)}$ | Exponencial decreciente causal |
| $e^{-a\vert t \vert}$ | $\sqrt{\frac{2}{\pi}} \frac{a}{a^2 + \omega^2}$ | Exponencial decreciente bilateral |
| $\text{rect}\left(\frac{t}{2a}\right)$ | $\sqrt{\frac{2}{\pi}} \frac{\sin(a\omega)}{\omega}$ | Pulso rectangular (Vale $1$ si $\vert t \vert < a$) |
| $\frac{\sin(at)}{\pi t}$ | $\frac{1}{\sqrt{2\pi}} \text{rect}\left(\frac{\omega}{2a}\right)$ | Función sinc (Dual del pulso rectangular) |
| $e^{-at^2}$ | $\frac{1}{\sqrt{2a}} e^{-\frac{\omega^2}{4a}}$ | Campana de Gauss (Autodual si $a = 1/2$) |
| $t u(t)$ | $i\sqrt{\frac{\pi}{2}} \delta'(\omega) - \frac{1}{\sqrt{2\pi}\omega^2}$ | Función rampa causal |
| $t e^{-at} u(t)$ | $\frac{1}{\sqrt{2\pi}(a + i\omega)^2}$ | Multiplicación por rampa causal |
