#Question 1
# arraysum
#include <iostream>
using namespace std;
int main ()
{
   int arr[] = {15, 4, 23, 9, 3, 18, 8, 44, 10, 1};
   int n = 10, sum = 0;
   for (int i = 0; i < n ; i++)
   {
      sum+=arr[i];
   }
                      
   cout<< "The array sum is " <<sum;                            
   return 0;
}

                                   
#Question 2  BATTLESHIP
#include <iostream>
#include <ctime>
using namespace std;

const int rows = 10;
const int columns = 10;
 
int amount_ships = 10;
 
int matrix[rows][columns];
 
void clear()
{
    for(int a=0; a < rows; a++)
    {
        for(int b=0; b < columns; b++)
        {
            matrix[a][b] = 0;
        }
    }
}
 
void show()
{
    for(int a=0; a < rows; a++)
    {
        for(int b=0; b < columns; b++)
        {
            cout << matrix[a][b] << " ";
        }
        cout << endl;
    }
}
 
int num_ships()
{
    int c = 0;
 
    for(int a=0; a < rows; a++)
    {
        for(int b=0; b < columns; b++)
        {
            if(matrix[a][b] == 1)
                c++;
        }
    }
 
    return c;
}
 
void setships()
{
    int s = 0;
    while(s < amount_ships)
    {
        int x = rand() % rows;
        int y = rand() % columns;
        if(matrix[x][y] != 1)
        {
            s++;
            matrix[x][y] = 1;
        }
    }
}
 
bool attack(int x,int y)
{
    if(matrix[x][y] == 1)
    {
        matrix[x][y] = 2;
        return true;
    }
    return false;
}
 
int main()
{
    srand(time(NULL));
    clear();
    setships();
    int position1,position2;
    char suggest;
    while(1)
    {
        cout << "Select location from a 10 x 10 Battleship grid (numbers 1-10 only with space between the two numbers): "; cin >> position1 >> position2;
        if(attack(position1,position2))
            cout << "HIT!" << endl;
        else
            cout << "MISS! Try Again" << endl;
        cout << "Number of ships left: " << num_ships() << endl;
        cout << "Do you want to surrender (y/n)? "; cin >> suggest;
        if(suggest == 'y')
            break;
    }
    cout << "Game Over thanks for playing!" << endl;
    show();
    system("pause");
    return 0;
}                                  
