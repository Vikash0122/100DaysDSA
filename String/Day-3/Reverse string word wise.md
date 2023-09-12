# Reverse string word wise
[Code Studio](https://parikh.club/parikh_strings_1)

~~~

// fails if string space at end
int n=s.size();
    int i=0; 
    string ans="";
    while(i<n){
        string temp="";

        while(i<n && s[i]==' '){
            i++;
        }

        while(i<n && s[i] != ' '){
            temp+=s[i];
            i++;
        }

        if(temp.size()==0){
            ans=temp;
        }else{
            ans=temp+' '+ans;
        }
    }
    return ans;

~~~

~~~
// works for all
string reverseWords(string s) {
        // 2 pointer approach
        string ans = "";
        int start;
        for(int end=s.size()-1; end>=0;){
            while(end >= 0 and s[end] == ' '){
                end--;
            }
            start = end;
            while(start >= 0 and s[start] != ' '){
                start--;
            }
            if(start == end) break;

            if(!ans.empty()) ans += " ";

            ans += s.substr(start+1, end - start);
            
            end = start;
        }
        return ans;
    }

~~~
