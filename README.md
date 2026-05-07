# Ambiente-De_Desarrollo
index.js
const dayjs = require('dayjs');

// datos del envio
const peso = 10; // lb
const distancia = 120; // km

// costos base
const costoBase = 50;

// recargos
let recargoPeso = 0;
let recargoDistancia = 0;

// si el peso es mayor a 5 lb
if (peso > 5) {
    recargoPeso = (peso - 5) * 20;
}

// si la distancia es mayor a 50 km
if (distancia > 50) {
    recargoDistancia = (distancia - 50) * 10;
}

// costo total
const costoTotal = costoBase + recargoPeso + recargoDistancia;

// fecha de entrega
const diasProcesamiento = 2;
const diasTransporte = Math.ceil(distancia / 100);
const diasTotales = diasProcesamiento + diasTransporte;

const fechaEntrega = dayjs().add(diasTotales, 'day').format('YYYY-MM-DD');

// mostrar resultados
console.log("Costo base: L" + costoBase.toFixed(2));
console.log("Recargo por peso: L" + recargoPeso.toFixed(2));
console.log("Costo total: L" + costoTotal.toFixed(2));
console.log("Fecha estimada de entrega: " + fechaEntrega);

Package.json
{
  "name": "envio-logistica",
  "version": "1.0.0",
  "main": "index.js",
  "license": "ISC",
  "dependencies": {
    "dayjs": "^1.11.10"
  }
}
