# Traxion Albatros API

## 📌 Descripción  
La **Traxion Albatros API** es una **Process API** que actúa como núcleo del **almacenamiento farmacéutico de Traxion**.  
Centraliza y orquesta flujos clave, integrando múltiples sistemas para garantizar la **trazabilidad** y **eficiencia** de la cadena de suministro.  

Administra procesos que abarcan desde la **recepción de pedidos** hasta la **certificación final de entregas**, brindando una vista unificada de las operaciones logísticas.

---

## ⚙️ Operaciones

### 🔹 Orden de Creación  
`POST /orders`  
Permite la creación de nuevos pedidos de clientes, validando la información y orquestando la asignación inicial de inventario.

### 🔹 Consulta de Disponibilidad  
`GET /products/{productId}/availability`  
Consulta la disponibilidad en tiempo real de un producto específico en diferentes almacenes.  
Es vital para la **toma de decisiones del negocio**.

### 🔹 Asignación de Inventario  
`POST /inventory/assignment`  
Asigna formalmente inventario disponible a un pedido ya creado.  
Este paso **reserva los bienes** para su posterior preparación.

### 🔹 Salida de Almacén - Carta Porte  
`POST /shipments/{shipmentId}/billoflading`  
Genera la **Carta Porte** (Bill of Lading) para la salida de almacén, validando la preparación del pedido y notificando a los sistemas de transporte.

### 🔹 Certificación de Entrega  
`POST /deliveries/{deliveryId}/certification`  
Confirma la **entrega exitosa** de un pedido al cliente final.  
Actualiza sistemas de **CRM** y **facturación**.

---

## 🏢 Sistemas Integrados

Estos son los sistemas de negocio con los que la API se conecta:

- **PSC (Pharmaceutical Supply Chain):** Certificación de remisiones. Sistema de Registro (SOR) para información de pedidos.  
- **SAP:** ERP para finanzas, inventario y facturación.  
- **CRM:** Gestión de clientes y seguimiento de pedidos.  
- **WMS-BY:** Sistema especializado en gestión de almacenes.  
- **DB:** Base de datos interna para almacenamiento temporal y auditoría transaccional.  

---

## 🔗 Dependencias

APIs o servicios de MuleSoft consumidos por la `traxion-albatros-api`:

- **process-albatros-orchestrator-api:** API de orquestación para flujos complejos.  
- **system-crm-api:** Acceso a datos de clientes y pedidos en CRM.  
- **system-sap-api:** Interacción con SAP para inventario y facturación.  
- **system-wms-by-api:** Gestión de inventario físico en WMS.  

---

## 👥 Consumidores

Los principales consumidores de esta API son:

- **WMS-BY:** Notifica estados de preparación de pedidos.  
- **CRM:** Crea nuevos pedidos y consulta su estado en tiempo real.  
- **PSC:** Sincroniza información de entregas y certificaciones.  

---

## ⏱️ Procesos Programados

Actualmente no existen procesos programados.  
**NA: Not Applicable.**

---

## 📖 Notas

- Esta API sigue el modelo de **API-led Connectivity de MuleSoft**.  
- La documentación técnica y de endpoints se gestiona en el **Developer Portal**.  
