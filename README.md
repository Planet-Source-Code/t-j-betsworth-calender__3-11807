<div align="center">

## Calender


</div>

### Description

displays a calender for any year

after 1900 in a single window
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[T J Betsworth](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/t-j-betsworth.md)
**Level**          |Advanced
**User Rating**    |4.8 (24 globes from 5 users)
**Compatibility**  |C\+\+ \(general\)
**Category**       |[Miscellaneous](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/miscellaneous__3-1.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/t-j-betsworth-calender__3-11807/archive/master.zip)





### Source Code

```
#include<iostream>
#include <stdlib.h>
#include <windows.h>
using namespace std;
HANDLE hout= GetStdHandle(STD_OUTPUT_HANDLE);
COORD coord ;
  int main()
{
      SetConsoleTitle("Calender");
      COORD coord = {100,36};
      SMALL_RECT rec = {0,0,0,0};
      SetConsoleScreenBufferSize(hout, coord);
      rec.Right = coord.X -1;
      rec.Bottom = coord.Y -1;
      SetConsoleWindowInfo(hout,TRUE,&rec);
  int year,day=0,x,y;
  int m[12]={31,28,31,30,31,30,31,31,30,31,30,31};
  int a[12]={24,48,72,96,24,48,72,96,24,48,72,96};
  char string[12][255] = {"JANUARY","FEBRUARY","MARCH","APRIL", "MAY","JUNE","JULY",
               "AUGUST","SEPTEMBER","OCTOBER","NOVEMBER","DECEMBER"};
COORD coord1 = {4,2};
SetConsoleTextAttribute(hout,12 );
SetConsoleCursorPosition(hout,coord1);
  cout<<"Enter Year 1900+ ";
  cin>>year;
  if(year<1901){
  cout<<"ERROR! ";
  system("PAUSE");
  return 0;
  }
COORD coord2 = {4,2};
SetConsoleTextAttribute(hout,12 );
SetConsoleCursorPosition(hout,coord2);
cout<<"Calender For The Year "<<year;
  for(int b=1;b<13;b++){
      m[1]=!(year%4)+28;
  for(int i=1900;i<year;i++,day++){
    day+=!(i%4);
    day%=7;
  }
for(int i=2;i<=b;i++) day+=m[i-2];day%=7;
   if (b==1){x=4;y=6;}
else if (b==2){x=28;y=6;}
else if (b==3){x=52;y=6;}
else if (b==4){x=76;y=6;}
else if (b==5){x=4;y=16;}
else if (b==6){x=28;y=16;}
else if (b==7){x=52;y=16;}
else if (b==8){x=76;y=16;}
else if (b==9){x=4;y=26;}
else if (b==10){x=28;y=26;}
else if (b==11){x=52;y=26;}
else if (b==12){x=76;y=26;}
COORD coord3 = {x,y-1};
SetConsoleTextAttribute(hout,249);
SetConsoleCursorPosition(hout,coord3);
cout<<"Mo Tu We Th Fr Sa Su";
COORD coord4 = {x,y-2};
SetConsoleTextAttribute(hout,12 );
SetConsoleCursorPosition(hout,coord4);
cout<<string[b-1];
 if (day==1)x=x;
 if (day==2)x=x+3;
 if (day==3)x=x+6;
 if (day==4)x=x+9;
 if (day==5)x=x+12;
 if (day==6)x=x+15;
 if (day==0)x=x+18;
  for(int i=1;i<=m[b-1];i++)
  {
COORD coord3 = {x,y};
SetConsoleTextAttribute(hout,11);
SetConsoleCursorPosition(hout,coord3);
cout.width(2); cout<<i<<char(32);
 x+=3;
   if(x>a[b-1])
    {
 y++;x-=21;}
     }
  day=0;
}
COORD coord5 = {35,33};
SetConsoleTextAttribute(hout,12 );
SetConsoleCursorPosition(hout,coord5);
system("PAUSE");
return 0;
}
```

