<div align="center">
  
# Apuntes de Ciberseguridad

![Ciberseguridad](https://img.shields.io/badge/Ciberseguridad-Apuntes-red?style=for-the-badge)
![Estado](https://img.shields.io/badge/Estado-En%20Desarrollo-yellow?style=for-the-badge)
![Licencia](https://img.shields.io/badge/Licencia-MIT-blue?style=for-the-badge)

</div>

## Descripción

Repositorio de apuntes, guías y recursos sobre ciberseguridad. Este proyecto recopila conocimientos fundamentales, herramientas, técnicas y buenas prácticas en el campo de la seguridad informática.

## Objetivo

Crear una base de conocimientos estructurada y accesible sobre ciberseguridad que sirva como referencia para estudiantes, profesionales y entusiastas de la seguridad informática.

---

## Índice de Contenidos

### Conocimientos necesarios previos
- [Redes informáticas](./fundamentos/introduccion.md)
- [Aplicaciones web](./fundamentos/conceptos-basicos.md)
- [Sistemas Operativos](./fundamentos/cia-triad.md)
- [Introducción a Linux](./fundamentos/amenazas-vulnerabilidades.md)
- [Hardware básico](./fundamentos/modelos-seguridad.md)

### Seguridad de Redes
- [Fundamentos de Redes](./redes/fundamentos-redes.md)
- [Protocolos de Red y Seguridad](./redes/protocolos.md)
- [Firewalls y IDS/IPS](./redes/firewalls-ids-ips.md)
- [VPN y Túneles Seguros](./redes/vpn.md)
- [Seguridad en Redes Inalámbricas](./redes/wireless.md)
- [Segmentación de Redes y VLANs](./redes/segmentacion.md)

### Criptografía
- [Fundamentos de Criptografía](./criptografia/fundamentos.md)
- [Cifrado Simétrico](./criptografia/simetrico.md)
- [Cifrado Asimétrico](./criptografia/asimetrico.md)
- [Funciones Hash](./criptografia/hash.md)
- [Certificados Digitales y PKI](./criptografia/certificados-pki.md)
- [Protocolos Criptográficos](./criptografia/protocolos.md)

### Seguridad Defensiva
- [Hardening de Sistemas](./defensiva/hardening.md)
- [Gestión de Parches](./defensiva/patch-management.md)
- [Antivirus y Anti-malware](./defensiva/antivirus.md)
- [SIEM y Correlación de Eventos](./defensiva/siem.md)
- [Respuesta a Incidentes](./defensiva/incident-response.md)
- [Forense Digital](./defensiva/forense.md)

### Seguridad Ofensiva
- [Metodologías de Pentesting](./ofensiva/metodologias.md)
- [Reconocimiento y OSINT](./ofensiva/reconocimiento.md)
- [Escaneo y Enumeración](./ofensiva/escaneo.md)
- [Explotación de Vulnerabilidades](./ofensiva/explotacion.md)
- [Post-Explotación](./ofensiva/post-explotacion.md)
- [Ingeniería Social](./ofensiva/ingenieria-social.md)

### Seguridad Web
- [OWASP Top 10](./web/owasp-top10.md)
- [Inyección SQL](./web/sql-injection.md)
- [Cross-Site Scripting (XSS)](./web/xss.md)
- [Cross-Site Request Forgery (CSRF)](./web/csrf.md)
- [Autenticación y Autorización](./web/auth.md)
- [Seguridad en APIs](./web/api-security.md)

### Cloud Security
- [Fundamentos de Seguridad en la Nube](./cloud/fundamentos.md)
- [AWS Security](./cloud/aws.md)
- [Azure Security](./cloud/azure.md)
- [Google Cloud Security](./cloud/gcp.md)
- [Contenedores y Kubernetes](./cloud/containers.md)
- [DevSecOps](./cloud/devsecops.md)

### Herramientas
- [Herramientas de Reconocimiento](./herramientas/reconocimiento.md)
  - Nmap
  - Masscan
  - Shodan
- [Herramientas de Explotación](./herramientas/explotacion.md)
  - Metasploit
  - Burp Suite
  - SQLMap
- [Herramientas de Análisis](./herramientas/analisis.md)
  - Wireshark
  - TCPDump
  - NetworkMiner
- [Distribuciones de Seguridad](./herramientas/distros.md)
  - Kali Linux
  - Parrot OS
  - BlackArch

### Frameworks y Estándares
- [ISO 27001/27002](./frameworks/iso27001.md)
- [NIST Cybersecurity Framework](./frameworks/nist.md)
- [CIS Controls](./frameworks/cis.md)
- [MITRE ATT&CK](./frameworks/mitre-attack.md)
- [GDPR y Privacidad](./frameworks/gdpr.md)
- [PCI DSS](./frameworks/pci-dss.md)

### Certificaciones
- [CompTIA Security+](./certificaciones/security-plus.md)
- [CEH (Certified Ethical Hacker)](./certificaciones/ceh.md)
- [OSCP (Offensive Security)](./certificaciones/oscp.md)
- [CISSP](./certificaciones/cissp.md)
- [CCNA Security](./certificaciones/ccna-security.md)
- [Recursos de Estudio](./certificaciones/recursos.md)

### Laboratorios y Práctica
- [Configuración de Lab Virtual](./labs/setup.md)
- [Máquinas Vulnerables](./labs/maquinas-vulnerables.md)
- [CTF y Wargames](./labs/ctf-wargames.md)
- [Escenarios Prácticos](./labs/escenarios.md)
- [Write-ups](./labs/writeups/)

### Recursos Adicionales
- [Blogs y Sitios Web](./recursos/blogs.md)
- [Libros Recomendados](./recursos/libros.md)
- [Podcasts de Seguridad](./recursos/podcasts.md)
- [Conferencias y Eventos](./recursos/conferencias.md)
- [Comunidades y Foros](./recursos/comunidades.md)
- [Glosario de Términos](./recursos/glosario.md)

---

## Cómo Usar Este Repositorio

1. **Navegación**: Utiliza el índice anterior para acceder directamente al tema de tu interés
2. **Búsqueda**: Usa la función de búsqueda de GitHub para encontrar términos específicos
3. **Contribución**: Lee la guía de contribución si deseas aportar contenido
4. **Actualizaciones**: Este repositorio se actualiza regularmente con nuevo contenido

## Estructura de los Apuntes

Cada documento sigue esta estructura:
- **Introducción**: Breve descripción del tema
- **Conceptos Clave**: Definiciones importantes
- **Explicación Detallada**: Desarrollo del contenido
- **Ejemplos Prácticos**: Casos de uso y demostraciones
- **Herramientas Relacionadas**: Software y utilidades relevantes
- **Referencias**: Enlaces y recursos adicionales

## Contribuciones

Las contribuciones son bienvenidas. Por favor:
1. Fork el repositorio
2. Crea una rama para tu característica (`git checkout -b feature/NuevoTema`)
3. Commit tus cambios (`git commit -m 'Añadir nuevo tema'`)
4. Push a la rama (`git push origin feature/NuevoTema`)
5. Abre un Pull Request

## Guía de Estilo

- Usar Markdown para todos los documentos
- Incluir ejemplos de código cuando sea relevante
- Añadir diagramas y capturas de pantalla para claridad
- Mantener un tono profesional pero accesible
- Citar fuentes y referencias

## Disclaimer

Este repositorio tiene fines educativos. El uso de las técnicas y herramientas descritas debe realizarse siempre de manera ética y legal, con autorización explícita en entornos controlados.

## Licencia

Este proyecto está bajo la Licencia MIT - ver el archivo [LICENSE](./LICENSE) para más detalles.

## Contacto

- GitHub: [@tu-usuario](https://github.com/tu-usuario)
- Email: tu-email@ejemplo.com

---

## 🌟 Estado del Proyecto

- [ ] Fundamentos - En progreso
- [ ] Seguridad de Redes - Por iniciar
- [ ] Criptografía - Por iniciar
- [ ] Seguridad Web - Por iniciar
- [ ] Cloud Security - Por iniciar
- [ ] Herramientas - Por iniciar
- [ ] Laboratorios - Por iniciar

---

**Última actualización**: [Fecha]

⭐ Si este repositorio te resulta útil, considera darle una estrella!
