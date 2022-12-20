'use strict';

process.stdin.resume();
process.stdin.setEncoding('utf-8');

let inputString = '';
let currentLine = 0;

process.stdin.on('data', function(inputStdin) {
    inputString += inputStdin;
});

process.stdin.on('end', function() {
    inputString = inputString.split('\n');

    main();
});

function readLine() {
    return inputString[currentLine++];
}

/*
 * Complete the 'plusMinus' function below.
 *
 * The function accepts INTEGER_ARRAY arr as parameter.
 */

function plusMinus(arr) {
    let posCount = 0
    let negCount = 0
    let zeroCount = 0
    
    arr.forEach(num => {
        if(num > 0){
            posCount++
        } else if (num < 0){
            negCount++
        } else if (num == 0){
            zeroCount++
        }
    })
    console.log((posCount/arr.length).toFixed(6,10))
    console.log((negCount/arr.length).toFixed(6,10))
    console.log((zeroCount/arr.length).toFixed(6,10))
    

}

//Create forEach loop. One loop for positive numbers, negative numbers, and zero numbers.
//Checked if they were positive, negative or zero. Then I created three variables for the count of each kind of number. And lastly we logged the ratio. 
function main() {
    const n = parseInt(readLine().trim(), 10);
    let temp = readLine()
    temp = temp.replace(/\s+$/g, '')
    temp = temp.split(' ')
    const arr = (((readLine()).replace(/\s+$/g, '')).split(' ')).map(arrTemp => parseInt(arrTemp, 10));

    plusMinus(arr);
}
