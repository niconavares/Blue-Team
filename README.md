# Práctica Blue Team - Infraestructura SIEM

Implementación de una infraestructura de seguridad completa basada en SIEM (Security Information and Event Management) con Elastic Stack, integrando múltiples fuentes de logs en una arquitectura de red segmentada.

## 📋 Descripción

Este proyecto documenta el diseño, implementación y validación de una infraestructura de monitorización de seguridad que incluye:

- **Segmentación de red** con pfSense (LAN, DMZ, DMZ2)
- **Honeypot SSH** con Cowrie para captura de intentos de intrusión
- **IDS/IPS** con Suricata para detección de amenazas
- **SIEM centralizado** con Elastic Stack en cloud
- **Monitorización de endpoints** Windows con Elastic Agent

## 🏗️ Arquitectura
```
┌─────────────┐     ┌─────────────┐     ┌─────────────┐
│    LAN      │     │    DMZ      │     │   DMZ2      │
│ Windows 10  │     │  Honeypot   │     │  Suricata   │
│ 192.168.100 │     │ 192.168.200 │     │ 192.168.250 │
└──────┬──────┘     └──────┬──────┘     └──────┬──────┘
       │                   │                   │
       └───────────────────┼───────────────────┘
                           │
                    ┌──────┴──────┐
                    │   pfSense   │
                    │    WAN      │
                    └──────┬──────┘
                           │
                    ┌──────┴──────┐
                    │   Internet  │
                    │ Elastic Cloud│
                    └─────────────┘
```

## 🛠️ Tecnologías

| Componente | Versión |
|------------|---------|
| pfSense | 2.7.2-RELEASE |
| Elastic Agent | 9.2.4 |
| Cowrie | Docker latest |
| Suricata | 6.x |
| Kali Linux | 2025.4 |
| Windows 10 | Build 19045.5247 |

## 📁 Estructura del Repositorio
```
├── Practica Blue-Team.pdf    # Documentación completa
├── Capturas Practica/        # Screenshots de la implementación
└── README.md
```

## 🎯 Objetivos Cumplidos

- [x] Infraestructura de red segmentada con múltiples DMZs
- [x] Reglas de firewall con principio de mínimo privilegio
- [x] Honeypot operativo capturando sesiones SSH
- [x] Suricata detectando y registrando tráfico
- [x] Logs centralizados con IPs correctas por segmento
- [x] Análisis detallado de estructura JSON de eventos

## 📚 Referencias

- [pfSense Documentation](https://docs.netgate.com/pfsense/)
- [Elastic Security](https://www.elastic.co/guide/en/security/current/)
- [Cowrie Honeypot](https://github.com/cowrie/cowrie)
- [Suricata Documentation](https://docs.suricata.io/)

---

**Bootcamp Ciberseguridad** - KeepCoding @ Google Campus | Enero 2026
