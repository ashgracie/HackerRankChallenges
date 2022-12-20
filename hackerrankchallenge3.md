'use strict';

const fs = require('fs');

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
 * Complete the 'timeConversion' function below.
 *
 * The function is expected to return a STRING.
 * The function accepts STRING s as parameter.
 */

function timeConversion(s) {
    let arr = s.split(':')
    if(arr[2].charAt(2) == "A" ){
        if(arr[0] == "12"){
            arr[0] = "00"
        }
    } else {
        
        arr[0]*=1
        arr[0]+=12;
        arr[0]= ""+arr[0]
    }
    console.log(`${arr[0]}:${arr[1]}:${arr[2].substr(0,2)}`)

}

function main() {
    const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

    const st = readLine();

    const result = timeConversion(st);

    ws.write(result + '\n');

    ws.end();
}
