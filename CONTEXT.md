# COMBRIDGE Landing Page — Contexto del Proyecto

## Qué es esto
Landing page de una sola página para promocionar **COMBRIDGE**, un taller experiencial de Comtraining (comtraining.cl) en el que equipos corporativos construyen un puente de 14 metros con 9.000 piezas en 90 minutos para desarrollar liderazgo, colaboración y gestión de proyectos.

## Dominio de producción
`https://combridge.comtraining.cl`

## Objetivo de negocio
**CTA principal:** que el visitante agende una reunión con Francisco Vallés mediante Cal.com embebido.
- Usuario Cal.com: `fjvalles`
- URL base: `https://cal.com/fjvalles`
- Embed: usar `@calcom/embed-react` o el snippet oficial de iframe embed inline

**CTA secundario:** scroll a la sección de experiencia para seguir explorando antes de agendar.

## Audiencia objetivo
Tomadores de decisión B2B en Chile y Latinoamérica:
- Gerentes de RRHH / People / Desarrollo Organizacional
- Gerentes de proyectos (especialmente minería, telecom, energía, tecnología, financiera, retail)
- Líderes de equipos en transformación

Son profesionales ocupados. La landing debe comunicar la propuesta de valor en los primeros 5 segundos.

## Propuesta de valor (una frase)
"Construye un puente de 14 metros en 90 minutos con tu equipo y transforma la forma en que colaboran, lideran y ejecutan proyectos."

## Tono
- Profesional pero cercano, español de Chile
- Confiado, no exagerado
- Orientado a resultados concretos
- Tutear al lector ("tú", "tu equipo")

## Identidad visual
Basada en el brochure existente de Comtraining:
- **Azul corporativo oscuro** (header del brochure): `#3E5C76` aprox.
- **Rojo COMTRAINING** (logo): `#E63946` aprox.
- **Blanco / gris claro** para fondos
- **Gris oscuro** para texto: `#1F2937`
- Tipografía sans-serif profesional: Inter (Google Fonts)
- Fotos reales del taller (no stock)

## Secciones de la landing (orden)
1. **Hero** — Imagen del puente real, título "COMBRIDGE", subtítulo de valor, CTA "Agendar reunión"
2. **Números que impactan** — 14m / 9.000 piezas / 90 min / 35 personas (grid de 4)
3. **La experiencia** — Copy emocional + fotos del equipo trabajando
4. **4 aprendizajes clave** — Cards con los objetivos del taller
5. **¿Para quién es?** — 3 perfiles: líderes, equipos de proyecto, organizaciones en transformación
6. **Industrias donde funciona** — Iconos de minería, telecom, energía, tecnología, financiera, retail
7. **El profesor** — Francisco Vallés con credenciales resumidas
8. **Logística** — 4h / presencial / hasta 35 personas / in company
9. **CTA final con Cal.com embebido** (`fjvalles`)
10. **Footer** con enlace a comtraining.cl, redes sociales, mail

## Contenido clave (copy base, refinable)

### Hero
- Título: **COMBRIDGE**
- Subtítulo: "Construye un puente y logra lo imposible a través de la colaboración en equipo y la gestión de proyectos."
- CTA primario: "Agenda una reunión" → scroll suave a `#agendar`
- CTA secundario: "Ver la experiencia" → scroll suave a `#experiencia`

### Números
- **14 metros** de puente construido
- **9.000 piezas** ensambladas
- **90 minutos** de ejecución
- **35 personas** máximo por taller

### Aprendizajes clave (cards)
1. **Definir y lograr objetivos claros** en trabajo de equipo
2. **Colaborar** compartiendo recursos, asignando tareas y manteniendo alta calidad
3. **Comunicarse** efectivamente y con frecuencia
4. **Lograr lo imposible** alineando esfuerzos individuales, de equipo y organizacionales

### Profesor
Francisco Vallés. Consultor y coach senior con más de 25 años de experiencia. Socio de Comtraining. Profesor en UAI y UTEC Lima. Ingeniero Civil Industrial PUC, Máster en PNL.

### Logística
- Duración: 4 horas
- Modalidad: presencial
- Capacidad: hasta 35 personas
- Modelo: in-company (vamos donde tu equipo esté)

## Integración Cal.com — instrucciones específicas

Instalar el paquete oficial:
```bash
npm install @calcom/embed-react
```

En la sección `#agendar`, embeber el calendario inline (no como popup), apuntando a `fjvalles`. Configurar el theme para que respete los colores corporativos (`brandColor: "#3E5C76"`). El embed debe ocupar ancho completo en mobile y un max-width de ~900px en desktop centrado.

Alternativa si el paquete React da problemas con Astro: usar el snippet oficial de iframe embed que Cal.com genera en su dashboard para el link de `fjvalles`.

## Stack técnico
- **Astro** (static site)
- **Tailwind CSS** para estilos
- **Lucide** para iconos (`lucide-astro` o `@lucide/astro`)
- **@calcom/embed-react** para agendamiento
- **Vercel** para hosting (deploy desde GitHub)
- Optimización de imágenes con `<Image />` de Astro (astro:assets)
- Meta tags SEO + Open Graph completos (para LinkedIn/WhatsApp)

## SEO y Open Graph
- Title: "COMBRIDGE | Taller de liderazgo y gestión de proyectos — Comtraining"
- Description: "Construye un puente de 14 metros con tu equipo en 90 minutos. Taller experiencial de colaboración, liderazgo y gestión de proyectos. In-company en Chile."
- OG image: `/og-image.jpg` (1200x630, generar con el puente + título)
- Twitter card: `summary_large_image`
- Canonical: `https://combridge.comtraining.cl`
- `hreflang="es-CL"`
- Schema.org: tipo `Course` con provider Comtraining

## Restricciones
- Debe verse perfecto en mobile (la mayoría llegará desde LinkedIn mobile)
- Lighthouse score objetivo: 95+ en todas las categorías
- Tiempo de carga objetivo: < 1.5s en 3G
- Todo el texto en español
- Accesibilidad WCAG AA (contraste, alt texts, navegación por teclado)

## Assets disponibles en /public/images/
- `hero-puente.jpg` — Puente real de noche (página 1 del brochure)
- `equipo-mesa.jpg` — Equipo planificando en la mesa
- `equipo-grupal.jpg` — Equipo completo con puente terminado
- `cascos.jpg` — Cascos de colores del taller
- `puente-estructural.jpg` — Puente con gente caminando encima
- `logo-comtraining.png` — Logo con fondo transparente
- `francisco-valles.jpg` — Foto del profesor (conseguir)

En `/public/`:
- `og-image.jpg` — Imagen 1200x630 para compartir en redes
- `favicon.svg`

## Deploy en Vercel con subdominio combridge.comtraining.cl

1. Push del repo a GitHub
2. En Vercel: Import Project → seleccionar repo → framework Astro se detecta solo
3. En Settings → Domains: agregar `combridge.comtraining.cl`
4. Vercel mostrará un registro DNS tipo CNAME a crear
5. En el panel DNS de comtraining.cl (donde sea que esté hospedado: NIC.cl, Cloudflare, etc.), crear:
   ```
   Tipo: CNAME
   Nombre: combridge
   Valor: cname.vercel-dns.com
   TTL: 3600
   ```
6. Esperar propagación (~15 min) y Vercel emite certificado SSL automáticamente
7. Validar que `https://combridge.comtraining.cl` cargue y tenga candado verde

## Integraciones pendientes de definir
- [ ] ID de Google Analytics 4 o dominio en Plausible
- [ ] URLs de redes sociales de Comtraining (LinkedIn, Instagram)
- [ ] Mail de contacto secundario por si alguien no quiere agendar
- [ ] Foto profesional de Francisco Vallés

## Cómo trabajar con Claude Code en este proyecto
1. Comienza cada sesión pidiendo que lea este archivo (`Lee CONTEXT.md y resúmeme el proyecto antes de empezar`)
2. Trabaja por secciones, no intentes construir toda la landing en una sola tanda
3. Después de cada sección visual, revísala en mobile antes de continuar
4. Al terminar, pide a Claude Code que ejecute Lighthouse y optimice los hallazgos
5. Antes del deploy final, pide que valide que todos los links internos funcionen y que el embed de Cal.com de `fjvalles` cargue correctamente
