# Self-Driving Car Simulation in JavaScript

![Self-Driving Car Demo](car.png)

## Descripción

Este proyecto es una simulación de un coche autónomo implementada completamente en JavaScript sin librerías externas. Utiliza una red neuronal simple para permitir que los coches aprendan a conducir por sí mismos, evitando obstáculos y otros coches en la carretera.

## Características

- Simulación de carretera con múltiples carriles
- Detección de colisiones
- Sensores virtuales para detectar obstáculos
- Red neuronal para toma de decisiones
- Visualización de la red neuronal en tiempo real
- Capacidad de guardar y cargar el "cerebro" entrenado
- Evolución automática mediante mutaciones genéticas
- Selección natural: solo sobreviven los mejores conductores

## Tecnologías Utilizadas

- HTML5 Canvas para renderizado
- JavaScript puro (vanilla JS)
- Implementación propia de redes neuronales
- LocalStorage para persistencia de datos

## Estructura del Proyecto

- **car.js**: Define la clase Car con propiedades físicas, controles y lógica de daños
- **sensor.js**: Implementa los sensores del coche mediante rayos virtuales
- **network.js**: Contiene la implementación de la red neuronal y algoritmos de mutación
- **road.js**: Maneja la creación y renderizado de la carretera
- **controls.js**: Gestiona los controles de entrada (manual y automático)
- **utils.js**: Funciones de utilidad como detección de intersecciones y conversiones
- **visualizer.js**: Dibuja la representación gráfica de la red neuronal
- **main.js**: Punto de entrada principal y bucle de animación
- **index.html**: Estructura HTML básica
- **style.css**: Estilos para la interfaz

## Cómo Funciona

### El Coche y Sus Sensores

El coche está equipado con sensores (rayos) que detectan la distancia a obstáculos como los bordes de la carretera y otros vehículos. Estos sensores proporcionan información que se utiliza como entrada para la red neuronal.

```javascript
// Ejemplo de cómo los sensores detectan obstáculos
#getReading(ray, roadBorders, traffic) {
    let touches = [];
    // Detecta intersecciones con los bordes de la carretera
    // Detecta intersecciones con otros coches
    // Devuelve la intersección más cercana
}
```

### La Red Neuronal

La red neuronal toma las lecturas de los sensores como entrada y produce acciones (avanzar, retroceder, girar) como salida. La red está compuesta por capas de neuronas interconectadas con pesos y sesgos que se ajustan mediante un proceso evolutivo.

```javascript
// Estructura básica de la red neuronal
[
  // Capa de entrada (lecturas de sensores)
  [neuron1, neuron2, neuron3, neuron4, neuron5],
  // Capa oculta
  [neuron1, neuron2, neuron3, neuron4, neuron5, neuron6],
  // Capa de salida (controles: adelante, izquierda, derecha, atrás)
  [neuron1, neuron2, neuron3, neuron4],
];
```

### Aprendizaje por Evolución

En lugar de usar algoritmos de aprendizaje tradicionales como backpropagation, este proyecto utiliza un enfoque evolutivo:

1. Se generan múltiples coches con redes neuronales aleatorias
2. Los coches que llegan más lejos sin chocar son seleccionados
3. Se guarda el "cerebro" (red neuronal) del mejor coche
4. Se crean nuevos coches basados en el mejor, con pequeñas mutaciones
5. Se repite el proceso, mejorando gradualmente el rendimiento

## Cómo Usar

1. Abre `index.html` en tu navegador
2. Observa cómo los coches intentan navegar por la carretera
3. Cuando un coche se desempeñe bien, haz clic en "💾 Save" para guardar su cerebro
4. Si quieres descartar el cerebro guardado, haz clic en "🗑️ Discard"
5. Recarga la página para ver cómo evoluciona la siguiente generación

## Futuras Mejoras

- Añadir más obstáculos y escenarios complejos
- Implementar un sistema de puntuación más sofisticado
- Mejorar la visualización de la red neuronal
- Añadir controles para ajustar parámetros de la simulación
- Permitir al usuario dibujar sus propias carreteras

## Créditos

Este proyecto fue creado como ejercicio educativo para entender los conceptos básicos de:

- Redes neuronales
- Algoritmos genéticos
- Inteligencia artificial aplicada
- Simulación física en JavaScript

## Licencia

Este proyecto está bajo la Licencia MIT. Siéntete libre de usar, modificar y distribuir el código como desees.
