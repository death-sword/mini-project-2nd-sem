# mini-project-2nd-sem
2nd semester mini project in C for problem solving through programming
//project for prototype//
#include<stdio.h>
#include<stdlib.h>
#include<string.h>
void waste (char);
void user (char);
int main()
 {
   char name[20],email[20],phone[10],lemail[20];
   //database to store all this info and check if user is using for first time user or not for the discounts
   float weight,item,amt=0;
   //number of times used
   printf("enter the name\n");
   scanf("%s",&name);
   int choice,login,phck,emchk1,emchk2;
   //choosing the login method
   printf("1: phone\n 2: email\n 3: guest user \n 4: cancel login \n");
   scanf("%d",&login);
   switch (login)
   {
     case 1:user(name);
             printf("enter the phone number\n");
             scanf("%s",phone);
             phck=strlength(phone);
             if(phck==10)
              waste(item);
             else
              printf("invalid phonenumber");
              break;
     case 2:user(name);
           printf("enter the email id of the user\n");
           scanf("%s",email);
           emchk1=strchr(email,'@');
           lemail=strlwr(email);
           emchk2=strchr(email,"mail.com");
           if(emchk1!='\0'&& emchk2!='\0')
            waste(item);
           else
            printf("invalid email id");
            break;
    case 3:waste(item);
          break;
    case 4:exit(0);
    default: printf("invalid option\n")
  }
}
   void user(char)
   {
     printf("enter the name of the user\n");
     scanf("%s",name);
   }
   void waste(int item)
   //sensors are to be installed to differentiate the items//
   {
     printf("1:plastic waste\n 2:metal waste\n 3:glass waste \n 4: other\n");
     scanf("%d",&item);
     switch(item)
     {
     case1:
                printf("enter the weight of the plastic user\n")
                scanf("%f",&weight);
                if (weight<=10)
                  amt+=weight*0.1;
                else if(weight<=100)
                  amt+=10*0.1+(weight-10)*0.2;
                else
                  amt+=10*0.1+100*0.2+(weight-100)*0.5;
                printf("the amount is %f\n",amt);
    case2:
                printf("enter the weight of the metal waste\n");
                scanf("%f",&weight);
                if(weight<=10)
                  amt+=weight*0.5;
                else if(weight<=100)
                  amt+=10*0.1+(weight-10)*0.75;
                else
                  amt+=10*0.1+100*0.5+(weight-100)*1.25;
                printf("the amount is %f\n",amt);
    case3:
                printf("enter the weight of the glass waste\n");
                scanf("%f",&weight);
                if(weight<=10)
                  amt+=10*0.45;
                else if(weight<=100
                  amt+=10*0.45+(weight-100)*0.65;
                  else
                  amt+=10*0.45+100*0.65+(weight_100)*0.95;
                  printf("the amount is %f\n",amt);
     }
  }
