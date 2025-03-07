//Rosilaine
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Exemplo de Array e Números</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 20px;
      background-color: #f0f0f0;
    }
    .result {
      margin-top: 20px;
      font-size: 1.2rem;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <h1>Array com Números Aleatórios e Filtragem</h1>

  <div class="result" id="originalArray"></div>
  <div class="result" id="evenNumbers"></div>
  <div class="result" id="oddNumbers"></div>
  <div class="result" id="primeNumbers"></div>

  <script>
    // Função para gerar números aleatórios de 1 a 100
    function generateRandomArray(size) {
      let arr = [];
      for (let i = 0; i < size; i++) {
        arr.push(Math.floor(Math.random() * 100) + 1); // Números entre 1 e 100
      }
      return arr;
    }

    // Função para verificar se um número é primo
    function isPrime(num) {
      if (num <= 1) return false;
      for (let i = 2; i <= Math.sqrt(num); i++) {
        if (num % i === 0) return false;
      }
      return true;
    }

    // Função para separar números pares, ímpares e primos
    function separateNumbers(arr) {
      let evenNumbers = [];
      let oddNumbers = [];
      let primeNumbers = [];

      for (let num of arr) {
        if (num % 2 === 0) {
          evenNumbers.push(num);
        } else {
          oddNumbers.push(num);
        }

        if (isPrime(num)) {
          primeNumbers.push(num);
        }
      }

      return { evenNumbers, oddNumbers, primeNumbers };
    }

    // Gerar o array de 10 números aleatórios
    const randomArray = generateRandomArray(10);
    const { evenNumbers, oddNumbers, primeNumbers } = separateNumbers(randomArray);

    // Exibir os resultados na página
    document.getElementById('originalArray').textContent = `Array original: [${randomArray.join(', ')}]`;
    document.getElementById('evenNumbers').textContent = `Números pares: [${evenNumbers.join(', ')}]`;
    document.getElementById('oddNumbers').textContent = `Números ímpares: [${oddNumbers.join(', ')}]`;
    document.getElementById('primeNumbers').textContent = `Números primos: [${primeNumbers.join(', ')}]`;
  </script>
</body>
</html>
Array original: [12, 55, 72, 11, 9, 19, 47, 35, 84, 3]
Números pares: [12, 72, 84]
Números ímpares: [55, 11, 9, 19, 47, 35, 3]
Números primos: [11, 19, 47]

