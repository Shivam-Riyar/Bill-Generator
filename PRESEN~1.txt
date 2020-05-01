#include<stdio.h>
#include<conio.h>
#include<string.h>
#include<process.h>
struct item
{
 char name[30];
 int qty;
 float price,total_price;
};
void main()
{
 struct item I[100];
 int i1,i2,i3,ctrsw,n=0,tempsum=0;
 char ch,ctr1='y';
 char srchname[30];
 float tot_amt=0;
 while(1)
 {
  clrscr();
  printf("\n=-=-=-=-=-=OPTION MENU=-=-=-=-=-=");
  printf("\n 1. NEW BILL \n 2. PRINT BILL \n 3. EDIT BILL \n 4. EXIT ");
  printf("\n ENTER YOUR CHOICE : ");
  scanf("%d",&ctrsw);
  switch(ctrsw)
  {
   case 1 : int temp; n=0;
	    printf("\n HOW MANY ITEMS TO BE BILLED ?  ");
	    scanf("%d",&temp);

	    do{
	    tempsum=temp+n;
	    for(i1=n;i1<tempsum;i1++)
	    { printf("\n ENTER NAME     : ");scanf("%s",I[i1].name);
	      printf("   ENTER PRICE    : ");scanf("%f",&I[i1].price);
	      printf("   ENTER QUANTITY : ");scanf("%d",&I[i1].qty);
	      I[i1].total_price=I[i1].price * I[i1].qty;
	      tot_amt+=I[i1].total_price;
	    } n=i1;
	    printf("\n MORE ITEMS LEFT? (press 2 for yes) : ");
	    scanf("%d",&ch);
	    if(ch==2)
	    {
	     printf("\n HOW MANY MORE ITEMS LEFT ? : ");
	     scanf("%d",&temp);
	    }
	    else
	    {
	     ctr1='n';
	    }}while(ctr1=='y');
	    getch();
	    break;
   case 2 : clrscr();
	    printf("\n |No.|    ITEM NAME    | UNIT PRICE | QUANTITY | TOTAL PRICE |");
	    printf("\n =============================================================");
	    for(i2=0;i2<n;i2++)
	    {
	     printf("\n %d   %s           %f         %d         %f",i2+1,I[i2].name,I[i2].price,I[i2].qty,I[i2].total_price);
	    }
	    printf("\n\n\t ====TOTAL AMOUNT : %f==== ",tot_amt);
	    getch();
	    break;
   case 3 : clrscr();
	    printf("\n ENTER NAME OF ITEM TO BE SEARCHED FOR : ");
	    scanf("%s",srchname);

	    for(i3=0;i3<n;i3++)
	    {
	     if((strcmpi(srchname,I[i3].name))==0)
	     {  printf("\n ENTER NAME     : ");scanf("%s",I[i3].name);
		printf("\n ENTER PRICE    : ");scanf("%f",&I[i3].price);
		printf("\n ENTER QUANTITY : ");scanf("%d",&I[i3].qty);
		I[i1].total_price=I[i3].price * I[i3].qty;
	     }
	    }printf("\n EDIT COMPLETE ");
	    getch();
	    break;
   case 4 : exit(0);
	    break;
   default: printf("\n WRONG CHOICE ");
	    getch();
  }
 getch();
 }
}
void linkfloat( )
{
 float a = 0, *b ;
 b = &a ;
 a = *b ;
}


