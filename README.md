# ReleEasy Cloud - Demo

Aplicación Angular mínima (una sola página con un contador) que sirve como repositorio
de prueba para desplegar con la plantilla `angular-static` de ReleEasy Cloud
(S3 + CloudFront).

## Estructura

El pipeline de ReleEasy espera el front en la carpeta `frontend/` del repositorio:

```
frontend/
  package.json, package-lock.json, angular.json
  src/        código de la aplicación
  public/     recursos estáticos
```

## Compilar en local

Requisitos: Node.js 22.12+ o 24 (ver `.nvmrc`).

```bash
cd frontend
npm ci
npm run build      # salida en frontend/dist/releasy-demo/browser
npm start          # servidor de desarrollo en http://localhost:4200
```

## Uso con ReleEasy

En el build de ReleEasy se ejecuta `cd frontend && npm ci && npm run build` y se publica
el contenido de `frontend/dist/*/browser` en el bucket S3 del sitio. Tras el despliegue,
la página debe mostrar el título y el contador debe responder al botón (comprueba que el
JavaScript se ha servido correctamente).
