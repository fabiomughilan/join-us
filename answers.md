## About You.

1. Introduce yourself.
   
This is Fabio Mughilan, I am doing my final year in B.Tech CSE at Vel Tech University,Chennai, and have 1+ year experience in building Dapps and 

2. Do you own a personal computer?
   
Yes, I have a personal laptop

3. Describe your development environment.

Windows 11, VS Code, Cursor, Replit

## Social Profile

Stack Overflow: https://stackoverflow.com/users/29971569/fabio-mughilan
   
2. Personal website, blog or something you want us to see.

Github: https://github.com/fabiomughilan
Linkedin: https://www.linkedin.com/in/fabiomughilan
Website: 

## The real stuff.
1. Which all programming languages are installed on your system.

Solidity, Javascript, Typescipt, Python, Rust, C, Java
   
2. Write a function that takes a number and returns a list of its digits in an array.

const numToarray = (num) => {
    if (typeof num !== "number" || isNaN(num)) return []; //prevent Nan value
    num = Math.abs(num); // remove -ve value
    if (!Number.isInteger(num)) return []; // Remove decimal point 
    return num.toString().split("").map(Number);
}
console.log(numToarray(12345));


3. Remove duplicates of an array and returning an array of only unique elements

const removDup = (arr) => {
return Array.isArray(arr) ? [...new Set(arr)] : [];
};

console.log(removDup([1, 2, 1, 2, 3, 4]));

4. Write function that translates a text to Pig Latin and back. English is translated to Pig Latin by taking the first letter of every word, moving it to the end of the word and adding ‘ay’. “The quick brown fox” becomes “Hetay uickqay rownbay oxfay”.

// Convert English to Pig Latin
const toPigLat = (text) => {
  return text
    .split(" ")
    .map(word => word.slice(1) + word[0] + "ay")
    .join(" ");
};

// Convert Pig Latin back to English
const fromPigLat = (text) => {
  return text
    .split(" ")
    .map(word => {
      const withoutAy = word.slice(0, -2); // remove 'ay'
      return withoutAy.slice(-1) + withoutAy.slice(0, -1);
    })
    .join(" ");
};

toPigLat("The quick brown fox");
// → "hetay uickqay rownbay oxfay"

fromPigLat("hetay uickqay rownbay oxfay");
// → "the quick brown fox"

5. Write a function that rotates a list by `k` elements. For example [1,2,3,4,5,6] rotated by `2` becomes [3,4,5,6,1,2]. Try solving this without creating a copy of the list. How many swap or move operations do you need?

const rotateInPlace = (arr, k) => {
  const n = arr.length;
  if (!Array.isArray(arr) || n === 0 || k % n === 0) return;

  k = k % n; // handle k > n

  const reverse = (start, end) => {
    while (start < end) {
      [arr[start], arr[end]] = [arr[end], arr[start]]; // swap
      start++;
      end--;
    }
  };

  reverse(0, k - 1);     // Reverse first part
  reverse(k, n - 1);     // Reverse second part
  reverse(0, n - 1);     // Reverse whole array
};


