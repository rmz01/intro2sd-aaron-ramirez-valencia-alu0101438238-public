[![Open in Codespaces](https://classroom.github.com/assets/launch-codespace-2972f46106e565e64193e422d61a12cf1da4916b45550586e14ef0a7c637dd04.svg)](https://classroom.github.com/open-in-codespaces?assignment_repo_id=16103417)

# Práctica: Developing Information Systems
Iré resumiendo los pasos que he realizado para hacer esta práctica.

## Modificando fichero _config.yml
He cambiado la skin del tema minimal mistakes de default a neon.

```
minimal_mistakes_skin : "neon" # "air", "aqua", "contrast", "dark", "dirt", "neon", "mint", "plum", "sunrise"
```

También el nombre para que se vea reflejado en la página:

```
name : &name "Aarón Ramírez" # &name is a YAML anchor which can be *referenced later
```

El baseurl también ha sido cambiado  para que contenga el nombre de su repositorio en GitHub:

```
baseurl : "/intro2sd-aaron-ramirez-valencia-alu0101438238/" # the subpath of your site, e.g. "/blog"
```

He creado una nueva collection:
```
# Collections
collections:
  docs:
    output: true
    permalink: /:collection/:path/
  recipes:
    output: true
    permalink: /:collection/:path/
  pets:
    output: true
    permalink: /:collection/:path/
  portfolio:
    output: true 
    permalink: /:collection/:path/
  DMSI:
    output: true # De forma predeterminada, las colecciones no generan una página para documentos. En este caso queremos que cada apartado tenga su propia página, así que modifiquemos la configuración de la colección.
    permalink: /:collection/:path/
```

```
  # _DMSI
  - scope:
      path: ""
      type: DMSI
    values:
      layout: single
      author_profile: true
      read_time: true
      comments: true
      share: true
      related: true
```

## Creación de nueva collection DMSI y uso de liquid
se ha creado un directorio llamado "_DMSI" que contiene un ejemplo de un bucle liquid a partir de un fichero DMSI.json en el directorio _data que contiene los datos de las listas a mostrar.

```json
[
    { "nombre": "Juan", "edad": 30, "pais": "México" },
    { "nombre": "Ana", "edad": 25, "pais": "España" },
    { "nombre": "Pedro", "edad": 28, "pais": "Argentina" }
  ]
```

```liquid
{% for persona in site.data.DMSI %}
- **Nombre**: {{ persona.nombre }}
- **Edad**: {{ persona.edad }} años
- **País**: {{ persona.pais }}
{% endfor %}
```

## Pages
### Página 404
Se ha reutilizado la página que nos ha proporcinado el profesor en los apuntes.

### DMSI.md
Aquí se tiene un listado de documentos de muestra para la colección `_DMSI_`.

## _posts
Se ha creado un nuevo post que contiene el resumen del Capítulo 1: Introduction to Systems Development. 