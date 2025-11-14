#  Criterios de Aceptación

El sistema será aceptado si:
- Permite CRUD de productos correctamente.  
- Maneja pedidos y estados sin errores.  
- Genera reportes precisos.  
- Autenticación distingue clientes y administradores.  
- Interface responde en menos de 2 segundos.  
- Sistema estable al menos 95% del tiempo.  
- Datos protegidos mediante cifrado y control de acceso.  


#  Casos de Prueba

### Casos unitarios (simulados):

| Requerimiento | Entrada | Resultado esperado | Resultado obtenido |
|---------------|---------|-------------------|--------------------|
| Funcional | Usuario “maria123” | Acceso exitoso | Correcto |
| Funcional | Solicitud | Lista completa | Correcto |
| Funcional | Café x2 + Sándwich | Pedido registrado | Correcto |
| Funcional | Pedido #103 | Estado actualizado | Correcto |
| Funcional | Brownie | Producto agregado | Correcto |


### Casos de validación:

| Requerimiento | Entrada | Resultado esperado | Resultado obtenido |
|---------------|---------|-------------------|--------------------|
| no Funcional | 10 usuarios simultáneos | Fluido | Correcto |
| no Funcional | Varias operaciones | ≤ 2s | correcto|
| no Funcional | Jornada completa | 95% | correcto |
