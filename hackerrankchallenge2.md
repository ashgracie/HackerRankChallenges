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
 * Complete the 'miniMaxSum' function below.
 *
 * The function accepts INTEGER_ARRAY arr as parameter.
 */

function miniMaxSum(arr) {
    // Write your code here
    let max=0;
    let min = 1000000000+1;
    let sum = 0;
    arr.forEach(num => {
        sum += num
        if(num>max){
            max=num
        }
        if(num<min){
            min = num
        }
    })
    console.log(`${sum-max} ${sum-min}`)
}
// Started off by creating a forEach loop. In that forEach loop we figured out the max and minimum numbers. We also created the sum of all the numbers in the array. We used a max a min and a sum variable to achieve all of this. Lastly we used console.log to subtract the max from the sum to get the small sum. We got the large sum by subtracting the minimum. 
function main() {

    const arr = readLine().replace(/\s+$/g, '').split(' ').map(arrTemp => parseInt(arrTemp, 10));

    miniMaxSum(arr);
}
