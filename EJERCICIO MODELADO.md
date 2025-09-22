
## 📂 Colecciones y ejemplos de datos

### 1. Usuarios

```js
db.usuarios.insertMany([
  {
    _id: ObjectId("64a111111111111111111111"),
    nombre: "Ana Torres",
    email: "ana@example.com",
    cursosInscritos: [
      ObjectId("64b111111111111111111111"),
      ObjectId("64b222222222222222222222")
    ]
  },
  {
    _id: ObjectId("64a222222222222222222222"),
    nombre: "Luis Pérez",
    email: "luis@example.com",
    cursosInscritos: [
      ObjectId("64b111111111111111111111"),
      ObjectId("64b333333333333333333333")
    ]
  },
  {
    _id: ObjectId("64a333333333333333333333"),
    nombre: "Carla Gómez",
    email: "carla@example.com",
    cursosInscritos: [ObjectId("64b333333333333333333333")]
  }
])
```

---

### 2. Cursos

```js
db.cursos.insertMany([
  {
    _id: ObjectId("64b111111111111111111111"),
    titulo: "MongoDB desde cero",
    categoriaId: ObjectId("64c111111111111111111111"),
    descripcion: "Curso introductorio de MongoDB",
    modulos: [
      { titulo: "Introducción", duracionMin: 30 },
      { titulo: "Modelado de datos", duracionMin: 50 }
    ]
  },
  {
    _id: ObjectId("64b222222222222222222222"),
    titulo: "Node.js avanzado",
    categoriaId: ObjectId("64c222222222222222222222"),
    descripcion: "Curso sobre Node.js y microservicios",
    modulos: [
      { titulo: "Fundamentos", duracionMin: 40 },
      { titulo: "APIs REST", duracionMin: 60 }
    ]
  },
  {
    _id: ObjectId("64b333333333333333333333"),
    titulo: "SQL para analistas",
    categoriaId: ObjectId("64c111111111111111111111"),
    descripcion: "Consultas avanzadas en SQL",
    modulos: [
      { titulo: "Consultas básicas", duracionMin: 45 },
      { titulo: "Funciones agregadas", duracionMin: 70 }
    ]
  }
])
```

---

### 3. Categorías

```js
db.categorias.insertMany([
  { _id: ObjectId("64c111111111111111111111"), nombre: "Bases de datos" },
  { _id: ObjectId("64c222222222222222222222"), nombre: "Desarrollo backend" }
])
```

---

### 4. Posts

```js
db.posts.insertMany([
  {
    _id: ObjectId("64d111111111111111111111"),
    usuarioId: ObjectId("64a111111111111111111111"),
    cursoId: ObjectId("64b111111111111111111111"),
    titulo: "¿Dudas con el modelado?",
    contenido: "No entiendo cuándo usar embebidos o referencias.",
    comentarios: [
      {
        usuarioId: ObjectId("64a222222222222222222222"),
        texto: "Yo prefiero embebidos para cosas pequeñas."
      },
      {
        usuarioId: ObjectId("64a333333333333333333333"),
        texto: "Las referencias van mejor si los datos se comparten mucho."
      }
    ]
  },
  {
    _id: ObjectId("64d222222222222222222222"),
    usuarioId: ObjectId("64a222222222222222222222"),
    cursoId: ObjectId("64b222222222222222222222"),
    titulo: "Errores con Express",
    contenido: "¿Alguien sabe por qué no funciona mi middleware?",
    comentarios: [
      {
        usuarioId: ObjectId("64a111111111111111111111"),
        texto: "Revisa si llamas a `next()` en todos los casos."
      }
    ]
  }
])
```

---

## 📝 Preguntas de práctica con `$lookup` y agregaciones

1. **Cursos con categoría**
   Lista todos los cursos junto con el nombre de su categoría.

2. **Posts con autores**
   Obtén todos los posts mostrando también el nombre y el email del usuario que los creó.

3. **Usuarios y sus cursos inscritos**
   Muestra los usuarios junto con el detalle de los cursos en los que están inscritos (usando `$lookup`).

4. **Comentarios con nombre de usuario**
   Para un post específico, muestra los comentarios pero en lugar de `usuarioId`, trae el nombre de quien comentó.

5. **Usuarios inscritos en un curso**
   Encuentra todos los usuarios inscritos en el curso **“MongoDB desde cero”**.

6. **Cursos con total de duración**
   Muestra los cursos y calcula el tiempo total de todos sus módulos (`$sum` de `duracionMin`).

7. **Top cursos más populares**
   Encuentra los cursos con más usuarios inscritos (usa `$lookup` entre usuarios y `cursosInscritos`).


