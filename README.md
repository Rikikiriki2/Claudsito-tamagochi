# Claudsito Tamagochi

Una mascota virtual en pixel art que se juega desde el cel. Claudsito vive en una maquinita con pantalla de terminal: lo alimentas, juegas con él, lo duermes, lo limpias y lo ves crecer.

Todo vive en `index.html` (HTML, CSS y JS sin dependencias). La partida se guarda en el navegador (`localStorage`).

## Mecánicas

### Barras (0 a 100)

Bajan con el tiempo real, aunque cierres la app. Al volver, el juego calcula lo que pasó mientras no estabas (hasta 3 días).

| Barra   | Qué hace                                                               |
|---------|------------------------------------------------------------------------|
| Panza   | Se vacía en unas 6 horas (más lento dormido).                          |
| Ánimo   | Baja en unas 5 horas. Sube jugando, con galletas o con cariño.         |
| Energía | Dura unas 12 horas despierto. Si llega a 0, se duerme donde sea.       |
| Higiene | Baja poco a poco y más rápido con cada popó en el piso.                |
| Salud   | Baja si está enfermo o con barras en 0. Se recupera si está bien.      |

### Acciones

- **Comer → Comida**: +30 panza. Entre 15 y 35 minutos después hace popó. Si ya está lleno, no come.
- **Comer → Galleta**: +15 ánimo, +8 panza. Si come 3 galletas en una hora, tiene 50% de probabilidad de enfermarse.
- **Jugar (Caza bugs)**: minijuego de 20 segundos. Toca los bugs antes de que se escapen. Ánimo +6 más 4 por bug (máximo +40). Cuesta energía y panza. No se puede jugar enfermo ni muy cansado.
- **Dormir**: apaga la luz y recarga energía. Se despierta solo con la pila llena. Si lo despiertas antes de tiempo, se enoja.
- **Limpiar**: quita las popós y deja la higiene en 100.
- **Curar**: medicina cuando aparece la calavera. Si no está enfermo, no hace nada.
- **Cariño**: tócalo en la pantalla. Sube un poco el ánimo (una vez cada 30 segundos).

### Enfermedad

Hay riesgo de enfermarse con higiene baja, 3 o más popós o la panza en 0. Enfermo, su salud baja y se ve verdoso.

### Crecimiento

Huevo (1 min) → Bebé (hasta 1 hora) → Chamaco (hasta 1 día) → Adulto.

Cada vez que una barra llega a 0 cuenta como **descuido**. Al volverse adulto:

- 3 descuidos o menos: **Claudsito Pro**, con audífonos.
- Más de 3: **Desvelado**, con ojeras.

### Fin del juego

Si la salud llega a 0, Claudsito "se va a la nube" y puedes empezar con un huevo nuevo. Se conservan el nombre y el récord del minijuego.

## Cómo jugarlo en el cel

1. En GitHub, ve a **Settings → Pages**.
2. En **Source** elige *Deploy from a branch*. En **Branch** elige `main` y la carpeta `/ (root)`, y toca **Save**.
3. Abre `https://rikikiriki2.github.io/Claudsito-tamagochi/` en el cel.
4. Usa *Agregar a pantalla de inicio* para que se abra como app.

Para probarlo en la compu basta con abrir `index.html` en el navegador.
