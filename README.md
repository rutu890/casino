# casino


Deposit some money—--








const prompt = require("prompt-sync")();
const deposit = () => {
    while(true){
    const depositAmount = prompt("Enter a deposit amount : ");
    const numberDepositAmount = parseFloat(depositAmount);




    if(isNaN(numberDepositAmount) || numberDepositAmount <= 0) {
        console.log("Invalid deposit amount, try again.")
    } else {
        return numberDepositAmount;
    }
}
};
const depositAmount=deposit();
console.log(depositAmount);



















—---------------------------


Determine number of lines to bet on—-




const prompt = require("prompt-sync")();
const deposit = () => {
    while(true){
    const depositAmount = prompt("Enter a deposit amount : ");
    const numberDepositAmount = parseFloat(depositAmount);


    if(isNaN(numberDepositAmount) || numberDepositAmount <= 0) {
        console.log("Invalid deposit amount, try again.")
    } else {
        return numberDepositAmount;
    }
}
};


const getNumberOfLines = () => {
    while(true){
        const lines=prompt("Enter number of lines from 1 to 3 : ");
        const numberOfLines=parseFloat(lines);


        if (isNaN(numberOfLines) || numberOfLines <= 0 || numberOfLines > 3) {
            console.log("Invalid number of lines, try again.");
        } else {
            return numberOfLines;
        }
        }
    };




const depositAmount=deposit();
const numberOfLines=getNumberOfLines();





Bet you are going to have is gonna be multiplied by the number of lines, 
Right now we are allowed to bet based on your balance and not on num of lines,
Max bet you can make is balance divided by lines

const prompt = require("prompt-sync")();
const deposit = () => {
    while(true){
    const depositAmount = prompt("Enter a deposit amount : ");
    const numberDepositAmount = parseFloat(depositAmount);


    if(isNaN(numberDepositAmount) || numberDepositAmount <= 0) {
        console.log("Invalid deposit amount, try again.")
    } else {
        return numberDepositAmount;
    }
}
};


const getNumberOfLines = () => {
    while(true){
        const lines=prompt("Enter number of lines from 1 to 3 : ");
        const numberOfLines=parseFloat(lines);


        if (isNaN(numberOfLines) || numberOfLines <= 0 || numberOfLines > 3) {
            console.log("Invalid number of lines, try again.");
        } else {
            return numberOfLines;
        }
        }
    };




const getbet = (balance, lines) => {
    while(true){
    const bet = prompt("Enter the total bet per line : ");
    const numberBet = parseFloat(bet);


    if(isNaN(numberBet) || numberBet <= 0 || numberBet > (balance/lines)){
        console.log("Invalid bet, try again.");
    }else{
        return numberBet;
    }
}
}




//const depositAmount=deposit();
let balance=deposit();
const numberOfLines=getNumberOfLines();
const bet = getbet(balance,numberOfLines);




—----------------------------------------------------

Spin the slot machine–

const prompt = require("prompt-sync")();


const ROWS=3;
const COLS=3;


const SYMBOLS_COUNT={
    "A":2,
    "B":4,
    "C":6,
    "D":8
}


const SYMBOLS_VALUES={
    "A":5,
    "B":4,
    "C":3,
    "D":2
}






const deposit = () => {
    while(true){
    const depositAmount = prompt("Enter a deposit amount : ");
    const numberDepositAmount = parseFloat(depositAmount);


    if(isNaN(numberDepositAmount) || numberDepositAmount <= 0) {
        console.log("Invalid deposit amount, try again.")
    } else {
        return numberDepositAmount;
    }
}
};


const getNumberOfLines = () => {
    while(true){
        const lines=prompt("Enter number of lines from 1 to 3 : ");
        const numberOfLines=parseFloat(lines);


        if (isNaN(numberOfLines) || numberOfLines <= 0 || numberOfLines > 3) {
            console.log("Invalid number of lines, try again.");
        } else {
            return numberOfLines;
        }
        }
    };




const getbet = (balance, lines) => {
    while(true){
    const bet = prompt("Enter the total bet per line : ");
    const numberBet = parseFloat(bet);


    if(isNaN(numberBet) || numberBet <= 0 || numberBet > (balance/lines)){
        console.log("Invalid bet, try again.");
    }else{
        return numberBet;
    }
}
}


const spin = () => {
    const symbols=[];
    for(const[symbol, count] of Object.entries(SYMBOLS_COUNT)){
        //console.log(symbol,count);
        for(let i=0; i<count; i++)
        {
            symbols.push(symbol);
        }
    }
    console.log(symbols);


};


spin();


//const depositAmount=deposit();
let balance=deposit();
const numberOfLines=getNumberOfLines();
const bet = getbet(balance,numberOfLines);






Here aim is, We’re going to be able to - randomly select elements from the array -  when we’re inserting themin our reels

—--------------------------

const prompt = require("prompt-sync")();


const ROWS=3;
const COLS=3;


const SYMBOLS_COUNT={
    "A":2,
    "B":4,
    "C":6,
    "D":8
}


const SYMBOLS_VALUES={
    "A":5,
    "B":4,
    "C":3,
    "D":2
}






const deposit = () => {
    while(true){
    const depositAmount = prompt("Enter a deposit amount : ");
    const numberDepositAmount = parseFloat(depositAmount);


    if(isNaN(numberDepositAmount) || numberDepositAmount <= 0) {
        console.log("Invalid deposit amount, try again.")
    } else {
        return numberDepositAmount;
    }
}
};


const getNumberOfLines = () => {
    while(true){
        const lines=prompt("Enter number of lines from 1 to 3 : ");
        const numberOfLines=parseFloat(lines);


        if (isNaN(numberOfLines) || numberOfLines <= 0 || numberOfLines > 3) {
            console.log("Invalid number of lines, try again.");
        } else {
            return numberOfLines;
        }
        }
    };




const getbet = (balance, lines) => {
    while(true){
    const bet = prompt("Enter the total bet per line : ");
    const numberBet = parseFloat(bet);


    if(isNaN(numberBet) || numberBet <= 0 || numberBet > (balance/lines)){
        console.log("Invalid bet, try again.");
    }else{
        return numberBet;
    }
}
}


const spin = () => {
    const symbols=[];
    for(const[symbol, count] of Object.entries(SYMBOLS_COUNT)){
        //console.log(symbol,count);
        for(let i=0; i<count; i++)
        {
            symbols.push(symbol);
        }
    }
    //console.log(symbols);


    const reels=[[],[],[]];
    for (let i=0; i < COLS; i++) {
        const reelSymbols = [...symbols];
        for (let j = 0; j < ROWS; j++){
            const randomIndex = Math.floor(Math.random() * reelSymbols.length);
            const selectedSymbol = reelSymbols[randomIndex];
            reels[i].push(selectedSymbol);
            reelSymbols.splice(randomIndex,1);
        }
    }


    return reels;


};


const reels = spin();


console.log(reels);


//const depositAmount=deposit();
let balance=deposit();
const numberOfLines=getNumberOfLines();
const bet = getbet(balance,numberOfLines);






In const Spin(); —

Const symbols(); —

We started by generating an array of all of te available symbols that we picked from, when we’re gonna choose whats inside of each reel, randomly. 
So this contains all the available symbols here.


Const reels(); —

Then we created an temporary array, that we’re gonna add to.
It has all of the different reels, const reels = [ [], [], [] ]
We loop through all the reels that we have, which is represented by the number of columns COLS

 
—------------------------------------


But, if the number of columns is different than 3, we’re gonna get bit of a error here.
So we have to fix the function reels function…

const reels=[];
    for (let i=0; i < COLS; i++) {
        reels.push([]);
        const reelSymbols = [...symbols];
        for (let j = 0; j < ROWS; j++){
            const randomIndex = Math.floor(Math.random() * reelSymbols.length);
            const selectedSymbol = reelSymbols[randomIndex];
            reels[i].push(selectedSymbol);
            reelSymbols.splice(randomIndex,1);
        }
Now this will work correctly, because, for every single reel or column we have, we add inside of const reels=[];   , and once we add it, then we can now push elements inside of that reel.

Const reelSymbols = [ …symbols ];
Once we do that we then copy all of the available symbols that we have, we will have an unique array to pick from this specific reel.

For (let j=0; j < ROWS ; j++)
 Then we loop through all of the rows, all of the rows is the number of symbols we’re gonna have in each reel, and we randomly generate one of the available symbols. 
We pick one of the symbols which are available, and we insert that into our reel. 


Now we need to check if they won…



Now, our reels comes in this format,

[[A B C]], [[D D D]], [[A A A]]  —> vertical 

We need a one more check in form of rows(horizontal):

If the user is winning we need to check it in form of rows, 
	So we need to transpose the array, into all of the rows.

We want to have an array that has all of our rows.
Once we have rows, we can check who is winning what and then we can present it.

Our rows will look something like in this format,

[A D A]
[B D A] 
[C D A]  

And once we have that, we can continue…

This is called transposing a matrix.

Here we’re transposing a 2d array

const prompt = require("prompt-sync")();


const ROWS=3;
const COLS=3;


const SYMBOLS_COUNT={
    "A":2,
    "B":4,
    "C":6,
    "D":8
}


const SYMBOLS_VALUES={
    "A":5,
    "B":4,
    "C":3,
    "D":2
}






const deposit = () => {
    while(true){
    const depositAmount = prompt("Enter a deposit amount : ");
    const numberDepositAmount = parseFloat(depositAmount);


    if(isNaN(numberDepositAmount) || numberDepositAmount <= 0) {
        console.log("Invalid deposit amount, try again.")
    } else {
        return numberDepositAmount;
    }
}
};


const getNumberOfLines = () => {
    while(true){
        const lines=prompt("Enter number of lines from 1 to 3 : ");
        const numberOfLines=parseFloat(lines);


        if (isNaN(numberOfLines) || numberOfLines <= 0 || numberOfLines > 3) {
            console.log("Invalid number of lines, try again.");
        } else {
            return numberOfLines;
        }
        }
    };




const getbet = (balance, lines) => {
    while(true){
    const bet = prompt("Enter the total bet per line : ");
    const numberBet = parseFloat(bet);


    if(isNaN(numberBet) || numberBet <= 0 || numberBet > (balance/lines)){
        console.log("Invalid bet, try again.");
    }else{
        return numberBet;
    }
}
}


const spin = () => {
    const symbols=[];
    for(const[symbol, count] of Object.entries(SYMBOLS_COUNT)){
        //console.log(symbol,count);
        for(let i=0; i<count; i++)
        {
            symbols.push(symbol);
        }
    }
    //console.log(symbols);


    const reels=[];
    for (let i=0; i < COLS; i++) {
        reels.push([]);
        const reelSymbols = [...symbols];
        for (let j = 0; j < ROWS; j++){
            const randomIndex = Math.floor(Math.random() * reelSymbols.length);
            const selectedSymbol = reelSymbols[randomIndex];
            reels[i].push(selectedSymbol);
            reelSymbols.splice(randomIndex,1);
        }
    }


    return reels;


};


const transpose = (reels) => {
    const rows = [];


    for (let i = 0; i < ROWS; i++) {
        rows.push([]);
        for (let j = 0; j < COLS; j++) {
            rows[i].push(reels[j][i]);
        }
    }
    return rows;
};






//const depositAmount=deposit();
let balance=deposit();
const numberOfLines=getNumberOfLines();
const bet = getbet(balance,numberOfLines);
const reels = spin();
const rows=transpose(reels);
console.log(reels);
console.log(rows);


















—-----------------


Now that we have those, we can print those out and we can represent the user what it is that they actually spot 

const prompt = require("prompt-sync")();


const ROWS=3;
const COLS=3;


const SYMBOLS_COUNT={
    "A":2,
    "B":4,
    "C":6,
    "D":8
}


const SYMBOLS_VALUES={
    "A":5,
    "B":4,
    "C":3,
    "D":2
}






const deposit = () => {
    while(true){
    const depositAmount = prompt("Enter a deposit amount : ");
    const numberDepositAmount = parseFloat(depositAmount);


    if(isNaN(numberDepositAmount) || numberDepositAmount <= 0) {
        console.log("Invalid deposit amount, try again.")
    } else {
        return numberDepositAmount;
    }
}
};


const getNumberOfLines = () => {
    while(true){
        const lines=prompt("Enter number of lines from 1 to 3 : ");
        const numberOfLines=parseFloat(lines);


        if (isNaN(numberOfLines) || numberOfLines <= 0 || numberOfLines > 3) {
            console.log("Invalid number of lines, try again.");
        } else {
            return numberOfLines;
        }
        }
    };




const getbet = (balance, lines) => {
    while(true){
    const bet = prompt("Enter the total bet per line : ");
    const numberBet = parseFloat(bet);


    if(isNaN(numberBet) || numberBet <= 0 || numberBet > (balance/lines)){
        console.log("Invalid bet, try again.");
    }else{
        return numberBet;
    }
}
}


const spin = () => {
    const symbols=[];
    for(const[symbol, count] of Object.entries(SYMBOLS_COUNT)){
        //console.log(symbol,count);
        for(let i=0; i<count; i++)
        {
            symbols.push(symbol);
        }
    }
    //console.log(symbols);


    const reels=[];
    for (let i=0; i < COLS; i++) {
        reels.push([]);
        const reelSymbols = [...symbols];
        for (let j = 0; j < ROWS; j++){
            const randomIndex = Math.floor(Math.random() * reelSymbols.length);
            const selectedSymbol = reelSymbols[randomIndex];
            reels[i].push(selectedSymbol);
            reelSymbols.splice(randomIndex,1);
        }
    }


    return reels;


};


const transpose = (reels) => {
    const rows = [];


    for (let i = 0; i < ROWS; i++) {
        rows.push([]);
        for (let j = 0; j < COLS; j++) {
            rows[i].push(reels[j][i]);
        }
    }
    return rows;
};


const printRows= (rows) => {
    for(const row of rows) {
        //let rowString = " A | B | C ";
        let rowString = "";
        for (const [i, symbol] of row.entries()) {
            rowString += symbol
            if (i != row.length -1 ) {
                rowString += " | "
            }
           
        }
        console.log(rowString)
    }
}




//const depositAmount=deposit();
let balance=deposit();
const numberOfLines=getNumberOfLines();
const bet = getbet(balance,numberOfLines);
const reels = spin();
const rows=transpose(reels);


printRows(rows);
















—------------

Checking if the user won

const prompt = require("prompt-sync")();


const ROWS=3;
const COLS=3;


const SYMBOLS_COUNT={
    "A":2,
    "B":4,
    "C":6,
    "D":8
}


const SYMBOLS_VALUES={
    "A":5,
    "B":4,
    "C":3,
    "D":2
}






const deposit = () => {
    while(true){
    const depositAmount = prompt("Enter a deposit amount : ");
    const numberDepositAmount = parseFloat(depositAmount);


    if(isNaN(numberDepositAmount) || numberDepositAmount <= 0) {
        console.log("Invalid deposit amount, try again.")
    } else {
        return numberDepositAmount;
    }
}
};


const getNumberOfLines = () => {
    while(true){
        const lines=prompt("Enter number of lines from 1 to 3 : ");
        const numberOfLines=parseFloat(lines);


        if (isNaN(numberOfLines) || numberOfLines <= 0 || numberOfLines > 3) {
            console.log("Invalid number of lines, try again.");
        } else {
            return numberOfLines;
        }
        }
    };




const getbet = (balance, lines) => {
    while(true){
    const bet = prompt("Enter the total bet per line : ");
    const numberBet = parseFloat(bet);


    if(isNaN(numberBet) || numberBet <= 0 || numberBet > (balance/lines)){
        console.log("Invalid bet, try again.");
    }else{
        return numberBet;
    }
}
}


const spin = () => {
    const symbols=[];
    for(const[symbol, count] of Object.entries(SYMBOLS_COUNT)){
        //console.log(symbol,count);
        for(let i=0; i<count; i++)
        {
            symbols.push(symbol);
        }
    }
    //console.log(symbols);


    const reels=[];
    for (let i=0; i < COLS; i++) {
        reels.push([]);
        const reelSymbols = [...symbols];
        for (let j = 0; j < ROWS; j++){
            const randomIndex = Math.floor(Math.random() * reelSymbols.length);
            const selectedSymbol = reelSymbols[randomIndex];
            reels[i].push(selectedSymbol);
            reelSymbols.splice(randomIndex,1);
        }
    }


    return reels;


};


const transpose = (reels) => {
    const rows = [];


    for (let i = 0; i < ROWS; i++) {
        rows.push([]);
        for (let j = 0; j < COLS; j++) {
            rows[i].push(reels[j][i]);
        }
    }
    return rows;
};


const printRows= (rows) => {
    for(const row of rows) {
        //let rowString = " A | B | C ";
        let rowString = "";
        for (const [i, symbol] of row.entries()) {
            rowString += symbol
            if (i != row.length -1 ) {
                rowString += " | "
            }
           
        }
        console.log(rowString)
    }
}


const getWinnings = (rows, bet, lines) => {
    let winnings=0;


    for(let row=0; row < lines ; row++) {
        const symbols=rows[row];
        let allSame = true;


        for (const symbol of symbols) {
            if (symbol != symbols[0]) {
                allSame = false;
                break;
            }
        }


        if (allSame) {
            winnings += bet * SYMBOLS_VALUES[symbols[0]]
        }
    }
    return winnings;
}




//const depositAmount=deposit();
let balance=deposit();
const numberOfLines=getNumberOfLines();
const bet = getbet(balance,numberOfLines);
const reels = spin();
const rows=transpose(reels);


printRows(rows);
const winnings = getWinnings(rows, bet, numberOfLines)
//check bet -- if bet is total bet its not what we want, we want bet per line


console.log("You won, $" + winnings.toString())

















—--------------------------------------------------------

Give the user their winnings

const prompt = require("prompt-sync")();


const ROWS=3;
const COLS=3;


const SYMBOLS_COUNT={
    "A":2,
    "B":4,
    "C":6,
    "D":8
}


const SYMBOLS_VALUES={
    "A":5,
    "B":4,
    "C":3,
    "D":2
}






const deposit = () => {
    while(true){
    const depositAmount = prompt("Enter a deposit amount : ");
    const numberDepositAmount = parseFloat(depositAmount);


    if(isNaN(numberDepositAmount) || numberDepositAmount <= 0) {
        console.log("Invalid deposit amount, try again.")
    } else {
        return numberDepositAmount;
    }
}
};


const getNumberOfLines = () => {
    while(true){
        const lines=prompt("Enter number of lines from 1 to 3 : ");
        const numberOfLines=parseFloat(lines);


        if (isNaN(numberOfLines) || numberOfLines <= 0 || numberOfLines > 3) {
            console.log("Invalid number of lines, try again.");
        } else {
            return numberOfLines;
        }
        }
    };




const getbet = (balance, lines) => {
    while(true){
    const bet = prompt("Enter the total bet per line : ");
    const numberBet = parseFloat(bet);


    if(isNaN(numberBet) || numberBet <= 0 || numberBet > (balance/lines)){
        console.log("Invalid bet, try again.");
    }else{
        return numberBet;
    }
}
}


const spin = () => {
    const symbols=[];
    for(const[symbol, count] of Object.entries(SYMBOLS_COUNT)){
        //console.log(symbol,count);
        for(let i=0; i<count; i++)
        {
            symbols.push(symbol);
        }
    }
    //console.log(symbols);


    const reels=[];
    for (let i=0; i < COLS; i++) {
        reels.push([]);
        const reelSymbols = [...symbols];
        for (let j = 0; j < ROWS; j++){
            const randomIndex = Math.floor(Math.random() * reelSymbols.length);
            const selectedSymbol = reelSymbols[randomIndex];
            reels[i].push(selectedSymbol);
            reelSymbols.splice(randomIndex,1);
        }
    }


    return reels;


};


const transpose = (reels) => {
    const rows = [];


    for (let i = 0; i < ROWS; i++) {
        rows.push([]);
        for (let j = 0; j < COLS; j++) {
            rows[i].push(reels[j][i]);
        }
    }
    return rows;
};


const printRows= (rows) => {
    for(const row of rows) {
        //let rowString = " A | B | C ";
        let rowString = "";
        for (const [i, symbol] of row.entries()) {
            rowString += symbol
            if (i != row.length -1 ) {
                rowString += " | "
            }
           
        }
        console.log(rowString)
    }
}


const getWinnings = (rows, bet, lines) => {
    let winnings=0;


    for(let row=0; row < lines ; row++) {
        const symbols=rows[row];
        let allSame = true;


        for (const symbol of symbols) {
            if (symbol != symbols[0]) {
                allSame = false;
                break;
            }
        }


        if (allSame) {
            winnings += bet * SYMBOLS_VALUES[symbols[0]]
        }
    }
    return winnings;
}




const game = () => {


    //const depositAmount=deposit();
 let balance=deposit();


 while(true){


    console.log("You have balance of $" + balance);


    const numberOfLines=getNumberOfLines();
    const bet = getbet(balance,numberOfLines);


     balance -= bet * numberOfLines;


     const reels = spin();
     const rows=transpose(reels);


    printRows(rows);
    const winnings = getWinnings(rows, bet, numberOfLines)
    balance += winnings;
    //check bet -- if bet is total bet its not what we want, we want bet per line


    console.log("You won, $" + winnings.toString())


    if (balance <= 0) {
    console.log("You ran out of money...!");
    break;
 }
  const playAgain = prompt("Do you want to play again? (y/n) ")


  if (playAgain != "y") break;

 }
};


game();
