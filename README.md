# Mi Municipio — entrega para revisión y presentación (13 noviembre 2026)

## Despliegue

1. Descomprime este ZIP.
2. En Netlify > Add new project > Deploy manually, arrastra la carpeta que contiene `index.html`, `sw.js`, `manifest.webmanifest` y `icons/`.
3. Abre la dirección HTTPS de Netlify. Chrome/Edge compatibles pueden ofrecer «Instalar». En Safari para iPhone/iPad usa Compartir > Añadir a pantalla de inicio.
4. Para pruebas de roles administrativos es necesario crear cuentas reales en Supabase Auth y asignarles su rol en `public.profiles` mediante un procedimiento administrativo autorizado. No existen cuentas de administrador precreadas en la base de datos.

## Proyecto conectado

Supabase: Mi Municipio Nuevo, ref `weosqhohvstctwdnahac`. La clave incluida es **publishable**, apta para cliente; nunca se incluyen claves secretas ni service_role.

## Funciones implementadas en el paquete

- Registro e ingreso con Supabase Auth, recuperación por correo y sesión persistente.
- Perfil ciudadano automático mediante trigger; catálogo de categorías y dependencias.
- Nuevo reporte con descripción, dirección, mapa Leaflet, GPS y folio generado por servidor.
- Asignación automática por categoría mediante trigger.
- Detección de un reporte de igual categoría a 5 m mediante función de base de datos y opción de apoyar un expediente existente.
- Consulta por folio para usuarios autorizados, listado según RLS.
- Actualización de estados por personal autorizado.
- Notas internas, asignaciones adicionales y subida/consulta de documentos en almacenamiento privado según permisos.
- Mapa de reportes visibles, estadísticas, CSV, avisos y administración básica de dependencias/categorías.
- PWA con manifest, iconos y service worker.

## Limitaciones que deben conocerse

- **No se han efectuado pruebas de extremo a extremo con cuentas de ciudadanos, funcionarios y administradores reales.** La base de datos consultada tenía cero usuarios.
- No está implementada la creación segura de funcionarios desde la interfaz, el primer cambio obligatorio de credenciales administrativas, eliminación completa de cuentas, auditoría integral, encuestas, fondo/logotipos institucionales definitivos, ni generación PDF nativa (el navegador permite imprimir o guardar PDF).
- La interfaz es una versión simplificada; el HTML anterior se conserva en `referencia_diseno_original/` para su recuperación, no es la interfaz conectada.
- Las notificaciones de instalación varían por navegador y sistema operativo. Requiere HTTPS y conexión para mapas y datos.
- No sustituir el sitio oficial ni recibir información ciudadana sensible antes de probar RLS, altas, cargas y roles.

## Para presentar

Se puede mostrar la pantalla inicial y la instalación PWA. Para demostrar creación/seguimiento real, primero se requiere registrar una cuenta de prueba y confirmar correo si Supabase lo solicita. Para mostrar el panel institucional es indispensable aprovisionar cuentas con rol autorizado.
