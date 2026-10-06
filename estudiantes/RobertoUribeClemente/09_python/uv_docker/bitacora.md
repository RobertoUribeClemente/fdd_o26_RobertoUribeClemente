# Bitácora — uv dentro de Docker

## Quién soy

- Usuario de GitHub: RobertoUribeClemente
- Usuario de Docker Hub: bobuc05

## El paquete que agregaste

Paquete: numpy

Para qué lo usa tu fila: Instancia una matriz bidimensional 2x2 mediante np.array([[1, 2], [3, 4]]) 
y muestra su contenido en la tabla del ambiente.

## Salida en tu máquina

La salida completa del reporte corrido con uv en tu máquina.

```text
Mi ambiente                              
┏━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┓
┃ Qué              ┃ Valor                                           ┃
┡━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┩
│ Python           │ 3.14.4                                          │
│ Intérprete       │ /home/bobuc05/fdd/fdd_o26_RobertoUribeClemente/ │
│                  │ estudiantes/RobertoUribeClemente/09_python/     │
│                  │ uv_docker/.venv/bin/python                      │
│ sys.prefix       │ /home/bobuc05/fdd/fdd_o26_RobertoUribeClemente/ │
│                  │ estudiantes/RobertoUribeClemente/09_python/     │
│                  │ uv_docker/.venv                                 │
│ ¿En un ambiente? │ sí                                              │
│ Sistema          │ Linux x86_64                                    │
│ NumPy            │ Matriz 2x2: [[1, 2], [3, 4]]                    │
└──────────────────┴─────────────────────────────────────────────────┘
     Paquetes instalados     
┏━━━━━━━━━━━━━━━━┳━━━━━━━━━━┓
┃ Paquete        ┃ Versión  ┃
┡━━━━━━━━━━━━━━━━╇━━━━━━━━━━┩
│ Pygments       │ 2.21.0   │
│ markdown-it-py │ 4.2.0    │
│ mdurl          │ 0.1.2    │
│ numpy          │ 2.5.3    │
│ rich           │ 15.0.0   │
└────────────────┴──────────┘

```

## Salida en el contenedor

La salida completa del reporte corrido desde tu imagen.

```text
Mi ambiente                    
┏━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┓
┃ Qué              ┃ Valor                        ┃
┡━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┩
│ Python           │ 3.13.16                      │
│ Intérprete       │ /app/.venv/bin/python        │
│ sys.prefix       │ /app/.venv                   │
│ ¿En un ambiente? │ sí                           │
│ Sistema          │ Linux x86_64                 │
│ NumPy            │ Matriz 2x2: [[1, 2], [3, 4]] │
└──────────────────┴──────────────────────────────┘
    Paquetes instalados     
┏━━━━━━━━━━━━━━━━┳━━━━━━━━━┓
┃ Paquete        ┃ Versión ┃
┡━━━━━━━━━━━━━━━━╇━━━━━━━━━┩
│ Pygments       │ 2.21.0  │
│ markdown-it-py │ 4.2.0   │
│ mdurl          │ 0.1.2   │
│ numpy          │ 2.5.3   │
│ rich           │ 15.0.0  │
└────────────────┴─────────┘

```

## Qué cambió y qué no

Tres líneas, con los valores de arriba: qué salió igual en las dos, qué salió
distinto, y por qué.

- Igual: Las versiones de todos los paquetes (numpy 2.5.3, rich 15.0.0, Pygments 2.21.0, markdown-it-py 4.2.0, mdurl 0.1.2) y el valor de la fila propia.
- Distinto: La versión de Python (3.14.4 vs 3.13.16) y las rutas de Intérprete y sys.prefix (/home/bobuc05/.../uv_docker/.venv vs /app/.venv).
- Por qué: uv.lock fija determinísticamente las librerías, pero el runtime de Python y las rutas dependen del sistema operativo anfitrión y de la imagen base.

## Tu imagen en Docker Hub

URL pública: https://hub.docker.com/r/bobuc05/uv-reporte

Digest: sha256:3633647237b0ae313e266343e599026931ed52ea997e7143cd5d1982e1693820

Comando para correrla: docker run --rm docker.io/bobuc05/uv-reporte

## Prueba de que se baja del registro

La salida completa, en este orden, de cerrar sesión en el registro, borrar
tu imagen local con la bandera de forzar, y correrla otra vez.

```text
bobuc05@bobuc05-MCLG-XX:~/fdd/fdd_o26_RobertoUribeClemente/estudiantes/RobertoUribeClemente/09_python/uv_docker$ docker logout docker.io
Not logged in to [https://index.docker.io/v1/](https://index.docker.io/v1/)
bobuc05@bobuc05-MCLG-XX:~/fdd/fdd_o26_RobertoUribeClemente/estudiantes/RobertoUribeClemente/09_python/uv_docker$ docker rmi -f bobuc05/uv-reporte
Untagged: bobuc05/uv-reporte:latest
Untagged: bobuc05/uv-reporte@sha256:3633647237b0ae313e266343e599026931ed52ea997e7143cd5d1982e1693820
Deleted: sha256:ceb921f59ba9a69fa4310588b82816d53f259410486297590ea732b574ef6169
bobuc05@bobuc05-MCLG-XX:~/fdd/fdd_o26_RobertoUribeClemente/estudiantes/RobertoUribeClemente/09_python/uv_docker$ docker run --rm docker.io/bobuc05/uv-reporte
Unable to find image 'docker.io/bobuc05/uv-reporte:latest' locally
latest: Pulling from bobuc05/uv-reporte
d175833b7147: Pull complete
acbf34fa608c: Pull complete
15f1c8eb1ab1: Pull complete
285510654d1d: Pull complete
66cb736eebc2: Pull complete
65ecf672bc4b: Pull complete
06fe3759dd1b: Pull complete
05d66c4250ea: Pull complete
1f59070073e0: Pull complete
Digest: sha256:3633647237b0ae313e266343e599026931ed52ea997e7143cd5d1982e1693820
Status: Downloaded newer image for docker.io/bobuc05/uv-reporte:latest
                    Mi ambiente                    
┏━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┓
┃ Qué              ┃ Valor                        ┃
┡━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┩
│ Python           │ 3.13.16                      │
│ Intérprete       │ /app/.venv/bin/python        │
│ sys.prefix       │ /app/.venv                   │
│ ¿En un ambiente? │ sí                           │
│ Sistema          │ Linux x86_64                 │
│ NumPy            │ Matriz 2x2: [[1, 2], [3, 4]] │
└──────────────────┴──────────────────────────────┘
    Paquetes instalados     
┏━━━━━━━━━━━━━━━━┳━━━━━━━━━┓
┃ Paquete        ┃ Versión ┃
┡━━━━━━━━━━━━━━━━╇━━━━━━━━━┩
│ Pygments       │ 2.21.0  │
│ markdown-it-py │ 4.2.0   │
│ mdurl          │ 0.1.2   │
│ numpy          │ 2.5.3   │
│ rich           │ 15.0.0  │
└────────────────┴─────────┘
```
