# Instalar Flask
**Instalar el entorno de virtual :**

pasos

1\. pip install virtualenv

2\. virtualenv "env"→nombre del entorno

3\. env\Scripts\activate

4\. imprime en pantalla el nombre del entorno que seria (env)

si no funciona abre el powershell

`	`pasos

`		`1. Get-ExecutionPolicy -list

`		`2. Set-ExecutionPolicy RemoteSigned -Force

**Instalar pip install Flask:**

pasos

1\. pip install flask
# Escribe tu primer Hola mundo con Flask.
Creas un archivo de Python y escribir el siguiente código:

from flask import Flask #→ es obligatorio llamar la libreria

app = Flask(\_\_name\_\_)#→ Activamos la dependencia 

@app.route("/") #→Ruta Url "Creamos una ruta"

def hello\_world():#→Funcion de salida"

`    `return "<p>Hello, World!</p>"

if \_\_name\_\_ == '\_\_main\_\_':#→Recomiendo poder ejecutar el servidor "

`    `app.run()

# Crear Rutas o paginas 
Simplemente debemos copiar @app.route y luego hacer la función con la salida.

from flask import Flask #→ es obligatorio llamar la libreria

app = Flask(\_\_name\_\_)#→ Activamos la dependencia 

@app.route("/") #→Ruta Url "Creamos una ruta"

def hello\_world():#→Funcion de salida"

`    `return "<p>Hello, World!</p>"

#creamos mas rutas 

@app.route("/Hola") #→Ruta Url "Creamos la ruta 2"

def ruta2():#→Funcion de salida"

`    `return "<p>Hello, RUTA 2!</p>"

if \_\_name\_\_ == '\_\_main\_\_':#→Recomiendo poder ejecutar el servidor "

`    `app.run()

# ` `Activar el modo debug en Flask 
poder ver los cambios mientras la api esta desplegada

if \_\_name\_\_ == '\_\_main\_\_':#→Recomiendo poder ejecutar el servidor "

`    `app.run(debug = True) #→ agregamos el modo debug "

# Activar  varias rutas en un index
` `Para que la pagina principal sea

app = Flask(\_\_name\_\_)#→ Activamos la dependencia 

@app.route("/") #→Ruta Url "Creamos una ruta"

@app.route("/main") #→Ruta Url "creamos varias rutas"

def hello\_world():#→Funcion de salida"



`    `return "<p>Hello, World!</p>"


# enviar variable argumentos 
` `Hacemos una práctica de  enviar  parámetros podrás ver el curso “ Flask - Construye aplicaciones web profesionales con Python” en la clase “10. Variables en rutas” en el minuto “0:20”

#creamos mas rutas 

@app.route("/Hola/<name>") #→Ruta Url "Creamos la ruta 2"

def ruta2(name):#→Funcion de salida"

`    `return f"<p>Hello, {name}!</p>"

asi se vera en la web :

![Interfaz de usuario gráfica, Texto, Aplicación

Descripción generada automáticamente](Aspose.Words.7dd3c3c8-96c3-4cdf-a089-819ccc3b4620.001.png)




Como pasarle los valores , y además hacer unos condicionales 

![](Aspose.Words.7dd3c3c8-96c3-4cdf-a089-819ccc3b4620.002.png)

# Plantillas html
` `debes crear una carpeta en la ruta del proyecto llamada templade, creamos el archivo html e inportamos una nueva librería :

from flask import Flask,render\_template #→ es obligatorio llamar la libreria

luego creamos un , creamos una ruta de esta manera :

#creamos mas rutas con Html 

@app.route("/html") #→Ruta Url "llamamos nuestro html "

def html():#→Funcion de salida"

`    `return render\_template("Index.html")

if \_\_name\_\_ == '\_\_main\_\_':#→Recomiendo poder ejecutar el servidor "

`    `app.run(debug = True) #→ agregamos el modo debug "

podemos pasarle ejemplo variables , y todo con argumentos esa parte la podrás encontrarla , ver el curso “ Flask - Construye aplicaciones web profesionales con Python” en la clase “14. Creación de plantillas” en el minuto “3:00”:

![](Aspose.Words.7dd3c3c8-96c3-4cdf-a089-819ccc3b4620.003.png)




Y en la plantilla índex como agregamos name:

![](Aspose.Words.7dd3c3c8-96c3-4cdf-a089-819ccc3b4620.004.png)

# Lógica a las plantillas  html como IF,BUCLES y demás 
Para tener esta información te cuento franklin del futuro que busques la sección del curso “ Flask - Construye aplicaciones web profesionales con Python”  de Udemy :

![Imagen que contiene Interfaz de usuario gráfica

Descripción generada automáticamente](Aspose.Words.7dd3c3c8-96c3-4cdf-a089-819ccc3b4620.005.png)

1. llamar una función de desde HTML :

   {{url\_for('registro')}}


# Html Base – Herencia de plantilla
Para tener esta información te cuento franklin del futuro que busques la sección del curso “ Flask - Construye aplicaciones web profesionales con Python”  de Udemy  , en la clase “16. Uso de herencia de plantillas” en el minuto “0:00” donde te explicaran como hacer un html , base y no tengas que reescribir código.

![](Aspose.Words.7dd3c3c8-96c3-4cdf-a089-819ccc3b4620.006.png)









Ejemplo de archivo base : 

Nota: aquí implementamos boostrap para el diseño.

{% block html %}

<!DOCTYPE html>

<html lang="en">

<head>

`    `<meta charset="UTF-8">

`    `<meta name="viewport" content="width=device-width, initial-scale=1.0">

`    `<title></title>

`    `<!-- Bootstrap CSS -->

`    `<link href="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" rel="stylesheet">  

`    `<link rel="stylesheet" href="{{ url\_for('static', filename='css/style.css' ) }}">



<body class="fondo">

{% endblock %} 

<!-- Contenido-->

{% block contenido %}

{% endblock %}

<!-- /Contenido-->

<!-- Mensaje error --> 

{%for massage in get\_flashed\_messages() %}

<div class="container mt-3">

`  `<div class="row">

`    `<div class="col-md-6 mx-auto">

`      `<div class="alert alert-danger" role="alert">

`        `{{ massage }}

`      `</div>

`    `</div>

`  `</div>

</div>

{% endfor %}

<!-- /Mensaje error -->     

{% block footer %}

`    `<!-- Bootstrap JS -->



`    `<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>

`    `<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.16.0/umd/popper.min.js"></script>

`    `<script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script>



</body>

</html>

{% endblock %}

Para llamar la plantilla base :

{% extends 'base.html' %}

{% block contenido %}

<!—aqui pones el contenido del html --> 

{% endblock %}


Para hacer mensaje de error en el Dom html:

<!-- Mensaje error --> 

{%for massage in get\_flashed\_messages() %}

<div class="container mt-3">

`  `<div class="row">

`    `<div class="col-md-6 mx-auto">

`      `<div class="alert alert-danger" role="alert">

`        `{{ massage }}

`      `</div>

`    `</div>

`  `</div>

</div>

{% endfor %}

<!-- /Mensaje error -->  



# API-REST con Flask

1. Es instalar la librería en el entorno
1. se hace los Model , modificar la tabla dependiendo a tus necesidades:

from flask import Flask ,request,jsonify

from flask\_sqlalchemy import SQLAlchemy

app = Flask(\_\_name\_\_)

app.config['SQLALCHEMY\_DATABASE\_URI'] = 'sqlite:///Students.db'



db=SQLAlchemy(app)

class Student(db.Model):

`    `id = db.Column(db.Integer, primary\_key=True)

`    `<a name="_hlk136460356"></a>“@Nombre de la columna“ = db.Column(db.String(50), nullable=False)



`    `def serialize(self):

`        `return{

`            `'id':self.id,

`            `'<a name="_hlk136460648"></a>“Nombre de la columna“ ':self.name,

`              `}


3\.se crea una función para la creación de todas  la tabla :

with app.app\_context():

`    `db.create\_all()



4\.para crear un metodo get obteniendo las tablas, el ejemplo es con una tabla llamada  Student :

@app.route("/Student" ,methods =['GET']) 

def get\_Student():

`    `Students=Student.query.all()

`    `return jsonify({'Student':[Student.serialize() for Student in Students ]})

5\.para hacer un post :

@app.route("/Student" ,methods =['POST']) 

def Create\_Student():

`    `data =request.get\_json()

`    `student = Student(

`        `“@Nombre de la columna“ = data['name'],

`    `db.session.add(student)

`    `db.session.commit()

`    `return jsonify({'message':'Contacto registrado con exito ','Student':Student.serialize()})

6\.para obtener un modificar datos   :

@app.route('/Student/<int:id>', methods = ['PUT', 'PATCH'])

def edit\_Student(id):

`    `Students = Student.query.get\_or\_404(id)

`    `data = request.get\_json()

`    `if '“@Nombre de la columna name' in data:

`        `Students.“@Nombre de la columna = data['name']



`    `# Guardar los cambios en la base de datos

`    `db.session.commit()

`    `return jsonify({'message':'Contacto actualizado con éxito', 'contact': 

`        `Students.serialize()})


6\.Como eliminar la clase de ejemplo es Student :

@app.route('/Student/<int:id>', methods = ['DELETE'])

def delete\_Student(id):

`    `Students = Student.query.get(id)

`    `if not Students:

`        `return jsonify({'message':'estudiante no encontrado'}), 404



`    `db.session.delete(Students)

`    `db.session.commit()

`    `return jsonify({'message':'estudiante eliminado con éxito'})



7\.para finalizar mostramos todo el proyecto:

from flask import Flask ,request,jsonify

from flask\_sqlalchemy import <a name="_hlk164966812"></a>SQLAlchemy

app = Flask(\_\_name\_\_)

app.config['SQLALCHEMY\_DATABASE\_URI'] = 'sqlite:///Students.db'



db=SQLAlchemy(app)

class Student(db.Model):

`    `id = db.Column(db.Integer, primary\_key=True)

`    `name = db.Column(db.String(50), nullable=False)

`    `lastName = db.Column(db.String(50), nullable=False)

`    `email = db.Column(db.String(50), nullable=False)

`    `codigoPhone= db.Column(db.String(11), nullable=False)

`    `phone= db.Column(db.String(11), nullable=False)

`    `password= db.Column(db.String(50), nullable=False)

`    `def serialize(self):

`        `return{

`            `'id':self.id,

`            `'name':self.name,

`            `'lastName':self.lastName,

`            `'email':self.email,

`            `'codigoPhone':self.codigoPhone,

`            `'phone':self.phone,

`            `'password':self.password

`        `}



with app.app\_context():

`    `db.create\_all()





@app.route("/Student" ,methods =['GET']) 

def get\_Student():

`    `Students=Student.query.all()

`    `return jsonify({'Student':[Student.serialize() for Student in Students ]})

@app.route('/Student/<int:id>', methods = ['GET'])

def get\_StudentID(id):

`    `Students = Student.query.get(id)

`    `if not Students:

`        `return jsonify({'message':'Contacto no encontrado'}), 404

`    `return jsonify(Students.serialize())




@app.route("/Student" ,methods =['POST']) 

def Create\_Student():

`    `data =request.get\_json()

`    `student = Student(

`        `name = data['name'],

`        `lastName = data['lastName'],

`        `email = data['email'],

`        `codigoPhone = data['codigoPhone'],

`        `phone = data['phone'],

`        `password = data['password'])



`    `db.session.add(student)

`    `db.session.commit()

`    `return jsonify({'message':'Contacto registrado con exito ','Student':Student.serialize()})

@app.route('/Student/<int:id>', methods = ['PUT', 'PATCH'])

def edit\_Student(id):

`    `Students = Student.query.get\_or\_404(id)

`    `data = request.get\_json()

`    `if 'name' in data:

`        `Students.name = data['name']

`    `if 'lastName' in data:

`        `Students.lastName = data['lastName']

`    `if 'email' in data:

`        `Students.email = data['email']

`    `if 'codigoPhone' in data:

`        `Students.codigoPhone = data['codigoPhone']

`    `if 'phone' in data:

`        `Students.phone = data['phone']

`    `if 'password' in data:

`        `Students.phone = data['password']

`    `# Guardar los cambios en la base de datos

`    `db.session.commit()

`    `return jsonify({'message':'Contacto actualizado con éxito', 'contact': Students.serialize()})

@app.route('/Student/<int:id>', methods = ['DELETE'])

def delete\_Student(id):

`    `Students = Student.query.get(id)

`    `if not Students:

`        `return jsonify({'message':'estudiante no encontrado'}), 404



`    `db.session.delete(Students)

`    `db.session.commit()

`    `return jsonify({'message':'estudiante eliminado con éxito'})




@app.route("/Cursos", methods =['GET']) 

def Cursos():

`    `return "<p>Cursos</p>"

@app.route("/Certificados") 

def Certificados():

`    `return "<p>Certificados</p>"



Como auteticarse con firebase= <https://www.youtube.com/watch?v=HltzFtn9f1c>

- Herramientas necesarias para el despliegue: Git, Github y PythonAnywhere

![Texto

Descripción generada automáticamente](Aspose.Words.7dd3c3c8-96c3-4cdf-a089-819ccc3b4620.007.png)
# Enviar datos de un formulario en  Flask

Se deben tener encuenta los id del html en el form por ejemplo aquí tenemos el formulario en html :

` `<form class="form-floating" action="" method="post">

`        `<div class="mb-3">

`        `<label class="text-start text-primary" for="items"><strong>Código:</strong></label>

`        `<input class="input-group-text" type="text" id="items" name="items" required>

`        `</div>

`        `<div class="mb-3">

`        `<label class="text-start text-primary" for="articulo"><strong>Artículo:</strong></label>

`        `<input class="input-group-text" type="text" id="articulo" name="articulo" required>

`        `</div>

`        `<div class="mb-3">

`        `<label class="text-start text-primary" for="ctd\_stickers"><strong>Cantidad de etiquetas a Imprimir:</strong></label>

`        `<input class="input-group-text" type="number" id="ctd\_stickers" name="ctd\_stickers" >

`        `</div>

`        `<div class="mb-3">

`        `<label class="text-start text-primary" for="ctd\_altura"><strong>Altura a Imprimir:</strong></label>

`        `<input class="input-group-text" type="number" id="ctd\_altura" name="ctd\_altura" required value="200">

`        `</div>

`        `<div class="mb-3">

`        `<label class="text-start text-primary" for="ctd\_ancho"><strong>Ancho a Imprimir:</strong></label>

`        `<input class="input-group-text" type="number" id="ctd\_ancho" name="ctd\_ancho" required value="150">

`        `</div>

`        `<input class="btn btn-info" type="submit" value="Convertir a etiquetas">

`      `</form>

Franklin del futuro recuerda tomar los nombres de id y ahora mira la función en Python :

def StikerSmall():

`    `items=request.form['items']

`    `articulo=request.form['articulo']

`    `ctd\_stickers=request.form['ctd\_stickers']

`    `ctd\_altura=request.form['ctd\_altura']

`    `ctd\_ancho=request.form['ctd\_ancho']

`    `out= db.stikersmall(items,articulo,ctd\_stickers,ctd\_altura,ctd\_ancho)

`    `return out






# Adjuntar archivos en Flask
Mira esta excelente referencia en este video en youtube explica paso a paso 

Link: <https://www.youtube.com/watch?v=Yyul17TBHrE&ab_channel=RoCode>

Lo primero que debes hacer es agregar esta librerías :

import os

from werkzeug.utils import secure\_filename


paso dos agregar y la este código y onfiguracion y crea una carpeta en el respositorio del proyecto:

app.config['UPLOAD\_FOLDER'] = 'uploads/'  # Directorio donde se guardarán los archivos subidos

ALLOWED\_EXTENSIONS= set(['png','jpg','pdf'])


Luego vez crea la función que captura el form :

soportes1=request.files['soportes1']

print(soportes1.filename)

soportes1.save(os.path.join(app.config['UPLOAD\_FOLDER'],soportes1.filename))


así queda en html :

<div class="form-floating mb-3"></div>

`        `<label for="soportes">Carta de solicitud de cesantías donde se especifique, motivo de retiro, monto y fondo:</label>

`        `<input class="form-control rounded-3" type="file" id="soportes1" name="soportes1" accept=".jpg .pdf .png">

`        `<br>


