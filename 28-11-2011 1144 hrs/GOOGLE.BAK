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
struct passty
{
 int nop,nom,nof;
 int apptim;
};
struct cargty
{
 int vog;
 int aptim;
 int nog;
 char brand[20];
};
class database
{
 char name[25];
 char code[10];
 public:
 char* retname()
 {
  return name;
 }
 char* retcode()
 {
  return code;
 }
 void read()
 {
  int gdriver = DETECT, gmode, errorcode;
  initgraph(&gdriver, &gmode, "");
  errorcode = graphresult();
  if (errorcode != grOk)
  {
   printf("Graphics error: %s\n", grapherrormsg(errorcode));
   printf("Press any key to halt:");
   getch();
   exit(1);
  }
  setbkcolor(4);
  cout<<"\n\tEnter the name of the ship:\t";
  gets(name);
  cout<<"\n\tEnter the code of the ship:\t";
  gets(code);
 }
};
class Arrival
{
 char type;
 char name[20];
 char code[10];
 public:
 char rettype()
 {
  return type;
 }
 char *retname()
 {
  return name;
 }
 char *retcode()
 {
  return code;
 }
 cargty c;
 passty p;
 void accept();
 void approval()
 {
  clrscr();
  int gdriver = DETECT, gmode, errorcode;
  initgraph(&gdriver, &gmode, "");
  errorcode = graphresult();
  if (errorcode != grOk)
  {
   printf("Graphics error: %s\n", grapherrormsg(errorcode));
   printf("Press any key to halt:");
   getch();
   exit(1);
  }
  setbkcolor(2);
 int poly[]={10,10,630,10,630,470,10,470,10,10};
 cout<<"\t\n\t\t\t APPROVAL CERTIFICATE";
 cout<<"\t\n\t\t\t ________ ___________";
 cout<<"\t\n\t\tThis is to certify that,the ship "<<name<<" is approved to ";
 cout<<"\t\n harbour in the Chennai port.";
 cout<<"\t\n\n Ship Details:";
 cout<<"\t\n\n Ship name:"<<name;
 cout<<"\t\n\n Ship code:"<<code;
 struct time t;
 gettime(&t);
 printf("\t\n\n The time of arrival is: %2d:%02d:%02d.%02d\n",
 t.ti_hour, t.ti_min, t.ti_sec, t.ti_hund);
 cout<<"\t\n\n Ship type:";
 if(type==1)
 {
  cout<<" Passenger";
  cout<<"\t\n\n No.of passengers:"<<p.nop;
  cout<<"\t\n\n No.of males:"<<p.nom;
  cout<<"\t\n\n No.of females:"<<p.nof;
  cout<<"\t\n\n Approx time of stay:"<<p.apptim<<"hours";
 }
 if(type==2)
 {
  cout<<" Cargo";
  cout<<"\t\n\n Volume of goods:"<<c.vog;
  cout<<"\t\n\n No.of goods"<<c.nog;
  cout<<"\t\n\n Organisation"<<c.brand;
  cout<<"\t\n\n Approx time of stay: "<<c.aptim<<"\thours";
 }
 cout<<"\n\n\t\t\t\t\t\tPORT MANAGER TM";
}
 void Disp()
 {
  cout<<"\n\tShip Name:\t"<<name;
  cout<<"\n\tShip code:\t"<<code;
  cout<<"\n\tShip type:\t";
  if(type==1)
  {
   cout<<"Passenger";
   cout<<"\n\tNo.of passengers:"<<p.nop;
   cout<<"\n\tNo.of males:"<<p.nom;
   cout<<"\n\tNo.of females:"<<p.nof;
  }
 if(type==2)
 {
  cout<<"Cargo";
  cout<<"\n\tThe volume of goods:"<<c.vog;
  cout<<"\n\tThe no.of goods:"<<c.nog;
  cout<<"\n\tOrganisation:"<<c.brand;
 }
 }
};
 void Arrival::accept()
 {
  clrscr();
  int gdriver = DETECT, gmode, errorcode;
  initgraph(&gdriver, &gmode, "");
  errorcode = graphresult();
  if (errorcode != grOk)
  {
   printf("Graphics error: %s\n", grapherrormsg(errorcode));
   printf("Press any key to halt:");
   getch();
   exit(1);
  }
  setbkcolor(2);
  cout<<"\n\n\t\t\tArrival Details";
  cout<<"\n\t\t\t------- -------";
  cout<<"\n\tEnter ship name:\t";
  gets(name);
  struct  time t;
  gettime(&t);
  int flag=0;
  ifstream fin3("database.dat",ios::binary);
  database d;
  while(fin3.read((char*)&d,sizeof(d)))
  {
   if(strcmpi(d.retname(),name)==0)
   {
    cout<<"\n\t\tThe ship is destined to the port.";
    cout<<"\n\t\tYour ship code:\t"<<d.retcode();flag=1;
    strcpy(code,d.retcode());
   }
  }
 if(flag)
 {
  cout<<"\n\tEnter type:\t";
  cout<<"\n\t1.Passenger:\t";
  cout<<"\n\t2.Cargo:\t";
  int ch1;
  cin>>ch1;
  type=ch1;
  if(ch1==1)
  {
   cout<<"\n\tEnter number of passengers:\t";
   cin>>p.nop;
  do
  {
   cout<<"\n\tEnter no of males:\t";
   cin>>p.nom;
   cout<<"\n\tEnter no of females:\t";
   cin>>p.nof;
  }
  while(p.nom+p.nof!=p.nop);
  cout<<"\n\tEnter approx time of stay(hours):\t";
  cin>>p.apptim;
  }
  if(ch1==2)
  {
   cout<<"\n\tEnter volume of goods:\t";
   cin>>c.vog;
   cout<<"\n\tEnter no of goods:\t";
   cin>>c.nog;
   cout<<"\n\tEnter organisation:\t";
   gets(c.brand);
   cout<<"\n\tEnter approx time of stay(hours):\t";
   cin>>c.aptim;
  }
 }
 else
  cout<<"\n\tShip not destined to the port.";
 fin3.close();
 approval();
}
 void asearch()
 {
  clrscr();
  int gdriver = DETECT, gmode, errorcode;
  initgraph(&gdriver, &gmode, "");
  errorcode = graphresult();
  if (errorcode != grOk)
  {
   printf("Graphics error: %s\n", grapherrormsg(errorcode));
   printf("Press any key to halt:");
   getch();
   exit(1);
  }
  setbkcolor(2);
  Arrival b;
  char n[20];
  cout<<"\n\tEnter ship name:\t";
  gets(n);
  ifstream fin4("Arrival.dat",ios::binary);
  while(fin4.read((char*)&b,sizeof(b)))
  if(strcmpi(b.retname(),n)==0)
  b.Disp();
  fin4.close();
 }
 class departure
 {
 int tos;
 char dname[20];
 char dcode[10];
 public:
 void check();
 void daccept();
 void dapproval(char* dname1,char* dcode1);
 void Display()
 {
  cout<<"\n\tShip name:\t"<<dname;
  cout<<"\n\tShip code:\t"<<dcode;
 }
  char *retname()
  {
   return dname;
  }
  char *retcode()
  {
  return dcode;
  }
  int rettos()
  {
   return tos;
  }
 };
 void departure :: dapproval(char* dname1,char* dcode1)
 {
  clrscr();
  int gdriver = DETECT, gmode, errorcode;
  initgraph(&gdriver, &gmode, "");
  errorcode = graphresult();
  if (errorcode != grOk)
  {
   printf("Graphics error: %s\n", grapherrormsg(errorcode));
   printf("Press any key to halt:");
   getch();
   exit(1);
  }
  setbkcolor(1);
  int tos=0,type1;
  Arrival a1;
  cout<<"\n\t\t\t DEPARTURE CERTIFICATE";
  cout<<"\n\t\t\t _________ ___________";
  cout<<"\n\t\tThis is to certify that,the ship "<<dname1<<" is approved to ";
  cout<<"\n depart the Chennai port.";
  cout<<"\n\n Ship Details:";
  cout<<"\n\n Ship name:"<<dname1;
  cout<<"\n\n Ship code:"<<dcode1;
  ifstream finn("arrival.dat",ios::binary);
  while(finn.read((char*)&a1,sizeof(a1)))
  {
   if(strcmpi(dname1,a1.retname())==0)
   {
    if(a1.rettype()==1)
     tos+=a1.p.apptim;
    else
     tos+=a1.c.aptim;
   }
  }
  long int cost=0;
  cost=(tos*5000);
  cout<<"\n\n Approx time of stay:"<<tos;
  cout<<"\n\n The rent for the stay is:Rs."<<cost;
  finn.close();
  cout<<"\n\n\t\t\t\t\t\tPORT MANAGER TM";
 }
 void departure :: daccept()
 {
  clrscr();
  int gdriver = DETECT, gmode, errorcode;
  initgraph(&gdriver, &gmode, "");
  errorcode = graphresult();
  if (errorcode != grOk)
  {
   printf("Graphics error: %s\n", grapherrormsg(errorcode));
   printf("Press any key to halt:");
   getch();
   exit(1);
  }
 setbkcolor(1);
 cout<<"\n\n\t\t\t\tDeparture Details";
 cout<<"\n\t\t\t\t_________ _______";
 cout<<"\n\tEnter name of ship:\t";
 gets(dname);
 ifstream fin0("database.dat",ios::binary);
 database d1;
 while(fin0.read((char*)&d1,sizeof(d1)))
 {
  if(strcmpi(dname,d1.retname())==0)
   strcpy(dcode,d1.retcode());
 }
 fin0.close();
 dapproval(dname,dcode);
 check();
 }
 void departure :: check()
 {
  Arrival a;
  ifstream fin("Arrival.dat",ios::binary);
  ofstream fout("departure.dat",ios::binary);
  ofstream fout2("new.dat",ios::binary);
  while(fin.read((char*)&a,sizeof(a)))
  {
   if(strcmpi(a.retcode(),dcode)==0)
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
  clrscr();
  int gdriver = DETECT, gmode, errorcode;
  initgraph(&gdriver, &gmode, "");
  errorcode = graphresult();
  if (errorcode != grOk)
  {
   printf("Graphics error: %s\n", grapherrormsg(errorcode));
   printf("Press any key to halt:");
   getch();
   exit(1);
  }
  setbkcolor(1);
  departure c;
  char n[20];
  cout<<"\n\tEnter ship name:\t";
  gets(n);
  ifstream fin5("departure.dat",ios::binary);
  while(fin5.read((char*)&c,sizeof(c)))
  {
   if(strcmpi(c.retname(),n)==0)
   c.Display();
  }
  fin5.close();
 }
 void delshipbase()
 {
  int gdriver = DETECT, gmode, errorcode;
  initgraph(&gdriver, &gmode, "");
  errorcode = graphresult();
  if (errorcode != grOk)
  {
   printf("Graphics error: %s\n", grapherrormsg(errorcode));
   printf("Press any key to halt:");
   getch();
   exit(1);
  }
  setbkcolor(4);
  ifstream fin("database.dat",ios::binary);
  ofstream fout("new.dat",ios::binary);
  cout<<"\n\tEnter the name of ship to be deleted";
  char n[100];
  cin>>n;
  database ship;
  while(fin.read((char*)&ship,sizeof(ship)))
  {
   if(strcmpi(ship.retname(),n)!=0)
   fout.write((char*)&ship,sizeof(ship));
  }
  fin.close();
  fout.close();
  remove("database.dat");
  rename("new.dat","database.dat");
 }
 void viewarr()
 {
  clrscr();
  int gdriver = DETECT, gmode, errorcode;
  initgraph(&gdriver, &gmode, "");
  errorcode = graphresult();
  if (errorcode != grOk)
  {
   printf("Graphics error: %s\n", grapherrormsg(errorcode));
   printf("Press any key to halt:");
   getch();
   exit(1);
  }
  setbkcolor(2);
  ifstream fin("Arrival.dat",ios::binary);
  Arrival a;
  int i=1;
  cout<<"\n\n\t\t\t The Ships that have Arrived:";
  while(fin.read((char*)&a,sizeof(a)))
  {
   cout<<"\n\n\t\t "<<i<<". "<<a.retname();
   i++;
   delay(500);
  }
  fin.close();
  getche();
 }
 void viewdep()
 {
  clrscr();
  int gdriver = DETECT, gmode, errorcode;
  initgraph(&gdriver, &gmode, "");
  errorcode = graphresult();
  if (errorcode != grOk)
  {
   printf("Graphics error: %s\n", grapherrormsg(errorcode));
   printf("Press any key to halt:");
   getch();
   exit(1);
  }
  setbkcolor(1);
  ifstream fin("departure.dat",ios::binary);
  departure d;
  int i=1;
  cout<<"\n\t\t\t The ships that have Departured are:";
  while(fin.read((char*)&d,sizeof(d)))
  {
   cout<<"\n\n\t\t"<<i<<". "<<d.retname();
   delay(500);
   i++;
  }
  fin.close();
  getche();
 }
 void viewdata()
 {
  clrscr();
  int gdriver = DETECT, gmode, errorcode;
  initgraph(&gdriver, &gmode, "");
  errorcode = graphresult();
  if (errorcode != grOk)
  {
   printf("Graphics error: %s\n", grapherrormsg(errorcode));
   printf("Press any key to halt:");
   getch();
   exit(1);
  }
  setbkcolor(4);
  ifstream fin("database.dat",ios::binary);
  database d;
  int i=1;
  cout<<"\n\t\t\t The ships that are available:";
  while(fin.read((char*)&d,sizeof(d)))
  {
   cout<<"\n\n\t\t"<<i<<". "<<d.retname();
   i++;
   delay(500);
  }
  fin.close();
  getche();
 }
 void main()
 {
  clrscr();
  char s[10];
  strcpy(s,"eshwar");
  char p;
  int flag=0;
  cout<<"\n\t\t\t Port Manager Login Authorization";
  cout<<"\n\t\t\t ---- ------- ----- -------------";
  cout<<"\n\tEnter your password:\t";
  for(int i=0;i<=strlen(s);i++)
  {
   p=getche();
   if(p==' '|| p=='\b')
   {
    delline();
    cout<<"\n\t\tLogin Unsuccessful";
    getche();
    exit(0);
   }
   else
   {
    cout<<"\b$";
    if(s[i]==tolower(p))
    flag++;
   }
  }
  clrscr();
  if(flag==strlen(s))
  cout<<"\n\n\t\t\tLogin Successful";
  else
  {
   cout<<"\nLogin Unsuccessful";
   exit(0);
  }
  getche();
  char choice;
  int gdriver = DETECT, gmode, errorcode;
  initgraph(&gdriver, &gmode, "");
  errorcode = graphresult();
  if (errorcode != grOk)
  {
   printf("Graphics error: %s\n", grapherrormsg(errorcode));
   printf("Press any key to halt:");
   getch();
   exit(1);
  }
  int poly1[]={10,10,630,10,630,470,10,470,10,10};
  int poly[]={390,200,480,200,450,300,190,300,160,200,260,200};
  cout<<"\n\n\t\t\tConcepts Used";
  delay(500);
  cout<<"\n\t\t\t-------- ----";
  delay(500);
  cout<<"\n\n\t Classes and Objects";
  delay(500);
  cout<<"\n\n\t Binary Files";
  delay(500);
  cout<<"\n\n\t Structures";
  delay(500);
  cout<<"\n\n\t Arrays";
  delay(500);
  cout<<"\n\n\t Graphics";
  delay(500);
  cout<<"\n\n\t Functions";
  drawpoly(5,poly1);
  getche();
  cleardevice();
  cout<<"\n\tLoading....";
  int ss=1;
  randomize();
  for(int j=10;j<=200;j+=10)
  {
   int r=random(11);
   while(ss==r && r==0)
   r=random(11);
   setcolor(r);
   drawpoly(5,poly1);
   circle(320,240,j);
   delay(500);
   ss=r;
  }
  getche();
  cleardevice();
  setcolor(3);
  int poly0[]={10,270,180,270,190,300,450,300,460,270,630,270,630,330,10,330,10,270};
  line(260,150,260,200);
  delay(500);
  line(300,150,300,200);
  delay(1000);
  line(300,200,340,200);
  delay(500);
  line(340,130,340,200);
  delay(500);
  line(390,130,390,200);
  delay(500);
  line(260,150,300,150);
  delay(500);
  line(340,130,390,130);
  delay(500);
  setcolor(3);
  drawpoly(6,poly);
  delay(500);
  setfillstyle(SOLID_FILL,1);
  int poly2[]={390,200,480,200,450,300,190,300,160,200,260,200,260,150,300,150,300,200,340,200,340,130,390,130,390,200,390,200};
  fillpoly(12,poly2);
  setcolor(7);
  drawpoly(13,poly2);
  setcolor(4);
  drawpoly(5,poly1);
  delay(500);
  setcolor(3);
  setfillstyle(SOLID_FILL,3);
  fillpoly(8,poly0);
  setcolor(2);
  delay(500);
  outtextxy(260,350,"Port");
  outtextxy(310,350,"Manager");
  delay(1000);
  setcolor(5);
  outtextxy(285,370,"Version");
  outtextxy(345,370,"I");
  getche();
  closegraph();
  int n;
  do
  {
   clrscr();
   initgraph(&gdriver, &gmode, "");
   setbkcolor(9);
   Arrival a;
   departure d;
   cout<<"\n\t\t\tPort Manager Build 1.0";
   cout<<"\n\t\t\t---- ------- ----- ---";
   delay(500);
   cout<<"\n\t\t\tChennai Port Trust Estd. 1881";
   cout<<"\n\t\t\t------- ---- ----- ----- ----";
   delay(500);
   cout<<"\n\t\t\tOptions";
   cout<<"\n\t\t\t-------";
   delay(500);
   cout<<"\n\n\t\t\t 1.Add to Arrivals";
   delay(500);
   cout<<"\n\n\t\t\t 2.Add to Departures";
   delay(500);
   cout<<"\n\n\t\t\t 3.Search Arrivals";
   delay(500);
   cout<<"\n\n\t\t\t 4.Search Departures";
   delay(500);
   cout<<"\n\n\t\t\t 5.Add ships to the database";
   delay(500);
   cout<<"\n\n\t\t\t 6.Delete a ship from the database";
   delay(500);
   cout<<"\n\n\t\t\t 7.View Arrivals";
   delay(500);
   cout<<"\n\n\t\t\t 8.View Departures";
   delay(500);
   cout<<"\n\n\t\t\t 9.View Database";
   delay(500);
   cout<<"\n\n\t\t\t10.Log Out";
   int ch;
   delay(500);
   cout<<"\n\n\tEnter ur choice:\t";
   cin>>ch;
   switch(ch)
   {
    case 1: setbkcolor(2);
	    a.accept();
	    ofstream fout("Arrival.dat",ios::binary|ios::app);
	    fout.write((char*)&a,sizeof(a));
	    fout.close();
	    break;
    case 2: setbkcolor(1);
	    d.daccept();
	    d.check();
	    ofstream fout1("departure.dat",ios::binary,ios::app);
	    fout1.write((char*)&d,sizeof(d));
	    fout1.close();
	    break;
    case 3: setbkcolor(2);
	    asearch();
	    break;
    case 4: setbkcolor(1);
	    dsearch();
	    break;
    case 5: setbkcolor(4);
	    cout<<"\n\n\t\t Enter the no.of ships to be added";
	    cin>>n;
	    database ds;
	    ofstream fout0("database.dat",ios::binary|ios::app);
	    for(int i=1;i<=n;i++)
	    {
	     ds.read();
	     fout0.write((char*)&ds,sizeof(ds));
	    }
	    fout0.close();
	    break;
    case 6: setbkcolor(4);
	    delshipbase();
	    break;
    case 7: setbkcolor(2);
	    viewarr();
	    break;
    case 8: setbkcolor(1);
	    viewdep();
	    break;
    case 9: setbkcolor(4);
	    viewdata();
	    break;
    case 10:exit(0);
	    break;
    default: cout<<"\n\t Invalid Input.";
   }
   cout<<"\n\n\t\t\t\t\t\tDo you want to continue using Port Manager?";
   cin>>choice;
   closegraph();
  }
  while(choice=='y'|| choice=='Y');
  getche();
 }


