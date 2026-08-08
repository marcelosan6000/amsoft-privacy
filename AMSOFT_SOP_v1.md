# 📘 AMSoft Launch Standard v1.0
## SOP de Google Play Console para nuevos juegos/apps
## (perfil: juego casual / utilidad · sin cuentas · sin IAP · monetización AdMob)

Propietario: Adrian (AMSoft) · Versión: 1.0 · Fecha: 07/08/2026
Proyecto de referencia: Block Puzzle Neon (com.amsoft.games.blockpuzzleneon)
REGLA DE ORO: Política de Privacidad ↔ Seguridad de datos ↔ SDK real
siempre dicen lo mismo. Cualquier SDK nuevo exige actualizar los 3.

---

## FASE 0 · PIEZAS ÚNICAS (se hacen una sola vez — verificar estado)
- [x] Cuenta Google Play Developer (pago único US$25)
- [x] Verificación de identidad del desarrollador
- [x] GitHub + repo `amsoft-privacy` con Pages activo
- [x] Plantilla Política de Privacidad v2.0 (index.html, bilingüe)
- [x] Plantilla Eliminación de Datos (eliminacion-datos.html, bilingüe)
- [ ] Cuenta AdMob creada y vinculada a Play Console  ← PENDIENTE
- [ ] Correo oficial AMSoft definido y sustituido en CONFIGs ← PENDIENTE
- [ ] Bóveda segura (gestor de contraseñas) para keystores

## FASE A · DISEÑO Y VALIDACIÓN (por app) ~1 h
- [ ] Análisis de nicho: demanda + competencia + factibilidad Kodular
- [ ] Package name congelado: com.amsoft.<genero>.<nombre>
      (minúsculas, sin guiones; INMUTABLE tras el primer AAB)
- [ ] Prototipo HTML/JS del core-loop probado y aprobado en navegador
- [ ] Mapa de monetización definido (dónde van Banner/Interstitial/Rewarded)

## FASE B · DOCUMENTOS LEGALES ~15 min
- [ ] index.html: añadir nombre + package de la nueva app a la lista
- [ ] eliminacion-datos.html: añadir nombre + package de la nueva app
- [ ] Commit → verificar que ambas URLs abren en público
- [ ] Correo CONFIG = correo oficial AMSoft

## FASE C · CREAR APLICACIÓN ~5 min
- [ ] Play Console → Todas las aplicaciones → Crear aplicación
- [ ] Nombre ≤30 con keyword (ASO) · Idioma: Inglés (EE.UU.)
- [ ] Tipo: Juego/App · Precio: Gratuita
- [ ] Casillas: Políticas ✔ · Firma de Play ✔ · Leyes exportación ✔
- [ ] Pulsar "Crear aplicación"

## FASE D · CONTENIDO DE LA APLICACIÓN (10 declaraciones) ~25 min
Respuestas estándar AMSoft (juego casual sin cuentas/IAP):
| Declaración              | Respuesta estándar                          |
|--------------------------|---------------------------------------------|
| Datos de inicio de sesión| NO                                          |
| Política de Privacidad   | URL de index.html → Guardar                 |
| Clasificación (IARC)     | Todo NO → PEGI 3/Everyone                   |
| Audiencia objetivo       | 13+ (coherente con política; evita Families)|
| Anuncios                 | SÍ (AdMob)                                  |
| ID de publicidad         | SÍ → Publicidad + Prevención de fraudes     |
| Salud / Finanzas / Gob.  | NO / NO / NO                                |
- [ ] IARC: pulsar GUARDAR antes de SIGUIENTE (el botón se habilita tras guardar)
- [ ] Verificar pestaña "Requiere atención" VACÍA
- [ ] "Protegida con Play": sin acción requerida para juegos casuales

## FASE E · SEGURIDAD DE LOS DATOS (detalle) ~10 min
- [ ] ¿Recoge/comparte? SÍ · ¿Cifrado en tránsito? SÍ
- [ ] Cuentas: "no permite crear cuenta" ✔ · login externo NO
- [ ] Eliminación: SÍ + URL de eliminacion-datos.html
- [ ] Tipos de datos (3): Ubicación aproximada · Interacciones con
      anuncios · IDs de dispositivo. Cada uno:
      Se recogen ✔ Se comparten ✔ · NO temporal · Necesaria ·
      Finalidad: Publicidad (+Fraudes solo en IDs)
- [ ] Vista previa muestra los 3 tipos + eliminación + cifrado → Guardar

## FASE F · FICHA DE PLAY STORE ~40 min
- [ ] Título ≤30 · Corta ≤80 · Larga ≤4000 (EN por defecto + traducción ES)
- [ ] Ícono PNG 512×512 ≤1024 KB (plantilla SVG neón AMSoft)
- [ ] Gráfico destacado 1024×500 (plantilla SVG)
- [ ] Capturas ≥2 (recom. 6) 1080×1920/2340
      Truco: prototipo en Chrome → F12 → modo dispositivo → screenshot
- [ ] Categoría: Juegos → Puzzle · Contacto: correo oficial + web GitHub

## FASE G · CONSTRUCCIÓN Y PRUEBAS (Kodular) ~variable
- [ ] Construir según Plano de Arquitectura del juego
- [ ] Manifiesto verificado: INTERNET + com.google.android.gms.permission.AD_ID
- [ ] IDs AdMob CONFIG reemplazados (Banner/Interstitial/Rewarded)
- [ ] UMP (mensaje de consentimiento EEA/UK) integrado — obligatorio con AdMob
- [ ] Prueba en dispositivo físico: loop, líneas, game-over, récord, anuncios
- [ ] Exportar AAB (nunca APK) + respaldar keystore en bóveda
- [ ] Pista Prueba INTERNA (iteración rápida, sin revisión)
- [ ] Pista Prueba CERRADA + ≥12 testers opted-in → ARRANCA RELOJ 14 DÍAS
- [ ] Día 15: solicitar acceso a producción → enviar a revisión

## FASE H · LANZAMIENTO Y MONITOREO
- [ ] Precios y distribución: Gratuita · todos los mercados
- [ ] Monitorizar: Android vitals · reseñas · Estado según políticas
- [ ] Si se añade SDK nuevo → actualizar Fase B + E antes del release

---

## APÉNDICE D · TRAMPAS CONOCIDAS (aprendidas en proyecto #1)
1. IARC: "Siguiente" gris hasta pulsar "Guardar".
2. Prueba INTERNA ≠ Prueba CERRADA: solo la cerrada cuenta los 14 días.
3. Apps de "ganar dinero" = baneo seguro; nunca declarar mecánicas de pago al usuario.
4. Audiencia <13 activa Política de Familias (requisitos extra); por eso 13+.
5. Declarar "no recoge datos" con AdMob integrado = rechazo por declaración falsa.
6. Package name inmutable tras el primer AAB: congelar en Fase A.
