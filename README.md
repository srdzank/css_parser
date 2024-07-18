# CSS Header only parser
## C++

#include <iostream>
#include "cparsecss.hpp"
#include <string>

using namespace std;

int main()
{

    string css = R"(
                h1
                {
                color:white;
                text-align:center;
                }

                p{ 
                font-family: verdana; 
                font-size: 20px; 
                } 
         
                b2{ 
                font-family: verdana; 
                font-size: 20px; 
                } 

            )";

    CParseCSS p;
    p.parse(css);
    typeListData data = p.getData();
    
    cout << "Selector" << " " << "Name" << " " << "Value" << endl;
    cout << "----------------------------------" << endl;
    for (size_t i = 0; i < data.size(); i++) {

        cout << data.at(i).selector << " " << data.at(i).name << " " << data.at(i).value << endl;
    }
}

/////////////////  result /////////////////////////////////////////////////////////
                                                                                                
Selector Name Value
----------------------------------
h1 color white
h1 text-align center
p font-family verdana
p font-size 20px
b2 font-family verdana
b2 font-size 20px
                                         
                                    
