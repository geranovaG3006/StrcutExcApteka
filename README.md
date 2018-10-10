# StrcutExcApteka
Да се напише програма, която създава структура Apteka с полета name, mg, number, и price, указващи наименованието, милиграмите, количеството опаковки и цена на лекарствта. Да се въведе цяло число n и след него n на брой данни за лекарствени препарати.А)Да се изведе списък на лекарствата сортирани по цена.

#include<iostream>
#include<cstring>
#include <iomanip>
using namespace std;
struct Apteka
{
    string name;
    float mg;
    int number;
    double price;
};
int main()
{
    int n;
    Apteka temp;
    cout<<"Number of medicines: ";
    cin>>n;
    Apteka medicine[n];
    for(int i=0;i<n;i++)
    {
        cout<<"*****Medicine*****"<<i+1<<endl;
        cout<<"Name: ";
        cin.get();
        cin>>medicine[i].name;
        cout<<"Mg: ";
        cin.get();
        cin>>medicine[i].mg;
        cout<<"Number: ";
        cin>>medicine[i].number;
        cout<<"Price: ";
        cin>>medicine[i].price;
    }
    cout<<"Medicines sorted by price: "<<endl;
    for(int i=0;i<n-1;i++)
    {
        for(int j=i+1;j<n;j++)
        {
            if(medicine[i].price>medicine[j].price)
            {
                temp=medicine[i];
                medicine[i]=medicine[j];
                medicine[j]=temp;
            }
        }
    }
    for(int i=0;i<n;i++)
    {
        cout<<"*****Medicine "<<i+1<<"*****"<<endl;
        cout<<"Name: "<<medicine[i].name<<endl;
        cout<<"Mg: "<<medicine[i].mg<<endl;
        cout<<"Number : "<<medicine[i].number<<endl;
        cout<<"Price: "<<medicine[i].price<<endl;
    }
    
    system("pause");
    return 0;
}
