#DSA 

[[_Problem solving fundas.pdf]]

- Site used for code execution : https://www.onlinegdb.com/ | use c++17
- Beware about which language and version you use be clear with it
- Boiler plate 
```cpp
#include<bits/c++.h>
using namespace std;

signed main(){

}
```

### Strings
-------------
##### getline(cin,s);
		fro it into s till enter is hit. so if the input is of 2 line , that is '/n' or any delimiter is there , the input ends at that point. Single line consider after that everything flush offed.
		

#####  Usecase 2 : if you want to add n-> number to a string number ?
```cpp
#include<bits/c++.h>
using namespace std;
signed main(){
	string s ;
	cin>>s; 
	//code start
		int val = stoi(s);
		cout<<val+7; // add 7 to string and print
		
		//Converting back to string
		s = to_string(val+7);
	
		// if input is more than int 183374983072340970
		//stoi -> runtime error caused
		long long val = stoll(s);
		s = to_string(val+7);
}
```


##### Usecase 3 :  Trick for conversion  datetype 1 -> datatype 2 
#Trick 
```cpp
#include <iostream>

int main()
{
    //Conversion 1
    int s ;
    cin>>s;
    long long x;
    
    //Conversion 2 
    string s ;
    cin>>s;
    int x;

> Regardless of any data type , int -> string , string -> int , int --> long long We can just convert source data into stringstream , and assign that to destination data 
> stringstream<<Data1
> strinfstream<<Data2 
> cin and cout are also streams.

    stringstream temp;
    temp<<s;
    temp>>x;
    

    return 0;
}
```


### Fast IO
#Trick #performance 

 #### Why '/n' is fast but endl is slow?
 ```cpp
	 #include <iostream>
	 using namespace std;
	 #define endl '\n'
	 
> put return type of main as signed as long long not support
	 #define int long long 
	 signed main(){
		ios_base::sync_with_stdio(0);
		 cin.tie(0); cout.tie(0);	
	}
	 
	```
 	  
![[Pasted image 20241216072201.jpg]]

