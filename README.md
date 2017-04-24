# include <iostream>
# include <fstream>
# include <algorithm>
# include <string>
using namespace std;

int main()
{
  ifstream file;
  file.open ("names.txt");
  
  string names;
  int size = 0;
  while (!file.eof()) {
    file >> names [size++];
  }
  
  sort (names, names + size);
  
  file.close ();
  
