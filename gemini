<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Amplificador de Voz - Para Clases</title>
    
    <meta name="theme-color" content="#667eea">
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
    <meta name="apple-mobile-web-app-title" content="Amplificador Voz">
    <meta name="mobile-web-app-capable" content="yes">
    
    <link rel="icon" type="image/svg+xml" href="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCA1MTIgNTEyIj48cmVjdCB4PSIwIiB5PSIwIiB3aWR0aD0iNTEyIiBoZWlnaHQ9IjUxMiIgZmlsbD0iIzY2N2VlYSIvPjx0ZXh0IHg9IjI1NiIgeT0iMzAwIiBmb250LXNpemU9IjIwMCIgdGV4dC1hbmNob3I9Im1pZGRsZSIgZmlsbD0id2hpdGUiPvCfj6Q8L3RleHQ+PC9zdmc+">
    
    <style>
        /* Reset y estilos base */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 20px;
            color: white;
            user-select: none; /* Previene selección de texto accidental */
        }

        /* Contenedor principal */
        .container {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 30px;
            text-align: center;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.2);
            max-width: 450px; /* Aumentado para mejor legibilidad */
            width: 100%;
        }

        /* Títulos y subtítulos */
        h1 {
            font-size: 2.5em;
            margin-bottom: 10px;
            font-weight: 300;
        }

        .subtitle {
            font-size: 1.2em;
            opacity: 0.9;
            margin-bottom: 30px;
            color: #FFE082; /* Tono amarillo para subtítulo */
        }

        /* Mensajes de advertencia/información */
        .https-warning, .offline-ready, .install-section, .output-device-tip, .setup-section { 
            border-radius: 10px;
            padding: 15px;
            margin-bottom: 20px;
            font-size: 0.9em;
            text-align: left; /* Alineado a la izquierda para mejor lectura */
        }

        .https-warning {
            background: rgba(255, 152, 0, 0.2);
            border: 2px solid rgba(255, 152, 0, 0.5);
            display: none; /* Oculto por defecto, se muestra con JS */
        }

        .offline-ready {
            background: rgba(76, 175, 80, 0.2);
            border: 2px solid rgba(76, 175, 80, 0.5);
            animation: offlineGlow 3s ease-in-out infinite;
        }

        @keyframes offlineGlow {
            0%, 100% { box-shadow: 0 0 10px rgba(76, 175, 80, 0.3); }
            50% { box-shadow: 0 0 20px rgba(76, 175, 80, 0.5); }
        }

        .install-section {
            background: rgba(33, 150, 243, 0.2);
            border: 2px solid rgba(33, 150, 243, 0.5);
        }
        
        /* Estilo para el mensaje de dispositivo de salida */
        .output-device-tip {
            background: rgba(255, 255, 255, 0.1);
            border: 2px solid rgba(255, 255, 255, 0.2);
            font-size: 1em;
            display: none; /* Oculto por defecto */
        }

        /* Estado del amplificador */
        .status {
            font-size: 1.3em;
            margin-bottom: 30px;
            padding: 20px;
            border-radius: 15px;
            background: rgba(255, 255, 255, 0.1);
            border: 2px solid rgba(255, 255, 255, 0.2);
            font-weight: 500;
            transition: background 0.3s ease, border-color 0.3s ease; /* Transición para cambios de estado */
        }

        .status.active {
            background: rgba(76, 175, 80, 0.3);
            border-color: rgba(76, 175, 80, 0.7);
            animation: activeGlow 2s ease-in-out infinite;
        }

        .status.error {
            background: rgba(244, 67, 54, 0.3);
            border-color: rgba(244, 67, 54, 0.7);
        }

        @keyframes activeGlow {
            0%, 100% { box-shadow: 0 0 20px rgba(76, 175, 80, 0.3); }
            50% { box-shadow: 0 0 30px rgba(76, 175, 80, 0.6); }
        }

        /* Controles de botones */
        .controls {
            display: flex;
            flex-direction: column;
            gap: 20px;
            margin-bottom: 30px;
        }

        .btn {
            padding: 18px 35px;
            font-size: 1.3em;
            font-weight: 600;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            background: rgba(255, 255, 255, 0.2);
            color: white;
            border: 3px solid rgba(255, 255, 255, 0.3);
            text-transform: uppercase;
            letter-spacing: 1px;
            touch-action: manipulation; /* Mejora respuesta táctil */
        }

        .btn:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.3);
        }

        .btn:active {
            transform: translateY(-1px);
        }

        .btn.primary {
            background: linear-gradient(45deg, #4CAF50, #45a049);
            border-color: #4CAF50;
            box-shadow: 0 4px 15px rgba(76, 175, 80, 0.4);
        }

        .btn.primary:hover {
            background: linear-gradient(45deg, #45a049, #3d8b40);
            box-shadow: 0 8px 25px rgba(76, 175, 80, 0.6);
        }

        .btn.danger {
            background: linear-gradient(45deg, #f44336, #d32f2f);
            border-color: #f44336;
            box-shadow: 0 4px 15px rgba(244, 67, 54, 0.4);
            animation: pulseRed 1.5s ease-in-out infinite; /* Animación para botón de detener */
        }

        .btn.danger:hover {
            background: linear-gradient(45deg, #d32f2f, #b71c1c);
        }

        @keyframes pulseRed {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        /* Controles deslizantes (sliders) */
        .volume-control, .delay-control {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 25px;
            margin: 20px 0;
        }

        .volume-control label, .delay-control label {
            display: block;
            margin-bottom: 15px;
            font-size: 1.2em;
            font-weight: 600;
        }

        .volume-slider, .delay-slider {
            width: 100%;
            height: 10px;
            border-radius: 5px;
            background: rgba(255, 255, 255, 0.3);
            outline: none;
            -webkit-appearance: none; /* Para personalizar en WebKit/Chrome */
            margin: 10px 0;
            cursor: grab; /* Cursor de arrastre */
        }

        .volume-slider::-webkit-slider-thumb, .delay-slider::-webkit-slider-thumb {
            -webkit-appearance: none;
            appearance: none;
            width: 25px;
            height: 25px;
            border-radius: 50%;
            background: linear-gradient(45deg, #FFE082, #FFC107);
            cursor: grab;
            box-shadow: 0 3px 8px rgba(0, 0, 0, 0.4);
        }

        .volume-slider::-moz-range-thumb, .delay-slider::-moz-range-thumb {
            width: 25px;
            height: 25px;
            border-radius: 50%;
            background: linear-gradient(45deg, #FFE082, #FFC107);
            cursor: grab;
            border: none;
            box-shadow: 0 3px 8px rgba(0, 0, 0, 0.4);
        }

        .delay-slider::-webkit-slider-thumb, .delay-slider::-moz-range-thumb {
            background: linear-gradient(45deg, #9C27B0, #E91E63); /* Color diferente para el delay */
        }

        .volume-display {
            margin-top: 15px;
            font-size: 1.4em;
            font-weight: bold;
            color: #FFE082;
        }

        .delay-display {
            margin-top: 10px;
            font-size: 1.1em;
            font-weight: bold;
            color: #E1BEE7; /* Tono de púrpura para delay */
        }

        /* Sección de información y configuración inicial */
        .info {
            font-size: 1em;
            opacity: 0.9;
            line-height: 1.6;
            background: rgba(255, 255, 255, 0.1);
            padding: 20px;
            border-radius: 15px;
            margin-top: 20px;
            text-align: left;
        }

        .info strong {
            color: #FFE082;
            font-size: 1.1em;
        }

        .microphone-icon {
            font-size: 5em;
            margin-bottom: 20px;
            opacity: 0.8;
            filter: drop-shadow(0 4px 8px rgba(0, 0, 0, 0.3));
            transition: transform 0.3s ease, opacity 0.3s ease; /* Transición para la animación */
        }

        .pulse {
            animation: pulse 1.5s infinite;
        }

        @keyframes pulse {
            0% { transform: scale(1); opacity: 0.8; }
            50% { transform: scale(1.15); opacity: 1; }
            100% { transform: scale(1); opacity: 0.8; }
        }

        .setup-section {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 20px;
            margin-bottom: 25px;
            border: 2px solid rgba(255, 255, 255, 0.2);
            text-align: left;
        }

        .setup-title {
            font-size: 1.3em;
            font-weight: bold;
            margin-bottom: 15px;
            color: #FFE082;
            text-align: center;
        }

        .setup-steps {
            list-style: none; /* Quita viñetas por defecto */
        }

        .setup-steps li {
            margin-bottom: 8px;
            position: relative;
            padding-left: 25px; /* Espacio para el ícono */
        }

        .setup-steps li:before {
            content: "✓"; /* Ícono de check */
            position: absolute;
            left: 0;
            color: #4CAF50;
            font-weight: bold;
        }

        /* Barra de nivel de audio */
        .audio-level {
            width: 100%;
            height: 20px;
            background: rgba(255, 255, 255, 0.2);
            border-radius: 10px;
            overflow: hidden;
            margin: 15px 0;
            border: 1px solid rgba(255, 255, 255, 0.3);
        }

        .audio-level-bar {
            height: 100%;
            background: linear-gradient(90deg, #4CAF50, #8BC34A, #CDDC39, #FFC107, #FF5722);
            width: 0%;
            transition: width 0.1s ease, background 0.3s ease;
            border-radius: 10px;
        }

        /* Media queries para responsividad */
        @media (max-width: 480px) {
            .container {
                padding: 20px;
                margin: 10px;
            }
            
            h1 {
                font-size: 2em;
            }
            
            .btn {
                font-size: 1.1em;
                padding: 15px 25px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="https-warning" id="httpsWarning">
            ⚠️ <strong>ATENCIÓN:</strong> Necesitas **HTTPS** para usar el micrófono.<br>
            Sube el archivo a un servidor HTTPS o usa localhost con certificado.
        </div>

        <div class="offline-ready" id="offlineReady">
            📡 <strong>MODO OFFLINE ACTIVADO</strong><br>
            ¡Funciona sin internet una vez cargado!
        </div>

        <div class="install-section" id="installSection">
            📱 <strong>Para usar siempre:</strong><br>
            • En Chrome: Menú (<span style="font-size: 1.2em; vertical-align: middle;">&#8942;</span>) &rarr; "Instalar aplicación"<br>
            • En Safari: Compartir (<span style="font-size: 1.2em; vertical-align: middle;">&#x21E7;</span>) &rarr; "Añadir a pantalla de inicio"<br>
            • Funciona 100% offline después de instalar.
        </div>
        
        <div class="output-device-tip" id="outputDeviceTip">
            🔊 **SALIDA DE AUDIO**<br>
            El audio saldrá por el **dispositivo predeterminado de tu sistema**. Si conectás **auriculares o un micrófono USB/jack**, tu sistema puede cambiar la salida automáticamente. Asegurate de seleccionar el **parlante Bluetooth** como salida principal en la **configuración de sonido de tu dispositivo** (Android/iOS/PC) para evitar esto.
        </div>

        <div class="microphone-icon" id="micIcon">🎤</div>
        <h1>Amplificador de Voz</h1>
        <p class="subtitle">📚 Ideal para dar tus clases sin forzar la voz</p>
        
        <div class="setup-section">
            <div class="setup-title">🔧 Guía Rápida para el Sonido</div>
            <ol class="setup-steps">
                <li>1. **CONECTA tu Parlante Bluetooth** (o auriculares).</li>
                <li>2. Asegúrate que sea la **salida de audio principal** en la configuración de tu dispositivo.</li>
                <li>3. Mantén el teléfono cerca del micrófono (20-30cm).</li>
                <li>4. ¡Presiona **INICIAR** y ajusta el volumen gradualmente!</li>
            </ol>
        </div>
        
        <div class="status" id="status">
            🎯 Todo listo. Presiona **INICIAR** para amplificar tu voz.
        </div>

        <div class="audio-level" id="audioLevelContainer" style="display: none;">
            <div class="audio-level-bar" id="audioLevelBar"></div>
        </div>

        <div class="controls">
            <button class="btn primary" id="startBtn" onclick="startAmplifier()">
                🚀 INICIAR AMPLIFICADOR
            </button>
            <button class="btn danger" id="stopBtn" onclick="stopAmplifier()" style="display: none;">
                ⏹️ DETENER
            </button>
        </div>

        <div class="volume-control">
            <label for="volumeSlider">🔊 Control de Volumen (Hasta 200%)</label>
            <input type="range" id="volumeSlider" class="volume-slider" min="0" max="200" value="100">
            <div class="volume-display" id="volumeValue">100%</div>
        </div>

        <div class="delay-control">
            <label for="delaySlider">⏱️ Retardo Anti-Feedback (ms)</label>
            <input type="range" id="delaySlider" class="delay-slider" min="0" max="50" value="10">
            <div class="delay-display" id="delayValue">10ms</div>
        </div>


        <div class="info">
            <strong>💡 Consejos CLAVE:</strong><br><br>
            • **VOLUMEN HASTA 200%:** Usá con cuidado, puede distorsionar o causar acoples.<br>
            • **PARLANTE EXTERNO / AURICULARES:** Es **esencial** para evitar el feedback (acople). Si tu micrófono tiene salida de auriculares, usalos.<br>
            • **UBICACIÓN:** Mantené el parlante externo **alejado** del micrófono (mínimo 2 metros si es posible).<br>
            • **INICIO GRADUAL:** Empezá con volumen bajo (100%) y subí gradualmente si necesitás más potencia.<br>
            • **HTTPS:** Esta página debe cargarse con **HTTPS** (conexión segura) para acceder al micrófono.<br>
            • **PRUEBA PREVIA:** Siempre ajustá y probá antes de usar en una clase.<br>
            • **OFFLINE:** Funciona sin internet una vez cargado en tu navegador.
        </div>
    </div>

    <script>
        // Variables globales para el contexto de audio
        let audioContext;
        let microphone;
        let gainNode;
        let analyserNode;
        let delayNode;
        let isAmplifying = false; // Estado del amplificador
        let animationId; // Para la animación de la barra de audio
        let mediaStream; // Para detener la pista de audio del micrófono

        // Referencias a elementos del DOM
        const statusEl = document.getElementById('status');
        const startBtn = document.getElementById('startBtn');
        const stopBtn = document.getElementById('stopBtn');
        const volumeSlider = document.getElementById('volumeSlider');
        const volumeValue = document.getElementById('volumeValue');
        const delaySlider = document.getElementById('delaySlider');
        const delayValue = document.getElementById('delayValue');
        const micIcon = document.getElementById('micIcon');
        const audioLevelContainer = document.getElementById('audioLevelContainer');
        const audioLevelBar = document.getElementById('audioLevelBar');
        const httpsWarning = document.getElementById('httpsWarning');
        const outputDeviceTip = document.getElementById('outputDeviceTip');

        // --- Verificación de entorno y PWA ---
        // Muestra la advertencia si no se usa HTTPS (excepto en localhost)
        if (location.protocol !== 'https:' && location.hostname !== 'localhost') {
            httpsWarning.style.display = 'block';
        } else {
            httpsWarning.style.display = 'none'; // Asegura que no se muestre en localhost HTTPS
        }

        // --- Configuración de Audio (generalmente sensible a cambiar) ---
        // Se mantienen los settings originales de tu código (echoCancellation: false, etc.)
        // Puedes experimentar con true si hay mucho ruido o eco, pero para amplificación directa a veces es mejor desactivarlos.
        const audioConfig = {
            audio: {
                echoCancellation: false,   
                noiseSuppression: false,   
                autoGainControl: false,    
                sampleRate: 44100,         
                channelCount: 1,           
                latency: 0.02              
            }
        };

        // --- Event Listeners para Controles ---
        // Control de volumen
        volumeSlider.addEventListener('input', function() {
            const volume = parseInt(this.value);
            volumeValue.textContent = volume + '%';
            
            // Guarda el volumen en localStorage para recordar el ajuste
            try {
                localStorage.setItem('amplifierVolume', volume);
            } catch (e) {
                console.error("Error al guardar el volumen en localStorage:", e);
            }
            
            if (gainNode && audioContext) {
                // Cálculo de ganancia: Aumenta exponencialmente para mayor impacto,
                // multiplicando por un factor extra para más potencia.
                // 100% = 1.0, 200% = 2.0. Usamos pow(x, 1.2) para que suba más rápido al final.
                const gainFactor = Math.pow(volume / 100, 1.2); 
                gainNode.gain.setTargetAtTime(gainFactor, audioContext.currentTime, 0.03); // Suaviza la transición
            }
        });

        // Control de retardo
        delaySlider.addEventListener('input', function() {
            const delay = parseInt(this.value);
            delayValue.textContent = delay + 'ms';
            
            // Guarda el retardo en localStorage
            try {
                localStorage.setItem('amplifierDelay', delay);
            } catch (e) {
                console.error("Error al guardar el retardo en localStorage:", e);
            }
            
            if (delayNode && audioContext) {
                delayNode.delayTime.setTargetAtTime(delay / 1000, audioContext.currentTime, 0.01); // Convertir ms a segundos
            }
        });

        // --- Visualizador de Nivel de Audio ---
        function updateAudioLevel() {
            if (!analyserNode || !isAmplifying) return;

            const bufferLength = analyserNode.frequencyBinCount;
            const dataArray = new Uint8Array(bufferLength);
            analyserNode.getByteFrequencyData(dataArray); // Obtiene los datos de frecuencia

            // Calcula el RMS (Root Mean Square) para un nivel de volumen más preciso
            let sum = 0;
            for (let i = 0; i < bufferLength; i++) {
                sum += dataArray[i] * dataArray[i];
            }
            const rms = Math.sqrt(sum / bufferLength);
            // Mapea el RMS a un porcentaje para la barra de nivel (de 0 a 128, aprox 50% max útil)
            const percentage = Math.min((rms / 128) * 100, 100); 

            audioLevelBar.style.width = percentage + '%';
            
            // Cambia el color de la barra y el mensaje de estado según el nivel
            if (percentage > 90) {
                audioLevelBar.style.background = 'linear-gradient(90deg, #FF1744, #D50000)'; // Rojo intenso
                statusEl.textContent = '⚠️ NIVEL MUY ALTO - Reduce volumen o aleja parlante';
                statusEl.className = 'status error';
            } else if (percentage > 70) {
                audioLevelBar.style.background = 'linear-gradient(90deg, #FF9800, #F57C00)'; // Naranja
            } else if (percentage > 30) {
                audioLevelBar.style.background = 'linear-gradient(90deg, #4CAF50, #388E3C)'; // Verde normal
                // Si estaba en estado de error, lo reinicia a activo (si no es un error de inicio)
                if (statusEl.className === 'status error' && !statusEl.textContent.includes('Error:')) {
                    statusEl.textContent = '🔴 ¡AMPLIFICANDO EN VIVO! Hablá normalmente';
                    statusEl.className = 'status active';
                }
            } else {
                audioLevelBar.style.background = 'linear-gradient(90deg, #2196F3, #1976D2)'; // Azul (nivel bajo/silencio)
                if (statusEl.className === 'status error' && !statusEl.textContent.includes('Error:')) {
                    statusEl.textContent = '🔴 ¡AMPLIFICANDO EN VIVO! Hablá normalmente';
                    statusEl.className = 'status active';
                } else if (!isAmplifying && !statusEl.textContent.includes('Error:')) { // Si no está amplificando y no hay error
                    statusEl.textContent = '🎯 Todo listo. Presioná INICIAR para amplificar tu voz.';
                    statusEl.className = 'status';
                }
            }

            animationId = requestAnimationFrame(updateAudioLevel); // Siguiente frame
        }

        // --- Funciones de Control del Amplificador ---

        // Inicia la amplificación
        async function startAmplifier() {
            try {
                statusEl.textContent = '🔄 Iniciando amplificador...';
                statusEl.className = 'status'; // Limpia clases de error o activo
                startBtn.disabled = true; // Deshabilita el botón para evitar clics múltiples
                startBtn.style.opacity = 0.7; // Indicador visual de deshabilitado
                outputDeviceTip.style.display = 'block'; // Mostrar el consejo del parlante al iniciar

                // 1. Verificar soporte del navegador
                if (!navigator.mediaDevices || !navigator.mediaDevices.getUserMedia) {
                    throw new Error('Tu navegador no soporta la grabación de audio. Probá con Chrome, Firefox o Safari actualizados.');
                }

                // 2. Verificar HTTPS
                if (location.protocol !== 'https:' && location.hostname !== 'localhost') {
                    throw new Error('Para acceder al micrófono, la página debe cargarse sobre HTTPS (conexión segura). Subí el archivo a un servidor seguro o usá localhost para pruebas.');
                }

                statusEl.textContent = '🎤 Solicitando acceso al micrófono...';
                
                // 3. Solicitar acceso al micrófono
                let stream;
                try {
                    stream = await navigator.mediaDevices.getUserMedia(audioConfig);
                } catch (e) {
                    console.warn('Configuración avanzada de audio falló, probando con configuración básica:', e);
                    // Si falla, intenta con una configuración más básica
                    stream = await navigator.mediaDevices.getUserMedia({ audio: true });
                }
                
                mediaStream = stream; // Guarda la referencia del stream para poder detenerlo

                // 4. Crear y configurar AudioContext
                const AudioContext = window.AudioContext || window.webkitAudioContext;
                audioContext = new AudioContext({
                    latencyHint: 'interactive', // Prioriza baja latencia para tiempo real
                    sampleRate: 44100 // Asegura un sample rate consistente
                });

                // Reanudar el contexto si está suspendido (necesario en algunos navegadores/dispositivos, ej. iOS)
                if (audioContext.state === 'suspended') {
                    await audioContext.resume();
                }

                // 5. Crear nodos del grafo de audio
                microphone = audioContext.createMediaStreamSource(mediaStream);
                gainNode = audioContext.createGain(); // Nodo para controlar el volumen
                analyserNode = audioContext.createAnalyser(); // Nodo para visualizar el nivel de audio
                delayNode = audioContext.createDelay(0.1); // Nodo de retardo (máximo 100ms)

                // 6. Configurar analizador
                analyserNode.fftSize = 2048; // Más detalle en la frecuencia
                analyserNode.smoothingTimeConstant = 0.85; // Suaviza la transición de la barra de nivel

                // 7. Configurar ganancia y retardo iniciales con los valores del slider
                const currentVolume = parseInt(volumeSlider.value);
                const gainFactor = Math.pow(currentVolume / 100, 1.2); 
                gainNode.gain.setValueAtTime(gainFactor, audioContext.currentTime);

                const currentDelay = parseInt(delaySlider.value);
                delayNode.delayTime.setValueAtTime(currentDelay / 1000, audioContext.currentTime); // Convertir ms a segundos

                // 8. Conectar nodos: Micrófono -> Retardo -> Ganancia -> Analizador -> Salida (parlantes)
                microphone.connect(delayNode);
                delayNode.connect(gainNode);
                gainNode.connect(analyserNode); // Conecta también al analizador para la visualización
                gainNode.connect(audioContext.destination); // Conecta la ganancia a la salida de audio del sistema

                // 9. Actualizar estado de la interfaz
                isAmplifying = true;
                statusEl.textContent = '🔴 ¡AMPLIFICANDO EN VIVO! Hablá normalmente.';
                statusEl.className = 'status active';
                startBtn.style.display = 'none';
                stopBtn.style.display = 'block';
                micIcon.className = 'microphone-icon pulse'; // Agrega clase pulse para animación
                micIcon.textContent = '🔴'; // Cambia el ícono
                audioLevelContainer.style.display = 'block'; // Muestra la barra de nivel

                updateAudioLevel(); // Inicia la visualización del nivel de audio
                requestWakeLock(); // Solicita el Wake Lock
                console.log('✅ Amplificador iniciado correctamente');

            } catch (error) {
                console.error('❌ Error al iniciar amplificador:', error);
                handleStartError(error); // Llama a la función de manejo de errores
            } finally {
                startBtn.disabled = false; // Vuelve a habilitar el botón "Iniciar" en caso de error
                startBtn.style.opacity = 1;
            }
        }

        // Maneja y muestra errores de forma amigable
        function handleStartError(error) {
            let errorMessage = '❌ Error: ';
            
            if (error.name === 'NotAllowedError') {
                errorMessage += 'Debes permitir el acceso al micrófono. Recargá la página y aceptá el permiso cuando te lo solicite.';
            } else if (error.name === 'NotFoundError') {
                errorMessage += 'No se detectó un micrófono. Verificá que tu dispositivo tenga uno conectado y funcionando.';
            } else if (error.name === 'NotSupportedError' || error.message.includes('supported')) {
                errorMessage += 'Tu navegador no soporta las funciones de audio necesarias. Intentá usar Chrome, Firefox o Safari actualizados.';
            } else if (error.name === 'NotReadableError') {
                errorMessage += 'El micrófono está siendo usado por otra aplicación. Cerrá esa aplicación e intentá de nuevo.';
            } else if (error.name === 'SecurityError' || error.message.includes('HTTPS')) {
                errorMessage += 'Necesitas usar una conexión segura (HTTPS) para acceder al micrófono. Subí el archivo a un servidor HTTPS o usá localhost con un certificado para desarrollo.';
            } else if (error.name === 'AbortError') {
                errorMessage += 'La operación de acceso al micrófono fue abortada. Podría ser un problema interno del navegador o del dispositivo.';
            }
            else {
                errorMessage += error.message || 'Ocurrió un error desconocido al acceder al micrófono.';
            }
            
            statusEl.textContent = errorMessage;
            statusEl.className = 'status error'; // Cambia a estado de error visual
            startBtn.disabled = false;
            outputDeviceTip.style.display = 'none'; // Oculta el consejo del parlante si hay un error
        }

        // Detiene la amplificación
        function stopAmplifier() {
            try {
                // Detener la animación de la barra de audio
                if (animationId) {
                    cancelAnimationFrame(animationId);
                    animationId = null;
                }

                // Detener la pista del micrófono
                if (mediaStream) {
                    mediaStream.getTracks().forEach(track => {
                        track.stop(); // Detiene cada track del stream (ej. el audio)
                    });
                    mediaStream = null;
                }

                // Cerrar el AudioContext si está activo
                if (audioContext && audioContext.state !== 'closed') {
                    audioContext.close();
                    audioContext = null;
                }

                // Limpiar referencias a nodos
                microphone = null;
                gainNode = null;
                analyserNode = null;
                delayNode = null;
                isAmplifying = false;

                // Actualizar estado de la interfaz
                statusEl.textContent = '✅ Amplificador detenido. Listo para reiniciar.';
                statusEl.className = 'status'; // Vuelve al estado normal
                startBtn.style.display = 'block';
                startBtn.disabled = false;
                stopBtn.style.display = 'none';
                micIcon.className = 'microphone-icon'; // Remueve la animación
                micIcon.textContent = '🎤'; // Vuelve al ícono original
                audioLevelContainer.style.display = 'none'; // Oculta la barra de nivel
                audioLevelBar.style.width = '0%'; // Reinicia la barra
                outputDeviceTip.style.display = 'none'; // Oculta el consejo del parlante al detener

                if (wakeLock) {
                    wakeLock.release().then(() => {
                        wakeLock = null;
                        console.log('Wake Lock liberado.');
                    });
                }

                console.log('✅ Amplificador detenido correctamente');

            } catch (error) {
                console.error('Error al detener el amplificador:', error);
                statusEl.textContent = '❌ Error al detener: ' + (error.message || 'Desconocido');
                statusEl.className = 'status error';
            }
        }

        // --- Inicialización al cargar la página ---
        document.addEventListener('DOMContentLoaded', function() {
            // Cargar valores guardados de volumen y retardo
            try {
                const savedVolume = localStorage.getItem('amplifierVolume');
                if (savedVolume) {
                    volumeSlider.value = savedVolume;
                    volumeValue.textContent = savedVolume + '%';
                } else { // Si no hay volumen guardado, establece el valor predeterminado del slider
                    volumeSlider.value = 100; // Valor inicial
                    volumeValue.textContent = '100%';
                }

                const savedDelay = localStorage.getItem('amplifierDelay');
                if (savedDelay) {
                    delaySlider.value = savedDelay;
                    delayValue.textContent = savedDelay + 'ms';
                } else { // Si no hay retardo guardado
                    delaySlider.value = 10; // Valor inicial
                    delayValue.textContent = '10ms';
                }
            } catch (e) {
                console.warn("No se pudo acceder a localStorage (posiblemente modo incógnito o navegador restrictivo):", e);
            }
            
            console.log('📱 Amplificador de Voz cargado y listo');

            // Intento de reanudar el AudioContext al primer toque/clic
            // Esto es crucial para iOS y algunos navegadores que lo suspenden al inicio
            // Se añaden event listeners a document.body para capturar el primer toque/clic en cualquier lugar.
            document.body.addEventListener('touchstart', resumeAudioContext, { once: true });
            document.body.addEventListener('click', resumeAudioContext, { once: true });
        });

        // Función para reanudar el AudioContext (para navegadores móviles)
        async function resumeAudioContext() {
            // Solo intenta reanudar si audioContext existe y está suspendido
            if (audioContext && audioContext.state === 'suspended') {
                try {
                    await audioContext.resume();
                    console.log('AudioContext reanudado con el primer toque/clic.');
                } catch (e) {
                    console.error('Error al reanudar AudioContext:', e);
                }
            }
        }

        // --- Manejo de Wake Lock (Mantener pantalla encendida) ---
        let wakeLock = null;

        async function requestWakeLock() {
            if ('wakeLock' in navigator) {
                try {
                    wakeLock = await navigator.wakeLock.request('screen');
                    console.log('✅ Wake Lock activado.');
                } catch (err) {
                    console.warn('⚠️ No se pudo activar Wake Lock:', err.name, err.message);
                    // Puedes mostrar un mensaje al usuario si es importante que la pantalla no se apague
                }
            } else {
                console.log('Wake Lock API no soportada por este navegador.');
            }
        }

        // Cuando la visibilidad de la página cambia
        document.addEventListener('visibilitychange', async () => {
            if (wakeLock !== null && document.visibilityState === 'visible') {
                // Si la página vuelve a ser visible y teníamos un wake lock, intentamos adquirirlo de nuevo
                await requestWakeLock();
            }
        });

        // Previene el cierre accidental de la página si el amplificador está activo
        window.addEventListener('beforeunload', e => {
            if (isAmplifying) {
                e.preventDefault();
                e.returnValue = '¿Seguro que querés cerrar? El amplificador está activo y se detendrá.';
            }
        });

        // --- Service Worker (Para capacidades PWA/Offline) ---
        if ('serviceWorker' in navigator) {
            window.addEventListener('load', () => {
                navigator.serviceWorker.register('/sw.js') // Asegurate que sw.js esté en el directorio raíz o ajusta la ruta
                    .then(registration => {
                        console.log('Service Worker registrado con éxito:', registration);
                        document.getElementById('offlineReady').style.display = 'block'; // Muestra el mensaje de offline
                        document.getElementById('installSection').style.display = 'block'; // Muestra las instrucciones de instalación
                    })
                    .catch(error => {
                        console.error('Error al registrar Service Worker:', error);
                        document.getElementById('offlineReady').style.display = 'none'; // Oculta si hay error
                        document.getElementById('installSection').style.display = 'none'; // Oculta si hay error
                    });
            });
        } else {
            document.getElementById('offlineReady').style.display = 'none'; // Oculta si no hay soporte
            document.getElementById('installSection').style.display = 'none'; // Oculta si no hay soporte
        }
    </script>

    </body>
</html>
