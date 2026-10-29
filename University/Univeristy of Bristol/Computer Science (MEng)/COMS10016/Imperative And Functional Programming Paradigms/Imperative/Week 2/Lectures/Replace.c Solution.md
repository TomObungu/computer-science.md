The question asked us to write a tiny program called replace.c that requires two strings as command line arguments and then prints  a string where all occurrences of the second string in the first string are iteratively replaced left-to-right all overlaps are ignored. 

The bit that confused me was what it meant by ignoring overlaps with the original first string itself. I didn't understand what it meant by ignoring overlaps - that is, what did it want us to replace the occurrences of the inner word with? 

Looking at the solution code, I realised that the code literally finds the position of each occurrence of the inner word and then replace the rest of the string with the original string from that position of the occurence of the inner word. 

```C
if(checkForInnerword(word,innerWord,wordCounter)){
            // Adds the replaced word at the position of the old inner word
            for(int j=0; j<strlen(word);j++){
                replacedString[i+j]=word[j];
            }
            // Increases the counter for both the replaced word and the word letter position to account for replaced word. 
            i+=strlen(word)-1;
```

The code then repeats the check for finding the inner words and replacing it with the string 