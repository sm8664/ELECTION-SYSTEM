# ELECTION-SYSTEM
#include <stdio.h>
#define CANDIDATE_COUNT
#define CANDIDATE1 "NARENDRA MODI"
#define CANDIDATE2 "JUSTIN TRUDEA"
#define CANDIDATE3 "JOE BIDEN"
#define CANDIDATE4 "BORIS JOHNSON"

int votecount1 = 0, votecount2 = 0, votecount3 = 0, votecount4=0, notacount = 0;

int
castvote ()
{
  int choice;
  printf ("\n****PLEASE CHOOSE YOUR CANDIDATE****\n");
  printf ("1.%s\n", CANDIDATE1);
  printf ("2.%s\n", CANDIDATE2);
  printf ("3.%s\n", CANDIDATE3);
  printf ("4.%s\n", CANDIDATE4);
  printf ("5.NONE OF THE ABOVE\n\n");
  printf ("ENTER YOUR CHOICE-");
  scanf ("%d", &choice);
  switch (choice)
    {
    case 1:
      votecount1++;
      break;
    case 2:
      votecount2++;
      break;
    case 3:
      votecount3++;
      break;
    case 4:
      votecount4++;
      break;
    case 5:
      notacount++;
      break;
    default:
      printf ("XXXXX ERROR XXXXX\n WRONG CHOICE!!\n PLEASE TRY AGAIN");
      getchar ();
    }
  printf ("THANKS FOR VOTING\n");
}

int
votescount ()
{
  printf ("\n\n****Voting Statics****");
  printf ("\n %s - %d ", CANDIDATE1,votecount1);
  printf ("\n %s - %d ", CANDIDATE2,votecount2);
  printf ("\n %s - %d ", CANDIDATE3,votecount3);
  printf ("\n %s - %d ", CANDIDATE4,votecount4);
  printf ("\n %s - %d ", "NOTA",notacount);
}

int
getleadingcandidate ()
{
 if(votecount1>votecount2 && votecount1>votecount3 && votecount1 >votecount4)
    printf("[%s]",CANDIDATE1);
    else if (votecount2>votecount3 && votecount2>votecount4 && votecount2 >votecount1)
    printf("[%s]",CANDIDATE2);
    else if(votecount3>votecount4 && votecount3>votecount2 && votecount3 >votecount1)
    printf("[%s]",CANDIDATE3);
    else if(votecount4>votecount1 && votecount4>votecount2 && votecount4 >votecount3)
    printf("[%s]",CANDIDATE4);
  else
    printf (" NO WIN SITUATION");
}

int
main ()
{
  int i;
  int choice;

  do
    {
      printf ("\n\n****WELCOME TO 2021 WORLD ELECTIONS****");
      printf ("\n\n 1. Cast the Vote");
      printf ("\n 2. Find Vote Count");
      printf ("\n 3. Find leading Candidate");
      printf ("\n 0. Exit");

      printf ("\n\n Please enter your choice : ");
      scanf ("%d", &choice);

      switch (choice)
	{
	case 1:
	  castvote ();
	  break;
	case 2:
	  votescount ();
	  break;
	case 3:
	  getleadingcandidate();
	  break;
	default:
	  printf ("\n Error: Invalid Choice");
	}
    }
  while (choice != 0);
  getchar ();
  return 0;
}
