# c-LX2
// 1.cpp : 定义控制台应用程序的入口点。
//

#include "stdafx.h"
#include "iostream"
using namespace std;

class CEnglen
{
public:
	CEnglen();
	void display();
	void setlen(int f, int i);
	CEnglen operator +(CEnglen o);
private:
	int feet;
	int inch;
};
CEnglen::CEnglen()
{
	feet = 0;
	inch = 0;
}
void CEnglen::display()
{
	cout << "feet=" << feet << " inch=" << inch << endl;
}
void CEnglen::setlen(int f, int i)
{
	feet = f;
	inch = i;
}
CEnglen CEnglen::operator+(CEnglen o)
{
	CEnglen t;
	t.setlen(feet + o.feet, inch + o.inch);
	if (t.inch >= 12)
	{
		t.feet++;
		t.inch = t.inch - 12;
	}
	return t;
}
int main()
{
	CEnglen oe1, oe2, oe3;
	oe1.setlen(1, 7);
	oe1.display();
	oe2.setlen(3, 9);
	oe2.display();
	oe3 = oe1 + oe2;
	oe3.display();
    return 0;
}

