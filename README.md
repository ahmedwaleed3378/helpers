#include <iostream>
using namespace std;
class c {
protected:
    int width ;
    int height ;
public :
    void set_values (int a ,int b )
    {
        width = a ;
        height=b;
    }
    virtual int area ()=0;};
class temp : public c{
public:
    int area (){return (width*height );}
};
class mem : public c{
public:
    int area (){return ((width*height)/2 );}
};
int main()
{
    c *pt2,*pt3;
    temp pr2;
    mem pr3;
    pt2=&pr2;
    pt3=&pr3;
    pt2->set_values(5,10);
    pt3->set_values(5,10);
    cout<< pt2->area();cout<< endl;
    cout<< pt3->area();
    c *pt[2]={&temp,&mem};
    for (int u=0; u>2;u++)
    {
        pt[u]->set_values(5,5);
        cout <<pt[u]->area();
        cout<< endl;
    }
 cout<< endl;
 }
