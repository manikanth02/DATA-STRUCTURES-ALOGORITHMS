# This Problem is all about to find longest palindrome in a substring

[LONGEST PALINDROME IN A STRING](https://www.geeksforgeeks.org/problems/longest-palindrome-in-a-string3411/1?utm_source=geeksforgeeks&utm_medium=ml_article_practice_tab&utm_campaign=article_practice_tab)

## BRUTE-FORCE-APPROACH

1.GENRATE ALL SUBSTRING USING RECURSIONS

2.FOR EACH SUBSTRINGS WE CHECK IS IT PALINDROME

** WE DON'T USE CONCEPT OF BACKTRACKING BECAUES IT MAY BE POSSIBLE THAT CURRENTLY THIS SUBSTRING IS NOT PALINDROME BUT AFTER SOME TIME IT BECOME PALINDROME **


```
bool isPalindrome(string s){
      int i = 0, j = s.size() - 1;
      while(i <j){
          if(s[i++] != s[j--]){
              return false;
          }
      }
      return true;
  }
  
    void generate(string s,string curr,int i,string& palindrome){
    if(i == s.size()){
        return;
    }
    if(isPalindrome(curr)){
        if(curr.size() > palindrome.size()){
            palindrome = curr;
        }
    }
    generate(s,curr + s[i+1],i+1,palindrome);
    }
    
    string longestPalin (string S) {
        // code here
        string longPalind = "";
        for(int i = 0; i <= S.size() - 1; i++){
        string str = S.substr(i, 1);
        string palindrome = "";
        generate(S,str,i,palindrome);
        if(palindrome.size() > longPalind.size()){
            longPalind = palindrome;
        }
        }
        return longPalind;
    }
```
