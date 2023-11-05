# javaNjavascriptQ

**1. JAVA **

A. Create an array with the values (1, 2, 3, 4, 5, 6, 7) and shuffle it. 

        
        Integer[] originalArray = {1, 2, 3, 4, 5, 6, 7};

         
        List<Integer> list = Arrays.asList(originalArray);

        
        Collections.shuffle(list);

         
        Integer[] shuffledArray = list.toArray(new Integer[0]);

        
        System.out.println(Arrays.toString(shuffledArray));
    


B. Enter a Roman Number as input and convert it to an integer. (ex IX = 9) .

public class RomanToInteger {
    public static int romanToInt(String s) {
        int result = 0;
        int prevValue = 0;

        for (int i = s.length() - 1; i >= 0; i--) {
            char currentChar = s.charAt(i);
            int currentValue = getValue(currentChar);

            if (currentValue < prevValue) {
                result -= currentValue;
            } else {
                result += currentValue;
            }

            prevValue = currentValue;
        }

        return result;
    }

    public static int getValue(char c) {
        switch (c) {
            case 'I':
                return 1;
            case 'V':
                return 5;
            case 'X':
                return 10;
            case 'L':
                return 50;
            case 'C':
                return 100;
            case 'D':
                return 500;
            case 'M':
                return 1000;
            default:
                return 0; // Handling invalid characters, you can modify this behavior if needed.
        }
    }

    public static void main(String[] args) {
        String romanNumeral = "IX"; // Change this to the Roman numeral you want to convert
        int integerEquivalent = romanToInt(romanNumeral);
        System.out.println("The integer equivalent of " + romanNumeral + " is: " + integerEquivalent);
    }
}


C. Check if the input is pangram or not. (Pangram is a sentence that contains all the alphabet
from a-z) .

public class PangramChecker {
    public static boolean isPangram(String sentence) {
        // Create a boolean array to mark the presence of each character from 'a' to 'z'
        boolean[] charPresent = new boolean[26];

        // Convert the sentence to lowercase to handle both uppercase and lowercase letters
        sentence = sentence.toLowerCase();

        // Iterate through the sentence and mark the characters as present
        for (int i = 0; i < sentence.length(); i++) {
            char c = sentence.charAt(i);
            if (c >= 'a' && c <= 'z') {
                charPresent[c - 'a'] = true;
            }
        }

        // Check if all characters from 'a' to 'z' are marked as present
        for (boolean present : charPresent) {
            if (!present) {
                return false; // If any character is missing, it's not a pangram
            }
        }

        return true; // All characters are present, it's a pangram
    }

    public static void main(String[] args) {
        String input = "The quick brown fox jumps over the lazy dog"; // Change this to the input sentence you want to check
        boolean isPangram = isPangram(input);

        if (isPangram) {
            System.out.println("The input is a pangram.");
        } else {
            System.out.println("The input is not a pangram.");
        }
    }
}



**2 JavaScript **

A. Take a sentence as an input and reverse every word in that sentence. 
a. Example - This is a sunny day > shiT si a ynnus yad.

function reverseWordsInSentence(sentence) {
    let reversedSentence = '';
    let word = '';

    for (let i = 0; i < sentence.length; i++) {
        if (sentence[i] === ' ') {
            // If a space is encountered, reverse and append the word to the reversed sentence
            for (let j = word.length - 1; j >= 0; j--) {
                reversedSentence += word[j];
            }
            reversedSentence += ' ';
            word = ''; // Reset the word
        } else {
            word += sentence[i]; // Build the word character by character
        }
    }

    // Reverse and append the last word
    for (let j = word.length - 1; j >= 0; j--) {
        reversedSentence += word[j];
    }

    return reversedSentence;
}

// Example usage:
const input = "Hello World"; // Change this to the input sentence you want to reverse
const reversedSentence = reverseWordsInSentence(input);
console.log("Reversed Sentence: " + reversedSentence);


B. Perform sorting of an array in descending order.

function bubbleSortDescending(arr) {
    const n = arr.length;
    let swapped;

    do {
        swapped = false;
        for (let i = 0; i < n - 1; i++) {
            if (arr[i] < arr[i + 1]) {
                // Swap the elements if they are out of order
                const temp = arr[i];
                arr[i] = arr[i + 1];
                arr[i + 1] = temp;
                swapped = true;
            }
        }
    } while (swapped);

    return arr;
}

// Example usage:
const originalArray = [5, 2, 9, 1, 5, 6];
const sortedArray = bubbleSortDescending(originalArray);
console.log("Sorted Array in Descending Order:", sortedArray);


 
 
