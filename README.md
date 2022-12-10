# c20#include<iostream.h>

#include<conio.h>

#include<stdlib.h>

class student

{

	char name;

	int age;

	public:

	student()

	{

		cout<<"\nConstructor is called...";

	}

	student(char name,int age)

	{

		this->name=name;

		this->age=age;

	}

	void display()

	{

		cout<<"\nName :"<<name;

		cout<<"\nAge :"<<age;

	}

	void * operator new(size_t size)

	{

		cout<<"\nOverloading new operator with size..."<<size;

		void *p=::operator new(size);

		return p;

	}

	void operator delete(void *p)

	{

		cout<<"\nOverloading Delete Operator...";

		free(p);

	}

};

int main()

{

	clrscr();

	student *p=new student('D',20);

	p->display();

	delete p;

	getch();

	return 0;

}
