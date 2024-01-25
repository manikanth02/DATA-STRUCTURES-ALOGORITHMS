###
https://www.geeksforgeeks.org/problems/recursively-remove-all-adjacent-duplicates0744/1?utm_source=geeksforgeeks&utm_medium=ml_article_practice_tab&utm_campaign=article_practice_tab


string rremove(string s){
        // code here
        int size = s.size();
        string subStr = "";
        for(int i = 0; i <= size - 1; i++){
            if(i == 0){
                if(s[i] != s[i + 1]){
                    subStr += s[i];
                }
            }else if(i == size - 1){
                 if(s[i] != s[i - 1]){
                    subStr += s[i];
                }
            }else if(s[i] != s[i + 1] && s[i] != s[i - 1]){
                subStr += s[i];
            }
        }
        if(s.size() == subStr.size()){
            return s;
        }
        return rremove(subStr);
    }
