# CRM Safari · ATS & PAS

CRM de gestión de clientes para African Territory Safaris y Premium African Safaris.

## Cómo acceder
URL: *(se actualiza al hacer el deploy en Vercel)*

- **Usuario:** Laura o Fernando
- **Contraseña:** `safari2026` *(cámbiala en el código si quieres)*

## Qué hay en este proyecto

| Archivo | Qué es |
|---|---|
| `index.html` | Todo el CRM (una sola página, toda la lógica incluida) |
| `vercel.json` | Configuración para que Vercel sepa cómo publicar el sitio |
| `.gitignore` | Lista de archivos que Git ignora |

## Tecnologías usadas
- **Frontend:** HTML + CSS + JavaScript vanilla (sin frameworks)
- **Base de datos:** Supabase (PostgreSQL en la nube)
- **Hosting:** Vercel
- **Código:** GitHub

## Supabase — tabla necesaria
En el SQL Editor de Supabase, hay que tener creada esta tabla:

```sql
CREATE TABLE IF NOT EXISTS crm_data (
  id TEXT PRIMARY KEY,
  data JSONB NOT NULL DEFAULT '{}',
  updated_at TIMESTAMPTZ DEFAULT NOW()
);
ALTER TABLE crm_data REPLICA IDENTITY FULL;
```

## Cambiar la contraseña
Abre `index.html`, busca la línea:
```
const CRM_PASSWORD = 'safari2026';
```
Cambia `safari2026` por la contraseña que quieras, guarda, y haz un nuevo commit+push.

## Fases completadas
- [x] **Fase 1** — CRM online en Vercel con login y Supabase
- [ ] **Fase 2** — Migrar los 37 leads a tablas reales de Supabase
- [ ] **Fase 3** — Sincronización en tiempo real entre Laura y Fernando
- [ ] **Fase 4** — Documentos (PDFs) en Supabase Storage
- [ ] **Fase 5** — Dominio propio crm.africanterritory.com

## Historial de cambios
- **2026-05-20** · Fase 1: migración de window.storage a Supabase, login, deploy Vercel
