# curly-doodle
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gerador de Números da Loteria</title>
</head>
<body>
    <h1>Números da Loteria</h1>
    <p id="numerosSorteados"></p>
    <button onclick="gerarNumeros()">Gerar Números</button>

    <script>
        function gerarNumeros() {
            const qtdNumeros = 6;
            const minimo = 1;
            const maximo = 60;

            const numerosLoteria = new Set();

            while (numerosLoteria.size < qtdNumeros) {
                const numeroSorteado = Math.floor(Math.random() * (maximo - minimo + 1)) + minimo;
                numerosLoteria.add(numeroSorteado);
            }

            const numerosSorteados = Array.from(numerosLoteria).sort((a, b) => a - b);
            document.getElementById("numerosSorteados").textContent = `Números: ${numerosSorteados.join(', ')}`;
        }
    </script>
</body>
</html>
