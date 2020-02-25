```java

		JButton btnSend = new JButton("Send");
		btnSend.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				Socket socket;
				ObjectOutputStream oos;

				if (!textField.equals("")) {
					textArea.append("Yo: " + textField.getText() + "\n");
			
					try {
						// Creamos el socket apuntando a la dirección del servidor 
						socket = new Socket("192.168.1.39", 9999); 
						// Además del Puerto que estará abierto

						// Mediante la clase DataPacket defino lo que será enviado
						DataPacket data = new DataPacket();

						data.setNickname(nickname);
						data.setIp(tfIp.getText());
						data.setMessage(textField.getText());

						oos = new ObjectOutputStream(socket.getOutputStream());
						oos.writeObject(data);
						oos.close();
						
						// Vuelvo a vaciar la caja de texto.
						textField.setText("");
					} catch (IOException ioe) {
						ioe.printStackTrace();
					}
				}
			}
		});
		btnSend.setBounds(155, 279, 69, 23);
		contentPane.add(btnSend);
```


## Estructura básica de una WEB
Te presento la estructura básica que se utiliza en HTML5:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Titulo</title>
</head>
<body>
    
</body>
</html>
```
## Formas de utilizar CSS en HTML5
En CSS disponemos de tres formas en las que podemos incluir CSS en nuestro código HTML, a continuación te las describo:

##### Incluirlo en el mismo documento HTML:
Tenemos la opción de utilizar la etiqueta <style type="text/css"></style> dentro del encabezado, todo el codigo que añadamos aquí se verá reflejado en la página web. 
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Titulo</title>
    <style type="text/css">
        p {
            color: red;
        }
    </style>
</head>
<body>
    <p> Esta es la primera forma de usar CSS en HTML </p>
</body>
</html>
```

#### Utilizando un archivo externo:
Tambien podríamos crear un archivo style.css dentro de la carpeta de nuestra página web, para no perdernos, en este archivo haremos los cambios y se verán reflejados en nuestra página web. Cuidado: tenemos que asociar este archivo style.css al archivo .html.
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Titulo</title>
    <link rel="stylesheet" type="text/css" href="style.css"/> //El atributo "href" hace referencia a la ruta del archivo.
</head>
<body>
    <p> Esta es la segunda forma de usar CSS en HTML </p>
</body>
</html>
```
#### Incluirlo en los propios elementos HTML
Esta manera de utilizar css es la menos recomendable y se utiliza solo en determinadas ocaciones.
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Titulo</title>
</head>
<body>
    <p style="color: red;font-family=Verdana;"> Esta es la tercera forma de usar CSS en HTML </p>
</body>
</html>

```
## Lista sin ordenar: receta de cocina
La manera de utilizar las listas sin ordenar es con la etiqueta ul, te la muestro a continuación.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Titulo</title>
</head>
<body>
    <h3>Pie de Helado y Caramelo: </h3>
    <ul>
        <li> 1 pinta (1/2 litro) de Helado de Chocolate Light SLOW CHURNED de DREYER'S o EDY'S </li>
        <li> 1 pinta (1/2 litro) de Helado de Vainilla Light SLOW CHURNED de DREYER'S o EDY'S </li>
        <li> 1 (6 a 8 onzas) corteza de galleta preparada de 9 pulgadas de tamaño </li>
        <li> Syrup de Sabor Chocolate NESTLÉ NESQUIK (opcional) </li>
        <li> 2 a 3 barras (1.55 onzas cada una) de NESTLÉ CRUNCH </li>
    </ul>
</body>
</html>
```
## Inclusión de JavaScript en HTML5
Tenemos la posibilidad de incluir JavaScript en el codigo, lo unico que tendremos que hacer es utilizar la etique <script></script> ya sea en el encabezado (head) o en el cuerpo (body), acontinuación te muestro un ejemplo en el que lo utilizo para obtener la hora actual en la página.
```html
<!DOCTYPE html>
<html lang="en-US">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>La hora actual es: </title>
</head>
<body>
<script>
let d = new Date();
document.body.innerHTML = "<h1>Time right now is:  " + d.getHours() + ":" + d.getMinutes() + ":" + d.getSeconds()
"</h1>"
</script>
</body>
</html>
```
## Diferencia entre ID y Class
La principal diferencia entres estas dos son las veces que puede ser llamado o aparece dentro de nuestra página web, ya que a un ID es un identificador que no se puede repetir en todo el documento, es utilizado como su nombre indica para identificar un elemento al vincularlo. Por otro lado las clases pueden repetirse varias veces sobre le mismo documento.
#### Implementación del ID y Class
La forma correcta de añadirlos a nuestro CSS es utilizando (#) para los id y un punto (.) para las clases.
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Titulo</title>
    <style type="text/css">
        #identificador {
            color: red;
        }
        .clase {
            color:red;
        }
    </style>
</head>
<body>
    <p id="identificador"> Esta es la  forma de utilizar ID </p>
    <p class="clase"> Esta la forma de utilizar Class </p>
</body>
</html>
```
## Abrir enlace en una nueva ventana
La manera de incluir una página externa y que se abra en nueva ventana para así no perder lo que estamos haciendo en la página actual es muy sencilla, utilizaremos:

```html
<a target="_blank" href="http://blog.elinsti.com/index.php/2018/11/23/ejercicios-html-y-css/">Con esto podemos abrir la pagina blog.elinsti.com en una nueva ventana</a>
```
## Pseudoclases
Las Pseudoclases las encontramos en CSS y estas son palabras clave que podemos añadir a los selectores, además especifican un estado "especial" del elemento que seleccionado. Un claro ejemplo, y el que se suele ver a menudo es :hover el cual se suele utilizar en las barras de navegación.

```html
<style>
    div:hover {
        background-color: #3883BC;
    }
</style>
```
Con :hover conseguimos que el usuario al posicionarse sobre el elemento que le hayamos especificado aplique un estilo nuevo. A continuación te nombro una lista de pseudoclases que podemos encontrar en CSS:
```html
:active
:checked
:default
:dir()
:disabled
:empty
:enabled
:first
:first-child
:first-of-type
:fullscreen
:focus
:hover
:indeterminate
:in-range
:invalid
:lang()
:last-child
:last-of-type
:left
:link
:not()
:nth-child()
:nth-last-child()
:nth-last-of-type()
:nth-of-type()
:only-child
:only-of-type
:optional
:out-of-range
:read-only
:read-write
:required
:right
:root
:scope
:target
:valid
:visited
```

## Modelo de caja CSS: MARGIN, BORDER Y PADDING

En un principio el modelo de cajas resultó una pesadilla para los diseñadores web ya que en cada navegador es posible que se viera de una manera diferente. Este modelo esta divido, yendo del interior hacia fuera, por el contenido, un padding, un border y un padding. Cuando hablamos de contenido es la información que tenemos dentro del bloque, cuando hablamos de padding nos referimos al espacio que hay entre el contenido y el borde. Mientras el margin es el 'nivel' más alejado del contenido, y cuando lo definimos es para marcar el espacio que tendrá el bloque respecto a los otros bloques. 

Nuestro elemento o bloque tiene unas dimensiones que podemos definir en css mediante un width(ancho) y un height(alto). Por otro lado tambien se puede producir lo que conoce como un debordamiento, es decir, que el bloque abarca más contenido del que es capaz de almacenar, para esto se crearon los atributos o valores: hidden, visible, scroll y auto. Tambien debemos saber que el elemento cuenta con unas zonas a las que denominamos: top, left, right, bottom y center. 

## Selectores
Los selectores los cuales tambien los encontraremos en CSS, se utilizan para identificar a un elemento dentro de una página web, para luego así poder definir sus propiedades o estilos. Hay distintos tipos de selecctores, desde selectores tan simples como los nombres de las etiquetas que utilizamos en nuestro archivo html hasta conbinaciones complejas que nos permiten jugar con nuestra página. A continuacuón te muestro ejemplos de algunos de ellos:

#### Selector universal (*)

Lo utilizamos para seleccionar absolutamente todos los elementos que nos encontremos, lo podriamos utilizar por ejemplo para quitar todo el margin y padding a nuestra página. 

```html
<style>
    * {
        margin: 0;
        padding: 0;
    }
</style>
```
#### Selector de tipo o etiqueta

Como he mencionado anteriormente estos son los mas sencillos ya que solo necesitamos indicar el nombre de una de las etiquetas html que hayamos usado en nuestro codigo, por ejemplo:

``` html 
<style>
    h1 {
        color: red;
    }
</style>
```

#### Selector descendente

Con este selector podemos seleccionar elementos que se encuentren dentor de otros elementos en nuestra página html por ejemplo suponiendo que disponemos del siguiente codigo:

```html
        <p>
          ...
          <span>Esto es un span dentro de un p</span>
          ...
          <a href="">...<span>Esto es una a dentro de un p</span></a>
          ...
        </p>
```
En nuestro codigo utilizaremos lo siguiente para seleccionar el span:

```html
<style>
    p span {
        color: red;
    }
</style>

```
#### Otros selectores

Tambien entre los selectores nos encontramos con los de clase e ID, pero estos ya los he explicado o mencionado en un apartado anterior, te dejo otros tipos selectores que podrías encontrar en CSS:
```html
<style>
    /* Selector de hijos */
        p > span {color: red;}
    /* Selector adyacente */
        h1 + h2 {color:red;}
    /* Selector de atributos */
        a[class] {color: red;}
        a[class="externo"; {color: red;}
        a[href="http://blog.elinsti.com" {color: red};
</style>
```
#### Los siguientes selectores afectan a:

```html
<style>
    p a { color: red; 
    p > a { color: red; }
    h1 + h2 { color: red }
    a[class] { color: blue; }
    a[class="externo"] { color: blue; }
    a[href="http://www.ejemplo.com"] { color: blue; }
</style>
```

