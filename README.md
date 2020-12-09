# Examen_1evaluacion

4. He creado una variable "dollar", que tenga el signo de dolar y este valor se lo he pasado al td con la var price

- `$dollar = "$";`
- `// creating new table row per record`
- `echo "<tr>";`
- `echo "<td>{$id}</td>";`
- `echo "<td>{$name}</td>";`
- `echo "<td>{$description}</td>";`
- `echo "<td>{$dollar}{$price}</td>";`
- `echo "<td>";`

He insertado el dolar, cuando se va a ejecutar el eco con la variable price

- `<td>Price</td>`
- `<td>`
- `<?php`
- `echo '$' . htmlspecialchars($price, ENT_QUOTES);`
- `?>`
- `</td>`

5)

- La imagen de guarda es un tipo de variable blob
- Dentro de create.php, podemos ver que se realizan unas excepciones de si la imagen es igual, tiene un tamaño mayor de 1 MB.
- Comprueba si hay una carpeta folders, donde se guardan estas imagenes, si no, se crea.
- En la base de datos, se ve que el archivo de la imagen, esta codificado.
- La imagen podemos recuperarla si se ha creado la carpeta folders y podemos ver la imagen ahi.
- Tambien podemos descargar esta imagen si vamos a la base de datos con adminer, y hacemos click izquierdo.
- La imagen solo pude tener algunos tipos de formatos de imagen jpg, jpeg, png, gif
- Comprueba tambien, si el fichero que nos da, es una imagen.
- Si algun error ha ocurrido el usuario puede verlo.
- Finalmente, la imagen se guardará si todo esta de manera correcta y no hay ningun error dentro de la BD.

6) 
- Cuando hago la query para llamar las propiedades de los objetos escribo la propiedades de image.
- Guardo POST image dentro de una variable $image
- Añado el bind paremetro de image
- Escribo el codigo html como se tendria que mostrar para subir la imagen

`$query = "UPDATE products`
`SET name=:name, description=:description, price=:price, image=:image`
`WHERE id = :id";`
`// prepare query for excecution`
`$stmt = $con->prepare($query);`
`// posted values`
`$name=htmlspecialchars(strip_tags($_POST['name']));`
`$description=htmlspecialchars(strip_tags($_POST['description']));`
`$price=htmlspecialchars(strip_tags($_POST['price']));`
`$image=htmlspecialchars(strip_tags($_POST['image']));`

`// bind the parameters`
`$stmt->bindParam(':name', $name);`
`$stmt->bindParam(':description', $description);`
`$stmt->bindParam(':price', $price);`
`$stmt->bindParam(':image', $image);`
`$stmt->bindParam(':id', $id);`

`<td>Photo</td>`
`<td>`
`<input type="file" name='image' value="<?php echo $image ? "<img src='uploads/{$image}' style='width:300px;' />" : "No image found.";  ?>"/>`
`</td>`
