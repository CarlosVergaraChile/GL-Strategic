# GL-Strategic - Sitio Web Corporativo

> **Código Red Reutilizable** | Arquitectura Desplegable a Múltiples Plataformas

## 📋 Descripción

GL-Strategic es un sitio web corporativo moderno, construido con arquitectura agnóstica de hosting. Puede desplegarse a:
- **Hostinger** (FTP/SSH)
- **Vercel** (Deploy automático desde GitHub)
- **Netlify** (Deploy automático)
- **AWS S3 + CloudFront** (para escala)
- **Otros servidores** (mediante Git)

## 🎯 Características

- ✅ Sitio estático HTML/CSS/JS (sin dependencias complejas)
- ✅ Responsive design (Mobile-first)
- ✅ SEO optimizado (meta tags, structured data)
- ✅ Performance optimizado (lazy loading, minificación)
- ✅ Deployment automático con GitHub Actions
- ✅ SSL/TLS gratis en todos los hosting
- ✅ Integración con Flow.cl para contactos/leads

## 📁 Estructura del Proyecto

```
GL-Strategic/
├── src/
│   ├── index.html          # Página principal
│   ├── pages/              # Páginas adicionales
│   │   ├── about.html
│   │   ├── services.html
│   │   ├── contact.html
│   │   └── blog/
│   ├── css/
│   │   ├── styles.css      # Estilos principales
│   │   └── responsive.css  # Media queries
│   ├── js/
│   │   ├── main.js         # Lógica principal
│   │   └── utils.js        # Utilidades
│   └── assets/
│       ├── images/
│       ├── fonts/
│       └── icons/
├── docs/
│   ├── DEPLOYMENT.md       # Guía de deployment
│   ├── ARCHITECTURE.md     # Decisiones técnicas
│   ├── SEO.md             # Estrategia SEO
│   └── MONITORING.md      # Monitoreo y alertas
├── .github/
│   └── workflows/
│       ├── deploy-hostinger.yml
│       ├── deploy-vercel.yml
│       └── ci.yml
├── config/
│   ├── config.example.js   # Variables de ambiente
│   └── deployment.env.example
├── .gitignore
├── package.json            # Dependencias (si aplica)
└── README.md
```

## 🚀 Quick Start

### Desarrollo Local

```bash
# Clonar
git clone https://github.com/CarlosVergaraChile/GL-Strategic.git
cd GL-Strategic

# Servidor local (Python)
python -m http.server 8000

# O usar Live Server si tienes Node.js
npx http-server src/ -p 8000

# Abrir en navegador
open http://localhost:8000
```

### Deploy a Hostinger

Ver `docs/DEPLOYMENT.md` para instrucciones detalladas.

```bash
# 1. Conectar con SSH
ssh usuario@hostinger.com

# 2. Navegar a public_html
cd public_html/gl-strategic/

# 3. Git pull
git pull origin main
```

### Deploy Automático (GitHub Actions)

Ver `.github/workflows/` para configuración.

**Pushea a main** → Trigger automático → Deploy a Hostinger/Vercel

## 📊 Deployment Matrix

| Plataforma | Tipo | Auto-Deploy | Costo | CDN | SSL |
|---|---|---|---|---|---|
| **Hostinger** | VPS/Shared | ✅ (Actions) | $36/año | ❌ | ✅ |
| **Vercel** | Serverless | ✅ (Automático) | Gratis | ✅ | ✅ |
| **Netlify** | Serverless | ✅ (Automático) | Gratis | ✅ | ✅ |
| **AWS S3+CloudFront** | Static+CDN | ✅ (Actions) | ~$3/mes | ✅ | ✅ |

## 🔐 Secretos y Configuración

**NO commitear nunca:**
- `.env.local`
- `config.local.js`
- API keys
- Credenciales SSH

**Usar GitHub Secrets para:**
- HOSTINGER_SSH_KEY
- HOSTINGER_SSH_HOST
- HOSTINGER_SSH_USER
- VERCEL_TOKEN
- NETLIFY_SITE_ID
- NETLIFY_AUTH_TOKEN

Ver `.github/workflows/` para uso en CI/CD.

## 📈 Monitoreo

- **Google Analytics 4**: Tráfico y comportamiento de usuarios
- **Lighthouse CI**: Performance audits automáticos
- **GitHub Actions**: Build/Deploy notifications
- **Uptime Monitor**: Alertas si el sitio cae

## 🔄 Flujo de Trabajo (Git)

```
main (production)
  ↑
  └── staging (pre-production)
      ↑
      └── feature/* (development)
```

**Proceso:**
1. Crear feature branch: `git checkout -b feature/nueva-seccion`
2. Hacer cambios y commit
3. Push a GitHub: `git push origin feature/nueva-seccion`
4. Crear Pull Request
5. Review y merge a `staging`
6. Test en staging
7. Merge a `main` → **Deploy automático**

## 📝 Documentación

- [`DEPLOYMENT.md`](./docs/DEPLOYMENT.md) - Guía detallada de deployment
- [`ARCHITECTURE.md`](./docs/ARCHITECTURE.md) - Decisiones de arquitectura
- [`SEO.md`](./docs/SEO.md) - Estrategia de SEO
- [`MONITORING.md`](./docs/MONITORING.md) - Monitoreo y alertas

## 🛠️ Tecnologías

- **Frontend**: HTML5, CSS3, JavaScript (ES6+)
- **Hosting**: Hostinger, Vercel, Netlify, AWS
- **CI/CD**: GitHub Actions
- **Monitoreo**: Google Analytics 4, Lighthouse
- **Analytics**: Mixpanel (opcional)

## 📞 Contacto & Soporte

- GitHub Issues: [Reportar bugs](https://github.com/CarlosVergaraChile/GL-Strategic/issues)
- Email: soporte@glstrategic.com
- Documentación técnica: Ver `/docs`

## 📄 Licencia

Privado - GL Strategic

---

**Último actualizado:** 2025-12-16

**Mantenedor:** CarlosVergaraChile (Gerente Técnico)
