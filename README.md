<div align="center">

## Twenty\-One Card Game


</div>

### Description

This is a re-creation of the card game Twenty-One. It is quite simple.
 
### More Info
 
Number of cards wanted and if you want to continue play

Make sure to delete the character 'y' in the next input line when you type 'y' to continue play


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Morgan L\.D\.](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/morgan-l-d.md)
**Level**          |Beginner
**User Rating**    |4.7 (14 globes from 3 users)
**Compatibility**  |C\+\+ \(general\)
**Category**       |[Games](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/games__3-13.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/morgan-l-d-twenty-one-card-game__3-5221/archive/master.zip)

### API Declarations

```
iostream.h
stdlib.h
conio.h
random.h
```


### Source Code

```
//Chapter 4, Exercise 33 of "A Guide to Programming in C++"
//(c)Morgan L.D.
//November 18, 2002
//Created with Dev C++ Programmer
//*Note* - Include files may vary among programmers
//This is a card game similar to Twenty-One
//
#include <iostream.h>
#include <stdlib.h>
#include <lvp\conio.h>
#include <lvp\random.h>
void main()
{
   randomize();
   cout<<"--Twenty-One Card Gamer--"<<endl<<endl;
   int CardsComp=3, ScoreComp=0, ScoreYou=0, Draw=0, CardsYou, Continue;
   int Cards1=0, YouTot=0, CompTot=0, Cards=0;
   const int TO=21;  //highest winning value
   while(1==1)  //runs loop until its broken
   {
     cout<<"How many cards do you want? ";
     cin>>CardsYou;
     cout<<"You: ";
     for(int CardsY=1; CardsY<=CardsYou; CardsY++)
       {
       Cards=random(10)+1;//generates random cards set to specific #
       cout<<Cards<<" ";
       YouTot+=Cards;  //totals cards
       }
     cout<<endl;
     cout<<"Computer: ";
     for(int CardsC=1; CardsC<=3; CardsC++)
       {
       Cards1=random(10)+1; //generates random cards
       cout<<Cards1<<" ";
       CompTot+=Cards1;  //totals cards
       }
     cout<<endl;
     cout<<"I have "<<CompTot<<" and you have "<<YouTot<<" so ";
     //below decides winning statement to output
     if(CompTot<=TO && CompTot>YouTot)
      { cout<<"I win"<<endl;
       ScoreComp++;
      }
     else if(YouTot<=TO && YouTot>CompTot)
      { cout<<"you win"<<endl;
       ScoreYou++;
      }
     else if(CompTot<=TO && YouTot>TO)
      { cout<<"I win"<<endl;
       ScoreComp++;
      }
     else if(YouTot<=TO && CompTot>TO)
      { cout<<"you win"<<endl;
       ScoreYou++;
      }
     else if(CompTot==YouTot)
      { cout<<"we draw"<<endl;
       Draw++;
      }
     CompTot=0;  //clears totals so they don't carry on in the...
     YouTot=0;       //next loop
     cout<<"Would you like to play again? (Y/N)? "; //loop program again
     Continue=getch();
     cout<<endl<<endl;
     if(Continue=='n' || Continue=='N')
      break;  //breaks loop if continue is true
   }
   cout<<"Computer wins = "<<ScoreComp<<endl;  //end of program
   cout<<"Your wins = "<<ScoreYou<<endl;      //chart
   cout<<"Draws = "<<Draw<<endl;
   cout<<endl;
   system("PAUSE");
}
```

