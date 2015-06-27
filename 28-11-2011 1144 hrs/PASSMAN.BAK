#include<iostream.h>
#include<conio.h>
#include<stdio.h>
#include<graphics.h>
#include<math.h>
#include<process.h>
#include<string.h>
void main()
{
clrscr();
char s[10];
strcpy(s,"eshwar");
char p;
int flag=0;
cout<<"\n\t\t\t Port Manager Login Authorization";
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
{cout<<"\b$";
if(s[i]==p)
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
}