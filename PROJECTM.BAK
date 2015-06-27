#include<iostream.h>
#include<conio.h>
#include<stdio.h>
#include<process.h>
#include<fstream.h>
#include<string.h>
#include<ctype.h>
#include<graphics.h>
#include<time.h>
#include<dos.h>
#include<stdlib.h>
struct scode
{
int sscode;};
struct passty
{
int nop,nom,nof;
float apptim;
};
struct cargty
{
int vog;
float aptim;
int nog;
char brand[20];
};
class Arrival
{
int toa;
char name[20];
int code;
cargty c;
passty p;
public:
int retcode()
{
return code;
}
void accept();
char *retname()
{
return name;
}
void Disp()
{
cout<<"\nShip Name:\t"<<name;
cout<<"\nship code:\t"<<code; }
};
void Arrival::accept()
{
cout<<"\nEnter ship name:\t";
gets(name);
cout<<"\nEnter time of arrival:\t";
cin>>toa;
scode s;
ifstream fin3("code.dat",ios::binary);
fin3.read((char*)&s,sizeof(s));
code=s.sscode;
s.sscode++;
ofstream fout1("code.dat",ios::binary|ios::trunc);
fout1.write((char*)&s,sizeof(s));
cout<<"\nyour ship code:\t"<<code;
cout<<"\nenter type:\t";
cout<<"\n1.Passenger:\t";
cout<<"\n2.Cargo:\t";
int ch1;
cin>>ch1;
if(ch1==1)
{
cout<<"\nenter number of passengers:\t";
cin>>p.nop;
cout<<"\nenter no of males:\t";
cin>>p.nom;
cout<<"\nenter no of females:\t";
cin>>p.nof;
cout<<"\nenter approx time of stay(hours):\t";
cin>>p.apptim;
}
else if(ch1==2)
{
cout<<"\nenter volume of goods:\t";
cin>>c.vog;
cout<<"enter no of goods:\t";
cin>>c.nog;
cout<<"\nenter brand of good:\t";
gets(c.brand);
cout<<"\nenter approx time of stay(hours):\t";
cin>>c.aptim;
}
else
cout<<"invalid choice";
fin3.close();fout1.close();
}
void asearch()
{
Arrival b;
char n[20];
cout<<"\nenter ship name:\t";
gets(n);
ifstream fin4("Arrival.dat",ios::binary);
while(fin4.read((char*)&b,sizeof(b)))
if(strcmpi(b.retname(),n)==0)
b.Disp();
fin4.close();
}
class departure
{
int tod;
char dname[20];
int dcode;
public:
void check();
void daccept();
void Display()
{
cout<<"\nShip name:\t"<<dname;
cout<<"\nShip code:\t"<<dcode;
cout<<"\ntime of departure:\t"<<tod;   }
char *retname()
{return dname;}
};
void departure :: daccept()
{
cout<<"\n Enter time of departure:\t";
cin>>tod;
cout<<"\n Enter name of ship:\t";
gets(dname);
cout<<"\nEnter ship code";
cin>>dcode;
}
void departure :: check()
{
Arrival a;
ifstream fin("Arrival.dat",ios::binary);
ofstream fout("Departure.dat",ios::binary);
ofstream fout2("new.dat",ios::binary);
while(fin.read((char*)&a,sizeof(a)))
{
if(a.retcode()==dcode)
fout.write((char*)&a,sizeof(a));
else
fout2.write((char*)&a,sizeof(a));
}
fin.close();fout.close();fout2.close();
remove("Arrival.dat");
rename("new.dat","Arrival.dat");

}
void dsearch()
{
departure c;
char n[20];
cout<<"\nenter ship name:\t";
gets(n);
ifstream fin5("departure.dat",ios::binary);
while(fin5.read((char*)&c,sizeof(c)))
{
if(strcmpi(c.retname(),n)==0)
c.Display();
}
fin5.close();
}
void main()
{ char choice;
/* request auto detection */
int gdriver = DETECT, gmode, errorcode;
/* initialize graphics, local variables */
initgraph(&gdriver, &gmode, "");

/* read result of initialization */
errorcode = graphresult();
if (errorcode != grOk)
/* an error occurred */
{
   printf("Graphics error: %s\n", grapherrormsg(errorcode));
   printf("Press any key to halt:");
   getch();
   exit(1);
   /* terminate with an error code */
}
cout<<"\n\n\n\n\t\t\t\tPORT MANAGEMENT";
cout<<"\n\t\t\tChennai Port Trust estd.1901";
cout<<"\n\tLoading....";
int s=1;
randomize();
for(int i=10;i<=100;i+=10)
{ int r=random(11);
while(s==r)
r=random(11);
setcolor(r);
circle(320,240,i);
delay(200);
s=r;
}
getche();
clrscr();
int defpass=1100,entpass[4];
for(int p=0;p<=3;p++)
{cin>>entpass[p];
cout<<"\nb";
delline(); }
closegraph();
do
{
clrscr();
Arrival a;
departure d;
initgraph(&gdriver, &gmode, "");
settextstyle(SANS_SERIF_FONT,HORIZ_DIR,1);
cout<<"\n\t\t\tPORT MANAGEMENT";
cout<<"\n\t\t\t---- ----------";
cout<<"\n\t\t\tMENU";
cout<<"\n\t\t\t1.ARRIVAL";
cout<<"\n\t\t\t2.DEPARTURE";
cout<<"\n\t\t\t3.SEARCH";
int ch;
cout<<"\nEnter ur choice:\t";
cin>>ch;
if(ch==1)
{
a.accept();
ofstream fout("Arrival.dat",ios::binary|ios::app);
fout.write((char*)&a,sizeof(a));
fout.close();
}
else if(ch==2)
{
d.daccept();
d.check();
}
if(ch==3)
{
int c;
cout<<"\nSearch By:";
cout<<"\n1.Arrivals";
cout<<"\n2.Departures";
cout<<"\nenter choice:\t";
cin>>c;
if(c==1)
asearch();
else if(c==2)
dsearch();
else cout<<"\nInvalid i/p";
}
else
cout<<"\n Invalid I/P";
getche();
cout<<"\n\n Do you want to continue?";
cin>>choice;
}
while(choice=='y');
getche();
closegraph();
}


