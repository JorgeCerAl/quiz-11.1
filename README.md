# quiz-11.1



/*
 *  #Quiz
 *  Created by George.16 on 4/23/15.
 *  Copyright (c) 2015 George.16. All rights reserved.
 *  Main: Read text files from C++
 *  #TC1017
 *  Referencia: Cplusplus.com,. (2015). Input/output with files - C++ Tutorials. Retrieved 28 April 2015, from http://www.cplusplus.com/doc/tutorial/files/
    Cplusplus.com,. (2015). tolower - C++ Reference. Retrieved 28 April 2015, from http://www.cplusplus.com/reference/locale/tolower/
 */
#include <iostream>
#include <unistd.h>
#include <string>
#include <fstream> // permite que un programa lea un textfile
#include <locale>         // std::locale, std::tolower


using namespace std;

int Bananas(){
    int Banana = 0, lol = 0;
    string line, x;
    locale loc;
    ifstream myfile ("Banana.txt");
    
    while ( getline (myfile,line) )
    {
        
        cout << line << endl;
        
        for (std::string::size_type i=0; i<line.length(); ++i){
            x = tolower(line[i],loc);
            if(x == "b" || x == "a" || x == "n"){
                
                lol = lol + 1;
            }
            else{
                
                lol = 100;
                
            }
            
            
            
        }
        if(lol == 6){
            
            Banana = Banana + 1;
        }
        lol = 0;
        
        
    }
    myfile.close();

    return Banana;
}

int main(){
    int Banana = 0, lol = 0;
    string line, x;
    locale loc;
    ifstream myfile ("Banana.txt");
    if (myfile.is_open())
    {
       Banana = Bananas();
       cout << "Hay " << Banana << " Bananas"<< endl;

            }
    
    else cout << "Unable to open file";
    
    
    
    return 0;
}
