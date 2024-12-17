
function catalanNumber(n) {
  let result = factorial(2 * n) / (factorial(n + 1) * factorial(n));
  return result;
}


function factorial(num) {
  if (num === 0 || num === 1) return 1;
  let result = 1;
  for (let i = 2; i <= num; i++) {
    result *= i;
  }
  return result;
}


let catalanNumbers = [];
for (let i = 0; i < 20; i++) {
  catalanNumbers.push(catalanNumber(i));
}
console.log("1. Original Catalan Numbers:", catalanNumbers);


const divisibleBy3 = catalanNumbers.filter(num => num % 3 === 0);
const divisibleBy4 = catalanNumbers.filter(num => num % 4 === 0);

console.log("2. Numbers Divisible by 3:", divisibleBy3);
console.log("3. Numbers Divisible by 4:", divisibleBy4);


const squareRoots = divisibleBy3.map(num => Math.sqrt(num).toFixed(2));
console.log("4. Square Roots of Numbers Divisible by 3:", squareRoots);


const largestProduct = divisibleBy4.reduce((product, num) => product * num, 1);
console.log("5. Largest Product of Numbers Divisible by 4:", largestProduct);
