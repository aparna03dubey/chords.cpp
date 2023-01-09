# chords.cpp
Codeforces 88a
```
#include<bits/stdc++.h>
using namespace std;
string notes[] = { "C", "C#", "D", "D#", "E", "F", "F#", "G", "G#", "A", "B", "H" };
int ind(string s){
    for(int i=0;i<12;i++){
        if(notes[i]==s){
            return i;
            break;
        }
        // return 0;
    }
}
string check(int x,int y,int z){
    int first,second;
    if(x>y){
        first=y+12-x;

    }
    else{
        first=y-x;
    }
    if(y>z){
        second=z+12-y;
    }
    else{
        second=z-y;
    }
    if(first==4&&second==3){
        return "major";
    }
    else if(second==4&&first==3){
        return "minor";
    }
    else{
        return "strange";
    }
}
int main(){
string s1,s2,s3;
cin>>s1>>s2>>s3;
int a=ind(s1);
int b=ind(s2);
int c=ind(s3);
// cout<<a<<" "<<b<<" "<<c<<endl;
string s[6];
int flag=0;
s[0]=check(a,b,c);
s[1]=check(c,a,b);
s[2]=check(b,c,a);
s[3]=check(b,a,c);
s[4]=check(c,b,a);
s[5]=check(a,c,b);
for(int i=0;i<6;i++){
    // cout<<s[i]<<endl;
    if(s[i]=="major"||s[i]=="minor"){
        cout<<s[i]<<endl;
        flag=0;
        break;
    }
    else{
        flag=1;
    }
}
if(flag==1){
    cout<<"strange";
}
return 0;
}
```
