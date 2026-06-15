# Power BI — Dashboard Ejecutivo de KPIs Financieros

Colección de medidas DAX avanzadas, plantillas de modelo de datos y guías de diseño para dashboards ejecutivos en el sector financiero. Desarrollado con base en experiencia real reportando a vicepresidentes y gerencias.

## Objetivo

Proporcionar un conjunto reutilizable de medidas DAX, buenas prácticas de modelado y estructuras de informes para dashboards financieros que combinen precisión analítica con claridad ejecutiva.

## Estructura

```
bi-dashboard-kpis/
├── README.md
├── dax/
│   ├── medidas_base.dax          # KPIs fundamentales
│   ├── medidas_tiempo.dax        # Inteligencia de tiempo (YTD, MTD, LY)
│   ├── medidas_aml.dax           # Indicadores de cumplimiento AML
│   └── medidas_calidad.dax       # Métricas de calidad de datos
├── sql/
│   └── queries_base_reportes.sql  # Consultas fuente para reportes
├── docs/
│   ├── guia_modelado.md
│   └── convenciones_dax.md
└── screenshots/
    └── dashboard_preview.png
```

## 📐 Modelo de Datos

El modelo sigue un **esquema estrella limpio** para máximo rendimiento en DAX:

- Una tabla de hechos central: `fact_transacciones`
- Dimensiones de rol: `dim_cliente`, `dim_tiempo`, `dim_producto`, `dim_canal`
- Sin relaciones muchos-a-muchos directas (se resuelven con tablas puente)
- Columnas innecesarias ocultas para UX limpia

## KPIs Incluidos

| KPI | Descripción |
|---|---|
| Total Transacciones | Volumen y monto del período |
| Crecimiento MoM / YoY | Comparativo mensual y anual |
| Saldo Promedio por Segmento | Por Masivo / Preferencial / Premium |
| Ratio de Morosidad | Préstamos vencidos vs. cartera total |
| Índice de Calidad de Datos | % registros sin inconsistencias |
| Alertas AML | Transacciones sobre umbral regulatorio |

## Cómo Usar

1. Conectar Power BI al DWH (SQL Server)
2. Importar las medidas DAX desde `/dax/`
3. Configurar slicers de fecha, segmento y canal
4. Publicar en Power BI Service con actualización programada

---
*Randy J. Tejeda Y. — BI Analyst | Santo Domingo, RD*
