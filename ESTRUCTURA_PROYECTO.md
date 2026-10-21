# Estructura del proyecto

Mapa de las carpetas y archivos actuales del repositorio. Se omiten `.git/` y los artefactos locales de compilación (`backend/bin/`, `backend/obj/`, `frontend/node_modules/`, `frontend/dist/`).

```text
TecNM_Project_Template/
├── .gitignore
├── .obsidian/                              # Configuración local de Obsidian
│   ├── app.json
│   ├── appearance.json
│   ├── core-plugins.json
│   └── workspace.json
├── README.md                               # Descripción general y estándares
├── ESTRUCTURA_PROYECTO.md                  # Este diagrama
├── base_de_datos_completa.canvas           # Diagrama visual de base de datos
├── esquema.canvas                          # Diagrama visual de esquema
├── docker-compose.yml                      # Orquestación de servicios
├── backend/                                # API ASP.NET Core / .NET 10
│   ├── .env.example
│   ├── AGENTS.md
│   ├── Dockerfile
│   ├── Program.cs
│   ├── TecNM.Api.csproj
│   ├── appsettings.Development.json
│   ├── appsettings.json
│   ├── Core/
│   │   └── Entities/
│   │       └── User.cs
│   ├── Data/
│   │   └── TecNMDbContext.cs
│   ├── Modules/
│   │   ├── Auth/
│   │   │   ├── AuthController.cs
│   │   │   ├── AuthDTOs.cs
│   │   │   ├── AuthService.cs
│   │   │   └── specs/
│   │   │       └── auth.spec.md
│   │   ├── Compliance/
│   │   │   └── specs/
│   │   │       └── compliance_database_spec.md
│   │   ├── Metrics/
│   │   │   └── specs/
│   │   │       └── metrics_database_spec.md
│   │   ├── Referrals/
│   │   │   └── specs/
│   │   │       └── referrals_database_spec.md
│   │   └── backend/
│   │       └── Modules/
│   │           └── Health/
│   │               ├── HealthController.cs
│   │               ├── HealthDTOs.cs
│   │               ├── HealthService.cs
│   │               └── specs/
│   │                   └── health_spec.md
│   └── Properties/
│       └── launchSettings.json
├── database/                               # Scripts y documentación de bases de datos
│   ├── database.sql                        # Inicialización PostgreSQL del backend
│   ├── estructura_tablas.sql                # Esquema legado de tablas
│   ├── estructura_usuarios_alumnos.sql     # Esquema de usuarios y alumnos
│   ├── scriptAlumnosTEC.sql                 # Script de origen de alumnos
│   └── TutoriaDb/
│       ├── especificaciones_de_base_de_datos.md
│       └── init_tutoring_db.sql
├── doc/                                    # Documentación organizada por tema
│   ├── architecture/
│   │   ├── AUTH.md
│   │   ├── BACKEND_ARCHITECTURE.md
│   │   └── FRONTEND_ARCHITECTURE.md
│   ├── legacy-db/
│   │   ├── DIAGRAMA_ER_COMPLETO.md
│   │   ├── ESQUEMA_TABLAS.md
│   │   ├── esquema_tablas.html
│   │   └── visor_er.html
│   ├── plans/
│   │   └── 01-auth-implementation.md
│   └── specs/
│       ├── auth.spec.md
│       └── health.spec.md
├── frontend/                               # SPA Vue 3 + TypeScript + Vite
│   ├── .env.example
│   ├── .gitignore
│   ├── AGENTS.md
│   ├── DESIGN.md
│   ├── Dockerfile
│   ├── index.html
│   ├── nginx.conf
│   ├── package-lock.json
│   ├── package.json
│   ├── tsconfig.json
│   ├── vite.config.ts
│   ├── scripts/
│   │   └── check-layout.mjs
│   └── src/
│       ├── app/                            # Inicio, layout y enrutamiento
│       │   ├── App.vue
│       │   ├── main.ts
│       │   ├── layouts/
│       │   │   ├── MainLayout.vue
│       │   │   ├── mainLayout-spec.md
│       │   │   └── mainLayout.config.ts
│       │   └── router/
│       │       └── index.ts
│       ├── modules/                       # Funcionalidades por dominio
│       │   └── auth/
│       │       ├── index.ts
│       │       ├── routes.ts
│       │       ├── api/
│       │       │   └── authApi.ts
│       │       ├── components/
│       │       │   ├── LoginForm.vue
│       │       │   ├── LogoutButton.vue
│       │       │   └── pagination.spec.md
│       │       ├── specs/
│       │       │   └── auth.spec.md
│       │       ├── types/
│       │       │   └── auth.ts
│       │       └── views/
│       │           ├── LoginView.vue
│       │           └── SessionView.vue
│       └── shared/                        # Código compartido
│           ├── api/
│           │   └── http.ts
│           ├── assets/
│           │   └── tecnm-isologo.svg
│           ├── components/
│           │   ├── index.ts
│           │   ├── navigation.ts
│           │   ├── UiAlert.vue
│           │   ├── UiBadge.vue
│           │   ├── UiBasePage.vue
│           │   ├── UiBrand.vue
│           │   ├── UiButton.vue
│           │   ├── UiCallout.vue
│           │   ├── UiCard.vue
│           │   ├── UiChip.vue
│           │   ├── UiColorPalette.vue
│           │   ├── UiDialog.vue
│           │   ├── UiDisclosure.vue
│           │   ├── UiDivider.vue
│           │   ├── UiField.vue
│           │   ├── UiHeader.vue
│           │   ├── UiLayout.vue
│           │   ├── UiMetric.vue
│           │   ├── UiNavigation.vue
│           │   ├── UiNavLink.vue
│           │   ├── UiPageHeader.vue
│           │   ├── UiRadio.vue
│           │   ├── UiRange.vue
│           │   ├── UiSampleMark.vue
│           │   ├── UiShell.vue
│           │   ├── UiSidebar.vue
│           │   ├── UiTable.vue
│           │   ├── UiText.vue
│           │   ├── UiToast.vue
│           │   ├── UiToggle.vue
│           │   ├── UiTypeSample.vue
│           │   └── specs/
│           │       └── components.spec.md
│           ├── composables/
│           │   ├── useTheme-spec.md
│           │   └── useTheme.ts
│           ├── styles/
│           │   ├── colorTokens.ts
│           │   └── global.css
│           └── utils/
│               └── sessionCookie.ts
└── scripts/
    └── smoke-auth.sh                      # Prueba de humo de autenticación
```

## Organización por responsabilidad

- `backend/`: API, entidades, acceso a datos y módulos del servidor.
- `frontend/`: interfaz web, separada en composición (`app`), funcionalidades (`modules`) y piezas compartidas (`shared`).
- `database/`: scripts SQL de la aplicación y del esquema heredado, junto con material de TutoriaDb.
- `doc/`: arquitecturas, especificaciones, planes y documentación de la base de datos heredada.
- `scripts/`: automatizaciones y verificaciones auxiliares.
