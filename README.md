## EXP-12

## Aim:
To study and implement Constructors and Destructors.

## Theory:
A constructor in C++ is a special member function whose name matches exactly with the class name. It is primarily used to initialize the variables of a class when an object is created. Constructors do not have a return type, not even void, and are automatically invoked when an object is instantiated. While constructors are typically defined in the public section of a class to allow easy creation of objects, they can also be declared in the private or protected sections if restricted access is desired. Constructors can be overloaded to allow multiple ways of initializing an object, but they cannot be declared as virtual functions. The syntax for a constructor is straightforward: it is defined with the class name followed by parentheses that may include parameters. A constructor can be defined either inside the class definition, like ClassName(parameters) { // implementation }, or outside the class definition using the scope resolution operator, like ClassName::ClassName(parameters) { // implementation }.

## Defining the constructor inside the class:
~~~
//Name: Saaj Mulik
//Prn: 23070123109
//Class: EnTC B-2
#include<iostream>
using namespace std;

class student
{
    int rollno;
    char name[50];
    double fee;
public:
    student()
    {
        cout << "Enter the RollNo: ";
        cin >> rollno;
        cin.ignore();
        cout << "Enter the Name: ";
        cin.getline(name, 50);
        cout << "Enter the Fee: "; 
        cin >> fee;
    }
    void display()
    {
        cout << endl << rollno << "\t" << name << "\t" << fee;
    }
};
int main()
{
    student s; 
    s.display();
    return 0;
}
~~~

## Output:

<img width="637" alt="image" src="https://github.com/user-attachments/assets/7b3d316f-5747-4f13-ae38-5b778bd8308b">

## Defining the constructor outside the class:
~~~
//Name: Saaj Mulik
//Prn: 23070123109
//Class: EnTC B-2
#include<iostream>
using namespace std;

class student
{
    int rno;
    char name[50];
    double fee;

public:
    student();
    void display();
};
student::student()
{
    cout << "Enter the RollNo: ";
    cin >> rno;
    cout << "Enter the Name: ";
    cin >> name;
    cout << "Enter the Fee: ";
    cin >> fee;
}
void student::display()
{
    cout << endl << rno << "\t" << name << "\t" << fee;
}
int main()
{
    student s;
    s.display();
    return 0;
}
~~~

## Output:

<img width="632" alt="image" src="https://github.com/user-attachments/assets/d5d84caf-63d6-4674-a509-6de01b884d82">

## Default constructor:
~~~
//Name: Saaj Mulik
//Prn: 23070123109
//Class: EnTC B-2
#include<iostream>
#include<string>
using namespace std;

class Data {
    string name;
    int roll_no;
    char dept[50];
    int batch;

public:
    Data() {
        cout << "Name: ";
        cin >> name;
        cout << "Roll Number: ";
        cin >> roll_no;
        cout << "Department: ";
        cin >> dept;
        cout << "Batch: ";
        cin >> batch;
    }
    void display() {
        cout << endl << "DETAILS:" << endl << name << " " << roll_no << " " << dept << " " << batch << endl;
    }
};
int main() {
    Data d1;
    d1.display();
}
~~~

## Output:

<img width="641" alt="image" src="https://github.com/user-attachments/assets/920c4d22-3df4-45fa-b9cc-90305894322a">

## Parameterized constructor:
~~~
//Name: Saaj Mulik
//Prn: 23070123109
//Class: EnTC B-2
#include<iostream>
using namespace std;
class Num
{
    public:
    Num(int c, int d)
    {
        if(c>d)
        {
            cout<<c<<" is greater";
        }
        else
        {
            cout<<d<<" is greater";
        }
    }
};
int main()
{
Num n1(4,3);
}
~~~

## Output:

<img width="431" alt="image" src="https://github.com/user-attachments/assets/cb2f69b4-6828-4fd7-91d4-ed04dba9e668">

## Copy constructor:
~~~
//Name: Saaj Mulik
//Prn: 23070123109
//Class: EnTC B-2
#include<iostream>
#include<string.h>
using namespace std;

class student {
    int rno;
    char name[50];
    double fee;
public:
    student(int no, const char n[], double f);
    student(const student &t);

    void display();
};
student::student(int no, const char n[], double f) {
    rno = no;
    strcpy(name, n);
    fee = f;
}
student::student(const student &t) {
    rno = t.rno;
    strcpy(name, t.name);
    fee = t.fee;
}
void student::display() {
    cout << endl << rno << "\t" << name << "\t" << fee;
}
int main() {
    student s(1001, "Manjeet", 10000);
    s.display();
    student manjeet(s);
    manjeet.display();
    return 0;
}
~~~

## Output:

<img width="415" alt="image" src="https://github.com/user-attachments/assets/4341e07c-74de-420e-a52f-6be59b12676d">

## Destructors:
~~~
//Name: Saaj Mulik
//Prn: 23070123109
//Class: EnTC B-2
#include<iostream>
using namespace std;
int count=0;
class destruct
{
    public:
    destruct()
    {
        count++;
        cout<<"No. of objects created: "<<count<<endl;
    }
    ~destruct()
    {
        count--;
        cout<<"No. of objects destroyed: "<<count<<endl;
    }
};
int main()
{
destruct aa,bb,cc;
{ 
    destruct dd;
}
return 0;
}
~~~

## Output:

![image](https://github.com/user-attachments/assets/690716fa-845c-48a8-b2a1-ca35de6d57a8)

## Conclusion:
In summary, constructors in C++ are essential for initializing objects and ensuring that they start in a valid state. With their automatic invocation upon object creation, lack of a return type, and support for overloading, constructors provide flexibility in object initialization. While typically defined in the public section of a class, they can also be made private or protected to control object creation. Understanding how to effectively define and utilize constructors is fundamental for robust and efficient C++ programming.
