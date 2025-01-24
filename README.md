* Nombre: Matias Casiba
* Link GitHub Repo: https://github.com/MatiCasiba/calculadora-con-grid
* Link Netlify:

# Desafio 13 - Calculadora con grid
Al igual que el desafio 11, ahora tengo que darle estilo a la calculadora pero con grid:

## Esqueleto de la calculadora
En el archivo index.html, estaré usando contenedores, clases y botones para la calculadora, lo arme de la siguiente forma:

```sh
    <div class="calculadora">
      <div class="pantalla" id="pantalla">0</div>
      <div class="botones">
        <button class="btn">9</button>
        <button class="btn">8</button>
        <button class="btn">7</button>
        <button class="btn">+</button>
        <button class="btn">6</button>
        <button class="btn">5</button>
        <button class="btn">4</button>
        <button class="btn">-</button>
        <button class="btn">3</button>
        <button class="btn">2</button>
        <button class="btn">1</button>
        <button class="btn">x</button>
        <button class="btn">.</button>
        <button class="btn">0</button>
        <button class="btn">=</button>
        <button class="btn">/</button>
      </div>
    </div> 
```

## Diseño de la calculadora
Te mostraré las configuraciones para el diseño de la calculadora, en este caso, los botones serán trabajdos con grid, con la finalidad de crear las 4 columnas.

* Reset:
```sh
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```
* Elemeto html:
```sh
html{
  font-size: 100%; # el tamaño estandar de las letras/numeros/símbolos, serán de 16px
}
```

### Cuerpo
```sh
body{
  display: flex;

  # centrando el contenido (la calculadora) en el eje horizontal y vertical
  justify-content: center;
  align-items: center;

  height: 100vh; # el alto de la ventana gráfica
  background-image: url(/imge/fornmulas-matematicas.webp); # coloco una imagen de fondo
  background-size: cover; # ajusta la imagen para que cubra todo el fondo
  background-position: center; # centro la imagen
  background-repeat: no-repeat; # me permite evitar que se repita la imagen
}
```

### Pantalla / Display
La pantalla donde se mostrarán las ejecuciones de las cuenta que desea usar el usuario, le estaré dando tamaño y color y que se escriban los números desde la derecha:
```sh
.pantalla{
  width: 100%;
  height: 60px;

  # color de fondoe y letras
  background-color: ...;
  color: ...;

  # inicio de los números y tamaño
  text-align: right;
  font-size: 2rem;

  # relleno y bordado de la pantalla
  padding: 10px;
  border-radius: 5px;

  margin-bottom: 10px; # un esppacio entre la pantalla y los teclados
}
```

### Calculadora
En este caso, la calculadora no tendrá un fondo como lo hice anterirormente, pero si estaré ajustando su ancho
```sh
.calculadora {
  width: 300px;
  background-color: none;
}
```
### Botones
Comno mencioné al principio, en los botones estaré usando grid, con la finalidad de crear las 4 columnas con 4 botones en cada una de estas:
```sh
.botones{
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 2px; # espacio entre los elementos
}
```
Voy a ir por partes:
* display: grid; -> con esto, los botones se organizan automaticamente en filas y columnas
* grid-template-columns: repeat(4, 1fr); -> son 4 columnas de igual tamaño, 1fr (fracción) hace que cada columna ocupe una partee igual del ancho disponible

### Estilo paraa los botones
Voy a diseñar los botones, les daré tamaño, grosor y colores:
```sh
.btn{
  background: linear-gradient(50deg, green, yellow); # los colores de los botones tendrá un degradado
  color: ... ;
  border: none;
  padding: 15px; # el relleno de los botones
  font-size: 1.5rem; # el tamaño de los numeros y simbolos que se encuentran en los botones
  border-radius: 5px;
  cursor: pointer; # cuando pasamos con el cursor sobre los botones, se convertirá en una manito
}

# hover -> al pasar el mouse sobre los botones, cambiarán de color
.btn:hover{
  background: linear-gradient(50deg, darkgreen, greenyellow);
}
```