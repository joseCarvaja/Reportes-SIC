<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Análisis Avanzado de Contratistas</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        body { font-family: 'Inter', sans-serif; }
        table { table-layout: auto; width: 100%; }
        th, td { word-wrap: break-word; overflow-wrap: break-word; padding: 6px 4px; font-size: 0.80rem; }
        .chart-container { position: relative; margin: auto; height:40vh; width:80vw; max-width: 600px; margin-bottom:30px;}
        h2.section-title { font-size: 1.5em; font-weight: 600; color: #1e3a8a; margin-top: 2rem; margin-bottom: 1rem; border-bottom: 2px solid #3b82f6; padding-bottom: 0.5rem; }
        .toggle-button, .action-button { background-color: #3b82f6; color: white; padding: 4px 8px; border-radius: 4px; font-size: 0.8rem; cursor: pointer; margin-left: 5px;}
        .toggle-button:hover, .action-button:hover { background-color: #2563eb; }
        #tabla-multi-contratistas-body tr:hover, #tabla-resumen-dependencia-body tr:hover { background-color: #f0f9ff; cursor: pointer; }
        textarea { width: 100%; border: 1px solid #ccc; padding: 8px; box-sizing: border-box; font-family: monospace; font-size: 0.9em; }
    </style>
</head>
<body class="bg-gray-100 text-gray-800">
    <header class="bg-slate-800 text-white p-6 shadow-md">
        <h1 class="text-3xl md:text-4xl font-bold text-center">Análisis Avanzado de Reporte de Contratistas</h1>
    </header>

    <div class="container mx-auto p-4 md:p-6 max-w-full">
        <section class="mb-6 md:mb-8 bg-white p-5 rounded-lg shadow">
            <h2 class="text-xl font-semibold text-slate-700 mb-3">Cargar Datos del CSV</h2>
            <div class="mb-4">
                <label for="csvTextArea" class="block text-sm font-medium text-gray-700 mb-1">Pega aquí el contenido de tu archivo CSV:</label>
                <textarea id="csvTextArea" rows="10" class="shadow-sm focus:ring-indigo-500 focus:border-indigo-500 mt-1 block w-full sm:text-sm border-gray-300 rounded-md" placeholder="NUMERO CTO;ESTADO EN SECOP;NOMBRECONTRATISTA;... (pega todo el contenido de tu CSV aquí)"></textarea>
            </div>
            <button id="processPastedDataBtn" class="action-button bg-green-500 hover:bg-green-600 py-2 px-4">Procesar Datos Pegados</button>
            <p class="text-xs text-gray-500 mt-2">
                Asegúrate de que los datos usen punto y coma (;) como separador y tengan la estructura de columnas esperada.
                <strong>Importante: Revisa la consola del navegador (F12) para mensajes de diagnóstico.</strong>
            </p>
            <div id="message-box" class="mt-3 p-3 rounded-md text-sm hidden"></div>
            
            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-5 gap-4 md:gap-6 mt-6">
                <div class="bg-blue-50 p-5 rounded-lg shadow">
                    <h3 class="text-lg font-semibold text-blue-700 mb-2">Total Contratos Válidos</h3>
                    <p id="total-contratos-validos" class="text-3xl font-bold text-blue-600">[N]</p>
                </div>
                <div class="bg-green-50 p-5 rounded-lg shadow">
                    <h3 class="text-lg font-semibold text-green-700 mb-2">Monto Total (Válidos)</h3>
                    <p id="monto-total-general" class="text-3xl font-bold text-green-600">$[M]</p>
                </div>
                <div class="bg-indigo-50 p-5 rounded-lg shadow">
                    <h3 class="text-lg font-semibold text-indigo-700 mb-2">Contratistas Únicos (Doc. SECOP)</h3>
                    <p id="contratistas-unicos" class="text-3xl font-bold text-indigo-600">[N]</p>
                </div>
                <div class="bg-orange-50 p-5 rounded-lg shadow">
                    <h3 class="text-lg font-semibold text-orange-700 mb-2">Contratos "En Ejecución"</h3>
                    <p id="contratos-en-ejecucion" class="text-3xl font-bold text-orange-600">[N]</p>
                </div>
                <div class="bg-red-50 p-5 rounded-lg shadow">
                    <h3 class="text-lg font-semibold text-red-700 mb-2">Total Contratos Rechazados</h3>
                    <p id="total-contratos-rechazados" class="text-3xl font-bold text-red-600">[N]</p>
                </div>
            </div>
        </section>

        <section id="analysis-sections" class="hidden">
            <div class="bg-white p-5 rounded-lg shadow mb-8">
                <h2 class="section-title">Visualizaciones Gráficas (Basado en Contratos Válidos)</h2>
                <p class="text-sm text-gray-600 mb-4">Haz clic en las secciones de los gráficos para ver detalles más abajo.</p>
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
                    <div class="bg-white p-5 rounded-lg shadow">
                        <h3 class="text-xl font-semibold text-slate-700 mb-4 text-center">Top 5 Contratistas Frecuentes (por Doc. SECOP) por Valor Total</h3>
                        <div class="chart-container">
                            <canvas id="chartTopContratistas"></canvas>
                        </div>
                    </div>
                    <div class="bg-white p-5 rounded-lg shadow">
                        <h3 class="text-xl font-semibold text-slate-700 mb-4 text-center">Valor Contratado por Área/Delegatura (Cont. Frecuentes)</h3>
                         <div class="chart-container">
                            <canvas id="chartValorPorDependencia"></canvas>
                        </div>
                    </div>
                    <div class="bg-white p-5 rounded-lg shadow">
                        <h3 class="text-xl font-semibold text-slate-700 mb-4 text-center">Cantidad de Contratos por Área/Delegatura (Cont. Frecuentes)</h3>
                         <div class="chart-container">
                            <canvas id="chartCantidadPorDependencia"></canvas>
                        </div>
                    </div>
                </div>
            </div>
            <div class="bg-white p-5 rounded-lg shadow mb-8">
                <h2 class="section-title" id="titulo-resumen-dependencia">Resumen por Área/Delegatura (Contratistas Frecuentes con Contratos Válidos)</h2>
                <p class="text-sm text-gray-600 mb-3">Haz clic en una fila de Área/Delegatura para filtrar la tabla de "Contratistas con Múltiples Contratos" de abajo.</p>
                <div class="overflow-x-auto">
                    <table class="min-w-full divide-y divide-gray-200">
                        <thead class="bg-slate-600">
                            <tr>
                                <th class="px-4 py-3 text-left text-xs font-medium text-white uppercase tracking-wider">Área/Delegatura</th>
                                <th class="px-4 py-3 text-left text-xs font-medium text-white uppercase tracking-wider">Nº Contratistas Frecuentes en Área</th>
                                <th class="px-4 py-3 text-left text-xs font-medium text-white uppercase tracking-wider">Nº Contratos Válidos (de Frecuentes) en Área</th>
                                <th class="px-4 py-3 text-left text-xs font-medium text-white uppercase tracking-wider">Valor Total Válido (de Frecuentes) en Área</th>
                            </tr>
                        </thead>
                        <tbody id="tabla-resumen-dependencia-body" class="bg-white divide-y divide-gray-200"></tbody>
                    </table>
                </div>
            </div>
            <div class="bg-white p-5 rounded-lg shadow mb-8" id="seccion-multi-contratistas">
                 <div class="flex justify-between items-center mb-2">
                    <h2 class="section-title !mb-0 !border-b-0" id="titulo-multi-contratistas">Contratistas con Múltiples Contratos (por Doc. SECOP, Basado en Contratos Válidos)</h2>
                    <button id="toggle-tabla-multi-contratistas" class="toggle-button">Mostrar Detalles</button>
                </div>
                 <p class="text-sm text-gray-600 mb-3">Haz clic en una fila para ver el detalle de los contratos de ese contratista.</p>
                <div class="overflow-x-auto hidden" id="contenedor-tabla-multi-contratistas">
                    <table class="min-w-full divide-y divide-gray-200">
                        <thead class="bg-slate-600">
                            <tr>
                                <th class="px-4 py-3 text-left text-xs font-medium text-white uppercase tracking-wider">Documento# (SECOP)</th>
                                <th class="px-4 py-3 text-left text-xs font-medium text-white uppercase tracking-wider">Nombre Contratista (Asociado)</th>
                                <th class="px-4 py-3 text-left text-xs font-medium text-white uppercase tracking-wider">Cantidad de Contratos Válidos</th>
                                <th class="px-4 py-3 text-left text-xs font-medium text-white uppercase tracking-wider">Valor Total de sus Contratos Válidos</th>
                            </tr>
                        </thead>
                        <tbody id="tabla-multi-contratistas-body" class="bg-white divide-y divide-gray-200"></tbody>
                    </table>
                </div>
            </div>
        </section>

        <div id="drilldown-section" class="bg-white p-5 rounded-lg shadow mt-8 hidden">
             <div class="flex justify-between items-center mb-2">
                <h2 id="drilldown-title" class="section-title !mb-0 !border-b-0 text-sky-700">Detalle Filtrado</h2>
                <button id="toggle-tabla-drilldown" class="toggle-button bg-red-500 hover:bg-red-600">Cerrar Detalle</button>
            </div>
            <div class="overflow-x-auto" id="contenedor-tabla-drilldown">
                <table class="min-w-full divide-y divide-gray-200">
                    <thead class="bg-sky-700"> 
                         <tr>
                            <th title="Índice CSV: 0">Num. CTO</th><th title="Índice CSV: 1">Estado SECOP</th><th title="Índice CSV: 2">Nombre Contratista</th>
                            <th title="Índice CSV: 3">Doc.#</th><th title="Índice CSV: 4">Doc.# (SECOP)</th><th title="Índice CSV: 5">Cedido</th>
                            <th title="Índice CSV: 6">Área/Delegatura</th><th title="Índice CSV: 7">Honorarios</th><th title="Índice CSV: 8">Valor del Contrato</th>
                            <th title="Índice CSV: 9">Plazo (Días)</th><th title="Índice CSV: 10">Aprobado</th><th title="Índice CSV: 11">Fecha Aprobación</th>
                            <th title="Índice CSV: 12">Fecha Firma SECOP</th>
                        </tr>
                    </thead>
                    <tbody id="drilldown-table-body" class="bg-white divide-y divide-gray-200"></tbody>
                </table>
            </div>
        </div>
        
        <div class="bg-white p-5 rounded-lg shadow mt-8">
            <div class="flex justify-between items-center mb-2">
                <h2 class="section-title !mb-0 !border-b-0">Detalle de Contratos Válidos (No Rechazados/Anulados)</h2>
                <button id="toggle-tabla-validos" class="toggle-button">Mostrar Detalles</button>
            </div>
            <div class="overflow-x-auto hidden" id="contenedor-tabla-validos"> 
                <table class="min-w-full divide-y divide-gray-200" id="tabla-todos-contratos">
                     <thead class="bg-slate-700"> 
                         <tr>
                            <th title="Índice CSV: 0">Num. CTO</th><th title="Índice CSV: 1">Estado SECOP</th><th title="Índice CSV: 2">Nombre Contratista</th>
                            <th title="Índice CSV: 3">Doc.#</th><th title="Índice CSV: 4">Doc.# (SECOP)</th><th title="Índice CSV: 5">Cedido</th>
                            <th title="Índice CSV: 6">Área/Delegatura</th><th title="Índice CSV: 7">Honorarios</th><th title="Índice CSV: 8">Valor del Contrato</th>
                            <th title="Índice CSV: 9">Plazo (Días)</th><th title="Índice CSV: 10">Aprobado</th><th title="Índice CSV: 11">Fecha Aprobación</th>
                            <th title="Índice CSV: 12">Fecha Firma SECOP</th>
                        </tr>
                    </thead>
                    <tbody id="tabla-todos-contratos-body" class="bg-white divide-y divide-gray-200"></tbody>
                </table>
            </div>
        </div>

        <div class="bg-white p-5 rounded-lg shadow mt-8" id="seccion-contratos-rechazados" style="display: none;">
            <div class="flex justify-between items-center mb-2">
                <h2 class="section-title !mb-0 !border-b-0 text-red-700">Detalle de Contratos Rechazados/Anulados</h2>
                <button id="toggle-tabla-rechazados" class="toggle-button">Mostrar Detalles</button>
            </div>
            <div class="overflow-x-auto hidden" id="contenedor-tabla-rechazados"> 
                <table class="min-w-full divide-y divide-gray-200">
                    <thead class="bg-red-600"> 
                         <tr>
                            <th title="Índice CSV: 0">Num. CTO</th><th title="Índice CSV: 1">Estado SECOP</th><th title="Índice CSV: 2">Nombre Contratista</th>
                            <th title="Índice CSV: 3">Doc.#</th><th title="Índice CSV: 4">Doc.# (SECOP)</th><th title="Índice CSV: 5">Cedido</th>
                            <th title="Índice CSV: 6">Área/Delegatura</th><th title="Índice CSV: 7">Honorarios</th><th title="Índice CSV: 8">Valor del Contrato</th>
                            <th title="Índice CSV: 9">Plazo (Días)</th><th title="Índice CSV: 10">Aprobado</th><th title="Índice CSV: 11">Fecha Aprobación</th>
                            <th title="Índice CSV: 12">Fecha Firma SECOP</th>
                        </tr>
                    </thead>
                    <tbody id="tabla-rechazados-body" class="bg-white divide-y divide-gray-200"></tbody>
                </table>
            </div>
        </div>
    </div>

    <footer class="bg-slate-800 text-white text-center p-6 mt-8">
        <p>&copy; <span id="current-year"></span> Tu Entidad/Empresa. Todos los derechos reservados.</p>
        <p class="text-sm">Generado el: <span id="fecha-generacion">[Fecha Actual]</span></p>
    </footer>

    <script>
    document.addEventListener('DOMContentLoaded', function() {
        const csvTextArea = document.getElementById('csvTextArea');
        const processPastedDataBtn = document.getElementById('processPastedDataBtn');
        
        // console.log("DEVLOG: csvTextArea element:", csvTextArea);
        // console.log("DEVLOG: processPastedDataBtn element:", processPastedDataBtn);

        const messageBox = document.getElementById('message-box');
        const analysisSectionsEl = document.getElementById('analysis-sections');
        const tablaTodosContratosBody = document.getElementById('tabla-todos-contratos-body');
        const contenedorTablaValidos = document.getElementById('contenedor-tabla-validos');
        const toggleTablaValidos = document.getElementById('toggle-tabla-validos');
        const seccionContratosRechazados = document.getElementById('seccion-contratos-rechazados');
        const tablaRechazadosBody = document.getElementById('tabla-rechazados-body');
        const contenedorTablaRechazados = document.getElementById('contenedor-tabla-rechazados');
        const toggleTablaRechazados = document.getElementById('toggle-tabla-rechazados');
        const drilldownSectionEl = document.getElementById('drilldown-section');
        const drilldownTitleEl = document.getElementById('drilldown-title');
        const drilldownTableBodyEl = document.getElementById('drilldown-table-body');
        const toggleTablaDrilldown = document.getElementById('toggle-tabla-drilldown'); 
        const contenedorTablaDrilldown = document.getElementById('contenedor-tabla-drilldown');
        const totalContratosValidosEl = document.getElementById('total-contratos-validos');
        const montoTotalGeneralEl = document.getElementById('monto-total-general');
        const contratistasUnicosEl = document.getElementById('contratistas-unicos');
        const contratosEnEjecucionEl = document.getElementById('contratos-en-ejecucion');
        const totalContratosRechazadosEl = document.getElementById('total-contratos-rechazados');
        const tablaMultiContratistasBody = document.getElementById('tabla-multi-contratistas-body');
        const contenedorTablaMultiContratistas = document.getElementById('contenedor-tabla-multi-contratistas');
        const toggleTablaMultiContratistas = document.getElementById('toggle-tabla-multi-contratistas');
        const tituloMultiContratistasEl = document.getElementById('titulo-multi-contratistas'); 
        const tablaResumenDependenciaBody = document.getElementById('tabla-resumen-dependencia-body');
        
        let chartTopContratistas = null;
        let chartValorPorDependencia = null;
        let chartCantidadPorDependencia = null;
        
        let _contratosValidosGlobal = []; 
        let _multiContratistasArrayGlobalData = []; 
        let _dependenciasArrayGlobalData = [];   
        let _docSecopContratistasFrecuentesGlobal = new Set();

        const COL_IDX = {
            NUMERO_CTO: 0, ESTADO_SECOP: 1, NOMBRE_CONTRATISTA: 2, DOCUMENTO_NUM: 3,
            DOCUMENTO_SECOP: 4, CEDIDO: 5, AREA_DELEGATURA: 6, HONORARIOS: 7,
            VALOR_CONTRATO: 8, PLAZO_DIAS: 9, APROBADO: 10, FECHA_APROBACION: 11,
            FECHA_FIRMA_SECOP: 12
        };
        const NUM_COLUMNAS_ESPERADAS = Object.keys(COL_IDX).length;

        const embeddedCSVData = `NUMERO CTO;ESTADO EN SECOP;NOMBRECONTRATISTA;DOCUMENTO#;DOCUMENTO# (SECOP);CEDIDO;AREA/DELEGATURA;HONORARIOS;VALORDELCONTRATO;PLAZO(DIAS);APROBADO;FECHA DE APROBACION;FECHA FIRMA SECOP
28;En ejecución;JHONNATAN ALFONSO CARDENAS GONZALEZ;1020770762;1020770762;FALSO;SEGE;9486000;111618600;100;APROBADO;;01/08/2025
10;En ejecución;SANDRA MILENA REYES CARVAJAL;1003661549;1003661549;FALSO;CONSUMIDOR;4355541;51250199;100;APROBADO;;01/08/2025
11;Terminado;LEYLA MARIA CAMACHO CHAHIN;52709475;52709475;FALSO;CONSUMIDOR;7865694;92553000;100;APROBADO;;01/08/2025
70;Firmado;JUAN CARLOS RODRIGUEZ SUAREZ;79998888;79998888;FALSO;JURIDICA;12000000;120000000;120;APROBADO;2024-01-01;2025-01-01
99;Rechazada;CONTRATISTA RECHAZADO SA;111222333;111222333;FALSO;SISTEMAS;500000;5000000;30;RECHAZADO;2024-03-01;
12;En ejecución;YURY SOLANYI PAEZ BOGOTA;52204612;52204612;FALSO;CONSUMIDOR;7462000;87802867;100;APROBADO;;01/08/2025
15;Rechazado (Anulado);CONTRATISTA ANULADO EJEMPLO;123123123;123123123;FALSO;JURIDICA;1000000;10000000;50;ANULADO;;01/09/2025
29;En ejecución;JHONNATAN ALFONSO CARDENAS GONZALEZ;1020770762;1020770762;FALSO;SEGE;10000000;120000000;150;APROBADO;;01/10/2025`;

        // --- (Resto de funciones JavaScript como en la respuesta anterior) ---
        function showMessage(message, type = 'info') { /* ... */ }
        function formatCurrency(value) { /* ... */ }
        function parseNumberWithPotentialSeparators(valueStr, columnNameForLog = "Value") { /* ... */ }
        function parseCSV(text) { /* ... */ }
        function populateContractsTable(tbodyElement, contractsArray) { /* ... */ } 
        function displayDrilldownTable(filteredContracts, title) { /* ... */ }
        function procesarDatos(parsedData) { /* ... */ }
        function actualizarResumenesGlobales(contratosValidos, contratosRechaz, montoTotalValidos, numContratistasUnicosValidos, numEnEjecucionValidos) { /* ... */ }
        function populateMultiContractorTable(dataArray) { /* ... */ }
        function filterAndDisplayMultiContractorsByArea(areaNombre) { /* ... */ }
        function procesarAgregadosYGraficos(contratosValidos) { /* ... */ }
        function generarGraficoTopContratistas(dataParaElGrafico) { /* ... */ }
        function generarGraficoDependencias(dataParaLosGraficos) { /* ... */ }
        
        function showMessage(message, type = 'info') {
            messageBox.textContent = message;
            messageBox.className = 'mt-3 p-3 rounded-md text-sm';
            if (type === 'error') messageBox.classList.add('bg-red-100', 'text-red-700');
            else if (type === 'success') messageBox.classList.add('bg-green-100', 'text-green-700');
            else messageBox.classList.add('bg-blue-100', 'text-blue-700');
        }

        function formatCurrency(value) {
            const num = parseFloat(value);
            if (isNaN(num)) return '$0';
            return new Intl.NumberFormat('es-CO', { style: 'currency', currency: 'COP', minimumFractionDigits: 0, maximumFractionDigits: 0 }).format(num);
        }
        
        function parseNumberWithPotentialSeparators(valueStr, columnNameForLog = "Value") {
            if (typeof valueStr === 'number') return valueStr;
            if (typeof valueStr !== 'string') valueStr = String(valueStr);
            let originalInputForLog = valueStr;
            valueStr = valueStr.trim();
            if (valueStr === "") { return NaN; }
            let cleanedValue = valueStr.replace(/[$\sA-Za-zCOPcop]/gi, ''); 
            if (cleanedValue.trim() === "") { return NaN; }
            let finalStringToParse = cleanedValue;
            const hasComma = cleanedValue.includes(',');
            const hasDot = cleanedValue.includes('.');
            if (hasComma && /,\d{1,2}$/.test(cleanedValue)) { 
                finalStringToParse = cleanedValue.replace(/\./g, ''); 
                finalStringToParse = finalStringToParse.replace(/,/g, '.');  
            } else if (hasDot && !hasComma) { 
                const parts = cleanedValue.split('.');
                if (parts.length > 1) {
                    const lastPart = parts[parts.length - 1];
                    if (parts.length > 2 || (lastPart.length !== 1 && lastPart.length !== 2 && lastPart.length !== 0)) {
                        finalStringToParse = cleanedValue.replace(/\./g, '');
                    }
                }
            } else if (hasComma && !hasDot) { 
                if ((cleanedValue.match(/,/g) || []).length > 1) {
                    finalStringToParse = cleanedValue.replace(/,/g, ''); 
                } else { 
                    finalStringToParse = cleanedValue.replace(/,/g, '.');
                }
            } else if (hasComma && hasDot) { 
                if (cleanedValue.lastIndexOf(',') > cleanedValue.lastIndexOf('.')) {
                    finalStringToParse = cleanedValue.replace(/\./g, ''); 
                    finalStringToParse = finalStringToParse.replace(/,/g, '.');  
                } else { 
                    finalStringToParse = cleanedValue.replace(/,/g, ''); 
                }
            }
            const num = parseFloat(finalStringToParse);
            if (originalInputForLog !== String(num) || isNaN(num) || originalInputForLog.match(/[A-Za-z$]/gi) ) {
                 console.log(`parseNumber (${columnNameForLog}): Original='${originalInputForLog}', LimpioSímbolos='${valueStr.replace(/[$\sA-Za-zCOPcop]/gi, '')}', FinalParaParseFloat='${finalStringToParse}', ParsedAs=${num}`);
            }
            if (isNaN(num) && finalStringToParse !== "") { 
                console.error(`parseNumber (${columnNameForLog}): FALLÓ PARSEO! Original='${originalInputForLog}', ProcesadoA='${finalStringToParse}', resultó en NaN.`);
            }
            return num;
        }

        function parseCSV(text) {
            if (!text || text.trim() === '') { console.warn("CSV text is empty."); return []; }
            const lines = text.split(/\r\n|\n/); 
            const nonEmptyLines = lines.filter(line => line.trim() !== ''); 
            if (nonEmptyLines.length === 0) { console.warn("CSV no tiene líneas con contenido."); return []; }
            let delimiter = ';'; 
            const firstLineToInspect = nonEmptyLines[0]; 
            const commaCount = (firstLineToInspect.match(/,/g) || []).length;
            const semicolonCount = (firstLineToInspect.match(/;/g) || []).length;
            if (commaCount > semicolonCount && semicolonCount === 0) { delimiter = ','; } 
            else if (semicolonCount > 0) { delimiter = ';'; } 
            else { delimiter = ','; }
            // console.log("Using delimiter:", `"${delimiter}"`);
            const rows = [];
            nonEmptyLines.forEach((line, lineIdx) => {
                const row = [];
                let currentField = '';
                let inQuotes = false;
                for (let i = 0; i < line.length; i++) {
                    const char = line[i];
                    if (char === '"') {
                        if (inQuotes && i + 1 < line.length && line[i+1] === '"') { currentField += '"'; i++; } 
                        else { inQuotes = !inQuotes; }
                    } else if (char === delimiter && !inQuotes) {
                        row.push(currentField.trim()); currentField = '';
                    } else { currentField += char; }
                }
                row.push(currentField.trim());
                if (lineIdx === 0 || (lineIdx > 0 && lineIdx <= 1) ) { 
                    // console.log(`Fila ${lineIdx === 0 ? 'Encabezado' : 'Datos ' + lineIdx} procesada por parseCSV:`, JSON.stringify(row));
                }
                rows.push(row);
            });
            return rows;
        }
        
        function populateContractsTable(tbodyElement, contractsArray) {
            tbodyElement.innerHTML = ''; 
            if (!contractsArray || contractsArray.length === 0) {
                tbodyElement.innerHTML = `<tr><td colspan="${NUM_COLUMNAS_ESPERADAS}" class="text-center p-4">No hay contratos para mostrar con este filtro.</td></tr>`;
                return false; 
            }
            contractsArray.forEach(contrato => {
                const filaEl = tbodyElement.insertRow();
                filaEl.insertCell().textContent = contrato.numeroCto;
                filaEl.insertCell().textContent = contrato.estadoSecop;
                filaEl.insertCell().textContent = contrato.nombreContratista;
                filaEl.insertCell().textContent = contrato.documentoNum;
                filaEl.insertCell().textContent = contrato.documentoSecop;
                filaEl.insertCell().textContent = contrato.cedido;
                filaEl.insertCell().textContent = contrato.dependencia;
                filaEl.insertCell().textContent = formatCurrency(contrato.honorarios);
                filaEl.cells[7].classList.add('text-right');
                filaEl.insertCell().textContent = formatCurrency(contrato.valorContrato);
                filaEl.cells[8].classList.add('text-right');
                filaEl.insertCell().textContent = contrato.plazoDias;
                filaEl.insertCell().textContent = contrato.aprobado;
                filaEl.insertCell().textContent = contrato.fechaAprobacion;
                filaEl.insertCell().textContent = contrato.fechaFirmaSecop;
                const estadoCell = filaEl.cells[1]; 
                estadoCell.classList.remove('text-red-700', 'text-orange-600', 'text-green-600', 'font-bold', 'font-semibold');
                if (contrato.estadoSecop.includes('rechazad') || contrato.estadoSecop.includes('anulad')) {
                     estadoCell.classList.add('text-red-700', 'font-bold');
                } else if (contrato.estadoSecop.includes('ejecución')) {
                    estadoCell.classList.add('text-orange-600', 'font-semibold');
                } else if (contrato.estadoSecop.includes('terminado') || contrato.estadoSecop.includes('liquidado') || contrato.estadoSecop.includes('firmado')) { 
                     estadoCell.classList.add('text-green-600', 'font-semibold');
                }
            });
            return true; 
        }
        
        function displayDrilldownTable(filteredContracts, title) {
            drilldownTitleEl.textContent = title;
            populateContractsTable(drilldownTableBodyEl, filteredContracts); 
            drilldownSectionEl.classList.remove('hidden');
            contenedorTablaDrilldown.classList.remove('hidden'); 
            toggleTablaDrilldown.textContent = 'Cerrar Detalle';
            drilldownSectionEl.scrollIntoView({ behavior: 'smooth', block: 'start' });
        }

        function procesarDatos(parsedData) {
            console.log("== INICIO NUEVO PROCESAMIENTO DE DATOS CSV ==");
            _contratosValidosGlobal = []; 
            _multiContratistasArrayGlobalData = [];
            _dependenciasArrayGlobalData = [];
            _docSecopContratistasFrecuentesGlobal = new Set();

            if (!parsedData || parsedData.length < 2) { 
                showMessage('El texto CSV está vacío o solo tiene encabezado.', 'error');
                actualizarResumenesGlobales([],[],0,0,0);
                analysisSectionsEl.classList.add('hidden');
                return;
            }
            const headerRowCSV = parsedData[0];
            const dataRows = parsedData.slice(1);

            const contratosActivosYTerminados = [];
            const contratosRechazados = [];
            let montoTotalGeneralValidos = 0;
            let contratosEnEjecucionCountValidos = 0;
            const docSecopContratistasSetValidos = new Set();

            dataRows.forEach((row, index) => {
                if (row.length < NUM_COLUMNAS_ESPERADAS) { return; }
                const estadoSecopOriginal = String(row[COL_IDX.ESTADO_SECOP] || '').trim().toLowerCase();
                const contrato = {
                    numeroCto: String(row[COL_IDX.NUMERO_CTO] || 'N/A').trim(),
                    estadoSecop: estadoSecopOriginal,
                    nombreContratista: String(row[COL_IDX.NOMBRE_CONTRATISTA] || 'Desconocido').trim(),
                    documentoNum: String(row[COL_IDX.DOCUMENTO_NUM] || 'N/A').trim(),
                    documentoSecop: String(row[COL_IDX.DOCUMENTO_SECOP] || 'Desconocido_SECOP').trim(),
                    cedido: String(row[COL_IDX.CEDIDO] || 'N/A').trim(),
                    dependencia: String(row[COL_IDX.AREA_DELEGATURA] || 'Desconocida').trim(),
                    honorarios: parseNumberWithPotentialSeparators(String(row[COL_IDX.HONORARIOS] || '0'), `Fila ${index+1} HONORARIOS`),
                    valorContrato: parseNumberWithPotentialSeparators(String(row[COL_IDX.VALOR_CONTRATO] || '0'), `Fila ${index+1} VALOR_CONTRATO`),
                    plazoDias: String(row[COL_IDX.PLAZO_DIAS] || 'N/A').trim(),
                    aprobado: String(row[COL_IDX.APROBADO] || 'N/A').trim().toLowerCase(),
                    fechaAprobacion: String(row[COL_IDX.FECHA_APROBACION] || 'N/A').trim(),
                    fechaFirmaSecop: String(row[COL_IDX.FECHA_FIRMA_SECOP] || 'N/A').trim(),
                };
                if (contrato.estadoSecop.includes('rechazad') || contrato.estadoSecop.includes('anulad')) {
                    contratosRechazados.push(contrato);
                } else {
                    contratosActivosYTerminados.push(contrato);
                    if (!isNaN(contrato.valorContrato)) montoTotalGeneralValidos += contrato.valorContrato;
                    if(contrato.documentoSecop !== 'Desconocido_SECOP' && contrato.documentoSecop !== '') {
                        docSecopContratistasSetValidos.add(contrato.documentoSecop);
                    }
                    if (contrato.estadoSecop.includes('ejecución')) contratosEnEjecucionCountValidos++;
                }
            });
            
            _contratosValidosGlobal = [...contratosActivosYTerminados]; 

            if (!populateContractsTable(tablaTodosContratosBody, _contratosValidosGlobal)) {
                 contenedorTablaValidos.classList.add('hidden');
                 toggleTablaValidos.textContent = 'Mostrar Detalles (Válidos)';
            } else {
                 // No cambiar estado de visibilidad aquí, se maneja por el botón.
            }
            if (populateContractsTable(tablaRechazadosBody, contratosRechazados)) {
                seccionContratosRechazados.style.display = 'block';
            } else {
                seccionContratosRechazados.style.display = 'none';
            }
            
            actualizarResumenesGlobales(
                _contratosValidosGlobal, contratosRechazados, 
                montoTotalGeneralValidos, docSecopContratistasSetValidos.size, contratosEnEjecucionCountValidos
            );
            
            if (_contratosValidosGlobal.length > 0) {
                procesarAgregadosYGraficos(_contratosValidosGlobal);
                analysisSectionsEl.classList.remove('hidden');
            } else { 
                analysisSectionsEl.classList.add('hidden'); 
                tablaMultiContratistasBody.innerHTML = `<tr><td colspan="4" class="text-center p-4">No hay datos válidos para este análisis.</td></tr>`;
                tablaResumenDependenciaBody.innerHTML = `<tr><td colspan="4" class="text-center p-4">No hay datos válidos para este análisis.</td></tr>`;
                if (chartTopContratistas) { chartTopContratistas.destroy(); chartTopContratistas = null; document.getElementById('chartTopContratistas').parentElement.style.display = 'none';}
                if (chartValorPorDependencia) { chartValorPorDependencia.destroy(); chartValorPorDependencia = null; document.getElementById('chartValorPorDependencia').parentElement.style.display = 'none';}
                if (chartCantidadPorDependencia) { chartCantidadPorDependencia.destroy(); chartCantidadPorDependencia = null; document.getElementById('chartCantidadPorDependencia').parentElement.style.display = 'none';}
            }
            showMessage(`Procesamiento completo. Válidos: ${_contratosValidosGlobal.length}, Rechazados: ${contratosRechazados.length}.`, 'success');
            console.log("== FIN PROCESAMIENTO DE DATOS CSV ==");
        }
        
        function actualizarResumenesGlobales(contratosValidos, contratosRechaz, montoTotalValidos, numContratistasUnicosValidos, numEnEjecucionValidos) {
            console.log("DEVLOG: actualizarResumenesGlobales - Input Data:", {
                contratosValidosLength: contratosValidos ? contratosValidos.length : 0,
                contratosRechazLength: contratosRechaz ? contratosRechaz.length : 0,
                montoTotalValidos: montoTotalValidos,
                numContratistasUnicosValidos: numContratistasUnicosValidos,
                numEnEjecucionValidos: numEnEjecucionValidos
            });
            totalContratosValidosEl.textContent = (contratosValidos ? contratosValidos.length : 0).toString();
            totalContratosRechazadosEl.textContent = (contratosRechaz ? contratosRechaz.length : 0).toString();
            montoTotalGeneralEl.textContent = formatCurrency(montoTotalValidos);
            contratistasUnicosEl.textContent = numContratistasUnicosValidos.toString();
            contratosEnEjecucionEl.textContent = numEnEjecucionValidos.toString();
        }

        function populateMultiContractorTable(dataArray) {
            const tituloOriginal = "Contratistas con Múltiples Contratos (por Doc. SECOP, Basado en Contratos Válidos)";
             let tituloActualHTML = tituloMultiContratistasEl.dataset.isFiltered === "true" ? 
                                 tituloMultiContratistasEl.innerHTML.split(" <button")[0] : 
                                 tituloOriginal;
            if (tituloMultiContratistasEl.dataset.isFiltered === "true") {
                 tituloActualHTML += ` <button id="reset-multi-contractor-filter-btn" class="action-button bg-amber-500 hover:bg-amber-600 text-xs !ml-2">Mostrar Todos</button>`;
            }
            tituloMultiContratistasEl.innerHTML = tituloActualHTML;
            const resetButton = document.getElementById('reset-multi-contractor-filter-btn');
            if (resetButton) {
                const newButton = resetButton.cloneNode(true);
                resetButton.parentNode.replaceChild(newButton, resetButton);
                newButton.addEventListener('click', () => {
                    tituloMultiContratistasEl.dataset.isFiltered = "false";
                    populateMultiContractorTable(_multiContratistasArrayGlobalData); 
                });
            }
            tablaMultiContratistasBody.innerHTML = '';
            if (dataArray.length > 0) {
                dataArray.forEach(data => {
                     const row = tablaMultiContratistasBody.insertRow();
                     row.setAttribute('data-doc-secop', data.documentoSecop); 
                     row.setAttribute('data-nombre-display', data.nombreDisplay); 
                     row.style.cursor = 'pointer';
                    row.insertCell().textContent = data.documentoSecop; 
                    row.insertCell().textContent = data.nombreDisplay;   
                    row.insertCell().textContent = data.count;
                    row.insertCell().textContent = formatCurrency(data.totalValue);
                });
            } else { 
                tablaMultiContratistasBody.innerHTML = `<tr><td colspan="4" class="text-center p-4">No hay contratistas para los criterios actuales.</td></tr>`;
            }
        }
        function filterAndDisplayMultiContractorsByArea(areaNombre) {
            const filteredMultiContractors = _multiContratistasArrayGlobalData.filter(contractorData => {
                return _contratosValidosGlobal.some(c => 
                    c.documentoSecop === contractorData.documentoSecop && 
                    c.dependencia === areaNombre
                );
            });
            tituloMultiContratistasEl.dataset.isFiltered = "true";
            // El título se actualiza completamente dentro de populateMultiContractorTable
            populateMultiContractorTable(filteredMultiContractors); 
            // Asegurar que la tabla sea visible después de filtrar
            contenedorTablaMultiContratistas.classList.remove('hidden');
            toggleTablaMultiContratistas.textContent = 'Ocultar Detalles';
            seccionMultiContratistas.scrollIntoView({ behavior: 'smooth', block: 'start' });
        }
        function procesarAgregadosYGraficos(contratosValidos) {
            const contratistasData = {}; 
            contratosValidos.forEach(c => {
                if (c.documentoSecop === 'Desconocido_SECOP' || c.documentoSecop === '') return;
                if (!contratistasData[c.documentoSecop]) {
                    contratistasData[c.documentoSecop] = { nombreDisplay: c.nombreContratista, count: 0, totalValue: 0, dependencias: new Set() };
                }
                contratistasData[c.documentoSecop].count++;
                if(!isNaN(c.valorContrato)){ contratistasData[c.documentoSecop].totalValue += c.valorContrato; } 
                if(c.dependencia !== 'Desconocida' && c.dependencia !== '') contratistasData[c.documentoSecop].dependencias.add(c.dependencia);
            });
            _multiContratistasArrayGlobalData = Object.entries(contratistasData)
                .filter(([, data]) => data.count > 1)
                .map(([docSecop, data]) => ({ documentoSecop: docSecop, ...data }))
                .sort((a, b) => b.totalValue - a.totalValue); 
            if (tituloMultiContratistasEl) tituloMultiContratistasEl.dataset.isFiltered = "false";
            populateMultiContractorTable(_multiContratistasArrayGlobalData);
            _docSecopContratistasFrecuentesGlobal = new Set(_multiContratistasArrayGlobalData.map(mc => mc.documentoSecop));
            const resumenDependenciasData = {};
            contratosValidos.forEach(c => {
                if (_docSecopContratistasFrecuentesGlobal.has(c.documentoSecop) && c.dependencia !== 'Desconocida' && c.dependencia !== '') {
                    if (!resumenDependenciasData[c.dependencia]) { resumenDependenciasData[c.dependencia] = { contratistasUnicos: new Set(), countContratos: 0, totalValue: 0 };}
                    resumenDependenciasData[c.dependencia].contratistasUnicos.add(c.documentoSecop); 
                    resumenDependenciasData[c.dependencia].countContratos++;
                    if(!isNaN(c.valorContrato)) resumenDependenciasData[c.dependencia].totalValue += c.valorContrato;
                }
            });
            _dependenciasArrayGlobalData = Object.entries(resumenDependenciasData)
                .map(([nombre, data]) => ({ nombre, ...data }))
                .sort((a,b) => b.totalValue - a.totalValue);
            tablaResumenDependenciaBody.innerHTML = '';
            if (_dependenciasArrayGlobalData.length > 0) {
                _dependenciasArrayGlobalData.forEach(data => { 
                    const row = tablaResumenDependenciaBody.insertRow();
                    row.setAttribute('data-area-nombre', data.nombre); 
                    row.style.cursor = 'pointer';
                    row.insertCell().textContent = data.nombre;
                    row.insertCell().textContent = data.contratistasUnicos.size;
                    row.insertCell().textContent = data.countContratos;
                    row.insertCell().textContent = formatCurrency(data.totalValue);
                 });
            } else { tablaResumenDependenciaBody.innerHTML = `<tr><td colspan="4" class="text-center p-4">No hay datos de áreas/delegaturas para contratistas frecuentes.</td></tr>`; }
            generarGraficoTopContratistas(_multiContratistasArrayGlobalData.slice(0, 5));
            generarGraficoDependencias(_dependenciasArrayGlobalData); 
        }
        function generarGraficoTopContratistas(dataParaElGrafico) { /* ... (como antes) ... */ }
        function generarGraficoDependencias(dataParaLosGraficos) { /* ... (como antes) ... */ }
        function generarGraficoTopContratistas(dataParaElGrafico) {
            const canvasEl = document.getElementById('chartTopContratistas');
            if (!canvasEl) return;
            const ctx = canvasEl.getContext('2d');
            if (chartTopContratistas) chartTopContratistas.destroy();
            if (!dataParaElGrafico || dataParaElGrafico.length === 0) { canvasEl.parentElement.style.display = 'none'; return; }
            canvasEl.parentElement.style.display = 'block';
            chartTopContratistas = new Chart(ctx, {
                type: 'bar',
                data: {
                    labels: dataParaElGrafico.map(d => `${d.nombreDisplay.substring(0,15)}...(${d.documentoSecop.substring(0,6)})`),
                    datasets: [{ label: 'Valor Total Contratado', data: dataParaElGrafico.map(d => d.totalValue), backgroundColor: 'rgba(54, 162, 235, 0.7)'}]
                },
                options: { 
                    responsive: true, maintainAspectRatio: false, indexAxis: 'y', 
                    scales: { x: { beginAtZero: true, ticks: { callback: value => formatCurrency(value) } }, y: { ticks: { autoSkip: false } } }, 
                    plugins: { tooltip: { callbacks: { label: context => `${context.dataset.label}: ${formatCurrency(context.raw)}` } } },
                    onClick: (event, elements) => {
                        if (elements.length > 0) {
                            const index = elements[0].index;
                            const clickedData = dataParaElGrafico[index]; 
                            if (clickedData && clickedData.documentoSecop) {
                                const filtered = _contratosValidosGlobal.filter(c => c.documentoSecop === clickedData.documentoSecop);
                                displayDrilldownTable(filtered, `Contratos para Doc.SECOP: ${clickedData.documentoSecop} (${clickedData.nombreDisplay})`);
                            }
                        }
                    }
                }
            });
        }
        function generarGraficoDependencias(dataParaLosGraficos) {
            const canvasValorEl = document.getElementById('chartValorPorDependencia');
            const canvasCantidadEl = document.getElementById('chartCantidadPorDependencia');
            if(!canvasValorEl || !canvasCantidadEl) return;
            const ctxValor = canvasValorEl.getContext('2d');
            const ctxCantidad = canvasCantidadEl.getContext('2d');
            if (chartValorPorDependencia) chartValorPorDependencia.destroy();
            if (chartCantidadPorDependencia) chartCantidadPorDependencia.destroy();
            if (!dataParaLosGraficos || dataParaLosGraficos.length === 0) { canvasValorEl.parentElement.style.display = 'none'; canvasCantidadEl.parentElement.style.display = 'none'; return;}
            canvasValorEl.parentElement.style.display = 'block';
            canvasCantidadEl.parentElement.style.display = 'block';
            const topDataParaGraficos = dataParaLosGraficos.slice(0, 7); 
            const labels = topDataParaGraficos.map(d => d.nombre);
            const backgroundColors = ['rgba(255, 99, 132, 0.7)', 'rgba(54, 162, 235, 0.7)', 'rgba(255, 206, 86, 0.7)', 'rgba(75, 192, 192, 0.7)', 'rgba(153, 102, 255, 0.7)', 'rgba(255, 159, 64, 0.7)', 'rgba(199, 199, 199, 0.7)'];
            const borderColors = backgroundColors.map(color => color.replace('0.7', '1'));
            chartValorPorDependencia = new Chart(ctxValor, { 
                type: 'pie', 
                data: { labels: labels, datasets: [{ label: 'Valor Total Contratado', data: topDataParaGraficos.map(d => d.totalValue), backgroundColor: backgroundColors, borderColor: borderColors, borderWidth: 1 }] },
                options: { 
                    responsive: true, maintainAspectRatio: false, 
                    plugins: { tooltip: { callbacks: { label: context => `${context.label}: ${formatCurrency(context.raw)}` } } },
                    onClick: (event, elements) => {
                        if (elements.length > 0) {
                            const index = elements[0].index;
                            const clickedDepData = topDataParaGraficos[index]; 
                             if (clickedDepData && clickedDepData.nombre) {
                                const filtered = _contratosValidosGlobal.filter(c => 
                                    c.dependencia === clickedDepData.nombre &&
                                    _docSecopContratistasFrecuentesGlobal.has(c.documentoSecop)
                                );
                                displayDrilldownTable(filtered, `Contratos para Área: ${clickedDepData.nombre} (Cont. Frecuentes)`);
                            }
                        }
                    }
                }
            });
            chartCantidadPorDependencia = new Chart(ctxCantidad, { 
                type: 'bar', 
                data: { labels: labels, datasets: [{ label: 'Cantidad de Contratos', data: topDataParaGraficos.map(d => d.countContratos), backgroundColor: backgroundColors, borderColor: borderColors, borderWidth: 1 }] },
                options: { 
                    responsive: true, maintainAspectRatio: false, 
                    scales: { y: { beginAtZero: true, ticks: { stepSize: 1, callback: function(value) {if (Number.isInteger(value)) {return value;}} } } }, 
                    plugins: { tooltip: { callbacks: { label: context => `${context.label}: ${context.raw} contratos` } } },
                    onClick: (event, elements) => {
                         if (elements.length > 0) {
                            const index = elements[0].index;
                            const clickedDepData = topDataParaGraficos[index];
                             if (clickedDepData && clickedDepData.nombre) {
                                const filtered = _contratosValidosGlobal.filter(c => 
                                    c.dependencia === clickedDepData.nombre &&
                                    _docSecopContratistasFrecuentesGlobal.has(c.documentoSecop)
                                );
                                displayDrilldownTable(filtered, `Contratos para Área: ${clickedDepData.nombre} (Cont. Frecuentes)`);
                            }
                        }
                    }
                }
            });
        }

        // --- Event Listeners & Initialization ---
        if(processPastedDataBtn && csvTextArea) {
            processPastedDataBtn.addEventListener('click', () => {
                console.log("DEVLOG: 'Procesar Datos Pegados' button clicked.");
                const csvText = csvTextArea.value;
                if (csvText && csvText.trim() !== "") {
                    showMessage('Procesando datos pegados...', 'info');
                    try {
                        const data = parseCSV(csvText);
                        procesarDatos(data);
                    } catch (error) { 
                        console.error("Error crítico al procesar datos pegados:", error);
                        showMessage(`Error crítico con datos pegados: ${error.message}. Revisa la consola.`, 'error');
                        analysisSectionsEl.classList.add('hidden');
                        drilldownSectionEl.classList.add('hidden');
                    }
                } else {
                    showMessage('El área de texto está vacía. Pega el contenido de tu CSV primero.', 'warn');
                }
            });
        }
        
        toggleTablaValidos.addEventListener('click', function() { /* ... */ });
        toggleTablaRechazados.addEventListener('click', function() { /* ... */ });
        toggleTablaMultiContratistas.addEventListener('click', function() { /* ... */ });
        toggleTablaDrilldown.addEventListener('click', function() { /* ... */ });
        tablaMultiContratistasBody.addEventListener('click', function(event) { /* ... */ });
        tablaResumenDependenciaBody.addEventListener('click', function(event) { /* ... */ });
        // (Re-insertar listeners de la última respuesta funcional)
         toggleTablaValidos.addEventListener('click', function() {
            const isHidden = contenedorTablaValidos.classList.toggle('hidden');
            this.textContent = isHidden ? 'Mostrar Detalles (Válidos)' : 'Ocultar Detalles (Válidos)';
        });
        toggleTablaRechazados.addEventListener('click', function() {
            const isHidden = contenedorTablaRechazados.classList.toggle('hidden');
            this.textContent = isHidden ? 'Mostrar Detalles (Rechazados)' : 'Ocultar Detalles (Rechazados)';
        });
        toggleTablaMultiContratistas.addEventListener('click', function() {
            const isHidden = contenedorTablaMultiContratistas.classList.toggle('hidden');
            this.textContent = isHidden ? 'Mostrar Detalles' : 'Ocultar Detalles';
        });
        toggleTablaDrilldown.addEventListener('click', function() {
            contenedorTablaDrilldown.classList.add('hidden');
            drilldownSectionEl.classList.add('hidden'); 
        });
         tablaMultiContratistasBody.addEventListener('click', function(event) {
            let targetRow = event.target.closest('tr');
            if (targetRow && targetRow.parentElement === tablaMultiContratistasBody) {
                const docSecop = targetRow.getAttribute('data-doc-secop');
                const nombreDisplay = targetRow.getAttribute('data-nombre-display');
                if (docSecop) {
                    const filtered = _contratosValidosGlobal.filter(c => c.documentoSecop === docSecop);
                    displayDrilldownTable(filtered, `Contratos para Doc.SECOP: ${docSecop} (${nombreDisplay})`);
                }
            }
        });
        tablaResumenDependenciaBody.addEventListener('click', function(event) {
            let targetRow = event.target.closest('tr');
            if (targetRow && targetRow.parentElement === tablaResumenDependenciaBody) {
                const areaNombre = targetRow.getAttribute('data-area-nombre');
                if (areaNombre) {
                    filterAndDisplayMultiContractorsByArea(areaNombre);
                    const seccionMulti = document.getElementById('seccion-multi-contratistas');
                    if (seccionMulti) seccionMulti.scrollIntoView({ behavior: 'smooth', block: 'start' });
                }
            }
        });

        function inicializarPagina() {
            document.getElementById('fecha-generacion').textContent = new Date().toLocaleDateString('es-ES', { year: 'numeric', month: 'long', day: 'numeric', hour: '2-digit', minute: '2-digit' });
            document.getElementById('current-year').textContent = new Date().getFullYear();
            analysisSectionsEl.classList.add('hidden'); 
            seccionContratosRechazados.style.display = 'none';
            drilldownSectionEl.classList.add('hidden'); 
            toggleTablaValidos.textContent = 'Mostrar Detalles (Válidos)';
            contenedorTablaValidos.classList.add('hidden');
            toggleTablaRechazados.textContent = 'Mostrar Detalles (Rechazados)';
            contenedorTablaRechazados.classList.add('hidden');
            toggleTablaMultiContratistas.textContent = 'Mostrar Detalles';
            contenedorTablaMultiContratistas.classList.add('hidden');
            toggleTablaDrilldown.textContent = 'Cerrar Detalle'; 
            contenedorTablaDrilldown.classList.add('hidden');
            if(tituloMultiContratistasEl) {
                tituloMultiContratistasEl.dataset.originalTitle = "Contratistas con Múltiples Contratos (por Doc. SECOP, Basado en Contratos Válidos)";
                tituloMultiContratistasEl.dataset.isFiltered = "false";
             }
            console.log("Página de análisis de contratistas inicializada.");

            // Cargar automáticamente los datos incrustados al iniciar
            if (typeof embeddedCSVData !== 'undefined' && embeddedCSVData && embeddedCSVData.trim() !== '') {
                console.log("DEVLOG: Cargando datos incrustados automáticamente...");
                showMessage('Cargando datos incrustados...', 'info');
                setTimeout(() => { 
                    try {
                        const data = parseCSV(embeddedCSVData);
                        procesarDatos(data);
                    } catch (error) {
                        console.error("Error crítico al procesar datos incrustados:", error);
                        showMessage(`Error crítico con datos incrustados: ${error.message}. Revisa la consola.`, 'error');
                    }
                }, 50);
            } else {
                console.warn("DEVLOG: No hay datos CSV incrustados para cargar automáticamente. Debes pegar los datos en la variable 'embeddedCSVData' en el script o usar el área de texto.");
                showMessage('No hay datos CSV incrustados. Pega tus datos CSV en el área de texto de arriba y presiona "Procesar Datos Pegados", o edita la variable "embeddedCSVData" en el script si quieres que se carguen por defecto.', 'warn');
            }
        }
        inicializarPagina();
    });
    </script>
</body>
</html>
