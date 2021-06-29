
function getIdealNums(low, high) {
  let idealNum = 0;
  let totalIdealNums = 0;
  let i = 0;
 
  while (idealNum <= high) {   
    idealNum = Math.pow(3, i) + Math.pow(5, i)
    if (idealNum >= low && idealNum <= high) totalIdealNums++
    i++
  }

  return totalIdealNums;
}

function getIdealNums(low, high) {
  
}

function maxPower(base, high) {
  let maxPow;
  while (Math.pow(base, maxPow) < high) {
    console.log(`maxPow: ${maxPow}`)
    maxPow ? maxPow++ : maxPow = 0
  }
  return maxPow
}
// let maxPow = 0;
// for (let i = 0; Math.pow(base, i) <= high; i++) {
//   if (Math.pow(base, i) <= high) {
//     maxPow++
//   }
// }
// return maxPow
  // let i = 0;
  // let maxPower = 0;

  // while (maxPower < high) {
  //   const result = Math.pow(base, i)
  //   if (result < high) {
  //     maxPower = i;
  //     i++
  //   }
  // }

  // return i
// }

function minimizeBias(ratings) {
  ratings.sort((a,b) => a-b);

  let totalBias = 0;

  for (let i = 1; i < ratings.length; i+= 2) {
    totalBias += ratings[i] - ratings[i-1]
  }

  return totalBias;
}


function idealNumbers(min, max) {
  let totalCount = 0;

  for (let i = min; i <= max; i++) {
    let num = i
    while (num % 3 === 0) {
      num /= 3
    }
    while (num % 5 === 0) {
      num /= 5
    }

    if (num === 1) totalCount++
  }

  return totalCount;
}



