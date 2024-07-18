# CParseCSS

CParseCSS is a C++ library dedicated to parsing CSS content. This library allows you to extract CSS selectors, declaration names, and values from CSS strings.

## Installation

To use this library, include the `cparsecss.hpp` header file in your project.

## Usage

Here is an example of how to use the `CParseCSS` class to parse CSS content and extract data:

```cpp
#include <iostream>
#include "cparsecss.hpp"
#include <string>

using namespace std;

int main() {
    string css = R"(
        h1 {
            color: white;
            text-align: center;
        }

        p {
            font-family: verdana;
            font-size: 20px;
        }

        b2 {
            font-family: verdana;
            font-size: 20px;
        }
    )";

    CParseCSS p;
    p.parse(css);
    typeListData data = p.getData();

    cout << "Selector" << " Name" << " Value" << endl;
    cout << "----------------------------------" << endl;
    for (size_t i = 0; i < data.size(); i++) {
        cout << data.at(i).selector << " " << data.at(i).name << " " << data.at(i).value << endl;
    }
}

Selector Name Value
----------------------------------
h1 color white
h1 text-align center
p font-family verdana
p font-size 20px
b2 font-family verdana
b2 font-size 20px
