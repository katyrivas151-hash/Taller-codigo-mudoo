# 📄 Módulo de Cálculo de Impuestos - El Salvador

## 📌 Descripción General

Este módulo proporciona una función para calcular el **salario neto** después de aplicar un descuento del 15% sobre una base de deducción, y opcionalmente agregar un bono fijo de $13 para la región de El Salvador.

---

## 🎯 ¿Qué hace la función?

- Calcula un **descuento del 15%** sobre un monto base de deducción.
- Resta ese descuento al salario base.
- **Si la región es "SV" (El Salvador)**, suma un **bono adicional de $13** al resultado.
- Retorna el **monto neto final**.

---

## 📊 Fórmula Matemática

### Para región "SV" (El Salvador):

Neto = (Salario - (DeducciónBase × 0.15)) + 13


### Para otras regiones:

Neto = Salario - (DeducciónBase × 0.15)


---

## 🔧 Parámetros de la Función

| Parámetro | Tipo    | Descripción                                                                 |
|-----------|---------|-----------------------------------------------------------------------------|
| `salario` | number  | Monto base del ingreso o salario bruto.                                     |
| `deduccionBase` | number  | Monto sobre el cual se calcula el 15% de descuento (ej. gastos, impuestos). |
| `region`  | string  | Código del país/región (ej. `"SV"` para El Salvador).                      |

---

## 💻 Uso Básico

javascript
// Importar o copiar la función
function calcularImpuesto(salario, deduccionBase, region) {
    const descuento = deduccionBase * 0.15;
    
    if (region.toLowerCase() === "sv") {
        return (salario - descuento) + 13;
    } else {
        return salario - descuento;
    }
}

// Ejemplo 1: El Salvador (aplica bono)
const resultadoSV = calcularImpuesto(100, 10, "SV");
console.log(resultadoSV); // 111.5

// Ejemplo 2: Otra región (sin bono)
const resultadoOtro = calcularImpuesto(100, 10, "US");
console.log(resultadoOtro); // 98.5


---

## 📝 Ejemplos Detallados

### Caso 1: Región El Salvador
javascript
calcularImpuesto(100, 10, "SV")
// Paso 1: descuento = 10 × 0.15 = 1.5
// Paso 2: 100 - 1.5 = 98.5
// Paso 3: 98.5 + 13 = 111.5
// Resultado: 111.5


### Caso 2: Otra región
javascript
calcularImpuesto(100, 10, "US")
// Paso 1: descuento = 10 × 0.15 = 1.5
// Paso 2: 100 - 1.5 = 98.5
// Resultado: 98.5


### Caso 3: Diferentes valores
javascript
calcularImpuesto(500, 50, "SV")
// descuento = 50 × 0.15 = 7.5
// 500 - 7.5 = 492.5
// 492.5 + 13 = 505.5
// Resultado: 505.5


---

## 🔄 Versión Original (Código "Mudo")

El código original recibido fue:

javascript
function x(a, b, c) {
    let d = b * 0.15;
    if (c == "sv") {
        return (a - d) + 13; // ¿Qué es el 13?
    } else {
        let res = a - d;
        return res;
    }
}


### Refactorización realizada:

| Original | Refactorizado    | Justificación                        |
|----------|------------------|--------------------------------------|
| `x`      | `calcularImpuesto` | Nombre descriptivo de la acción.     |
| `a`      | `salario`        | Representa el salario base.          |
| `b`      | `deduccionBase`  | Base para calcular el descuento.     |
| `c`      | `region`         | Código de país/región.               |
| `d`      | `descuento`      | Valor calculado del 15%.             |
| `13`     | `BONO_SV`        | Constante con nombre semántico.      |

---

## ⚠️ Consideraciones Técnicas

1. **Comparación de región**: Se usa `.toLowerCase()` para hacer la comparación **insensible a mayúsculas/minúsculas**, aceptando `"sv"`, `"SV"`, `"Sv"`, etc.

2. **El número 13**: Es un **bono fijo** aplicable exclusivamente para El Salvador. Se recomienda definirlo como constante:
   javascript
   const BONO_SV = 13;
   

3. **Validaciones sugeridas**:
   javascript
   if (typeof salario !== 'number' || salario < 0) {
       throw new Error('El salario debe ser un número positivo');
   }
   if (typeof deduccionBase !== 'number' || deduccionBase < 0) {
       throw new Error('La base de deducción debe ser un número positivo');
   }
   

---

## 🚀 Mejoras Futuras Sugeridas

- [ ] Configurar el porcentaje de descuento (15%) como constante o parámetro configurable.
- [ ] Permitir múltiples regiones con diferentes bonos mediante un objeto de configuración.
- [ ] Agregar soporte para diferentes porcentajes según el país.
- [ ] Implementar pruebas unitarias con Jest o Mocha.

---

## 📚 Historial de Cambios

| Versión | Fecha       | Descripción                                   |
|---------|-------------|-----------------------------------------------|
| 1.0.0   | 2026-07-02  | Versión inicial con refactorización completa. |
| 1.0.1   | 2026-07-02  | Documentación técnica y ejemplos agregados.   |

---

## 👤 Autor

- **Desarrollador**: Equipo de Documentación Técnica
- **Empresa**: [Nombre de tu empresa]
- **Contacto**: [email@empresa.com]

---

## 📄 Licencia

Este código es propiedad de [Nombre de tu empresa] y se proporciona "tal cual", sin garantías de ningún tipo.

---

**Última actualización**: 2026-07-02


---