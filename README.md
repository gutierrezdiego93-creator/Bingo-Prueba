# 🎱 Bingo

Juego de bingo clásico (1–75) en una sola página HTML. Sin dependencias, sin build, sin backend: se abre en cualquier navegador y funciona.

## Cómo jugar

1. Abre `index.html` en el navegador (o entra a la URL desplegada).
2. Pulsa **Sacar número** — o la barra espaciadora — para cantar una bola.
3. Cada jugador marca en su cartón haciendo clic sobre el número. Solo deja marcar números que ya salieron.
4. El juego avisa automáticamente cuando hay **línea** (fila, columna o diagonal completa) y cuando hay **bingo** (cartón lleno).

Los nombres de los jugadores se editan haciendo clic sobre ellos. Con los botones puedes generar cartones nuevos, reiniciar la partida o jugar entre uno y seis cartones a la vez.

## Cómo está hecho

Todo vive en `index.html`: estructura, estilos y lógica en un solo archivo de poco más de 300 líneas, sin librerías externas.

La generación de cartones sigue el bingo estadounidense: cinco columnas B-I-N-G-O, cada una con cinco números sorteados de su propio rango (B va de 1 a 15, I de 16 a 30, N de 31 a 45, G de 46 a 60 y O de 61 a 75), con la casilla central marcada como FREE desde el inicio. El bombo es un arreglo de 1 a 75 barajado con Fisher-Yates, del que se extrae un número por turno sin reposición, así que nunca se repite ninguno ni se agota antes de tiempo.

La detección de premio revisa las cinco filas, las cinco columnas y las dos diagonales en cada marcado; si alguna está completa se anuncia línea, y si las veinticinco casillas están marcadas se anuncia bingo.

## Despliegue

El proyecto es estático, así que cualquier hosting sirve sin configuración. En Vercel basta con importar el repositorio: detecta el `index.html` en la raíz y lo publica tal cual, sin framework ni comando de build.

## Estructura

```
.
├── index.html    # el juego completo
├── vercel.json   # configuración de despliegue estático
└── README.md
```
