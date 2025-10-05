<!doctype html>
<html lang="es">
<head>
  <meta charset="utf-8" />
  <title>Aplicaciones de la Estadística - Interactivo</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <script src="https://cdn.plot.ly/plotly-2.26.0.min.js"></script>
  <style>
    body { font-family: system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial; margin: 0; padding: 12px; background-color: #ffffff; }
    #chart { width: 100%; max-width: 1000px; height: 560px; margin: 0 auto; }
    .credit { text-align:center; font-size:12px; color:#666; margin-top:8px; }
  </style>
</head>
<body>
  <div id="chart"></div>
  <div class="credit">Gráfico interactivo: Aplicaciones de la Estadística — Elaboración propia.</div>

  <script>
    // Datos
    const campos = [
      "Educación",
      "Salud",
      "Economía",
      "Informática",
      "Ciencias Sociales",
      "Ingeniería",
      "Medio Ambiente"
    ];

    const niveles = [85, 90, 95, 80, 88, 75, 70];

    // Tooltips explicativos (2-3 líneas cada uno, en tono académico)
    const hoverText = [
      "Educación: Analiza el rendimiento académico, evalúa programas y orienta decisiones pedagógicas basadas en evidencias. Permite detectar brechas y medir impacto didáctico.",
      "Salud: Estudia incidencia y prevalencia de enfermedades, evalúa eficacia de tratamientos y soporta decisiones en epidemiología y gestión sanitaria.",
      "Economía: Apoya la estimación de indicadores macro y microeconómicos, pronósticos y evaluación de políticas públicas y modelos de mercado.",
      "Informática: Fundamental en minería de datos, aprendizaje automático y evaluación de modelos predictivos aplicados a grandes volúmenes de datos.",
      "Ciencias Sociales: Instrumenta el análisis de encuestas, censos y estudios de comportamiento social para formular hipótesis y validar teorías.",
      "Ingeniería: Se utiliza en control de calidad, diseño de experimentos y optimización de procesos productivos y de mantenimiento.",
      "Medio Ambiente: Contribuye al modelado climático, monitoreo ambiental y evaluación de impacto para la gestión sostenible de recursos."
    ];

    // Colores temáticos (cada barra un color distinto según área)
    const colors = [
      "#2E86C1", // Educación - azul
      "#28B463", // Salud - verde
      "#D4A017", // Economía - dorado
      "#7D3C98", // Informática - morado
      "#17A2B8", // Ciencias Sociales - teal
      "#6E6E6E", // Ingeniería - gris
      "#1E8449"  // Medio Ambiente - verde oscuro
    ];

    const trace = {
      x: campos,
      y: niveles,
      type: 'bar',
      marker: { color: colors, line: { color: '#222', width: 0.5 } },
      hovertemplate: '<b>%{x}</b><br><br>' +
                     '%{customdata}<br><br>' +
                     '<b>Nivel de uso:</b> %{y}%<extra></extra>',
      // attach customdata to show the explanatory tooltip text
      customdata: hoverText,
    };

    const layout = {
      title: {
        text: 'Aplicaciones de la Estadística en Diferentes Campos del Conocimiento',
        font: { size: 18, family: "'Helvetica Neue', Arial, sans-serif" }
      },
      xaxis: {
        tickangle: -25,
        tickfont: { size: 12 }
      },
      yaxis: {
        title: 'Nivel de uso o relevancia (%)',
        range: [0, 100],
        dtick: 10
      },
      margin: { l: 70, r: 20, t: 80, b: 120 },
      hoverlabel: { align: 'left' },
      showlegend: false
    };

    Plotly.newPlot('chart', [trace], layout, {responsive: true});
  </script>
</body>
</html># Genially...
