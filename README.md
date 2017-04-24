# include <iostream>
# include <fstream>
# include <algorithm>
# include <string>
using namespace std;

int value(string str)
{
  int res = 0;
  for (int i = 0; i < str.length(); i++)
  {
      res += str [i] - 'A' + 1;
   }
   return res;
 }

int main()
{
  ifstream file;
  file.open ("names.txt");
  
  string names[];
  int size = 0;
  while (!file.eof()) {
    file >> names [size++];
  }
  
  sort (names, names + size);
  int res = 0;
  for (int x = 0; x < size; x++)
  { 
    res+= value (names [x]);
  }
  cout << res << endl; 
  file.close ();
}
