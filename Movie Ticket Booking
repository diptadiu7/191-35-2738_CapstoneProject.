#include<stdio.h> //Library function for input/output
#include<stdlib.h> //library function for define size
#include<string.h>//for using string function
#define ENTER 13//global variable
#define uname"dipta"//here user name define
#define pass"123"//here password define
void login();//for login function
void insertNewMovie();//for inserting movie
void viewAllMovieList();//for viewing all movie list
void find();//finding movie
void bookTicket();//for booking ticket
void oldTransectionHistory();//for checking old transaction history

struct book //structure
{
    char code[20];//character data type
    char name[20];//character data type
    char date[20];//character data type
    int cost;//integer data type
} b;//structure variable

void main()//main function
{
    login();//here calling login function

    int ch;//integer variable

    do//here loop start(taking user input)
    {
        printf("\n#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#");//display *#
        printf("\t\t\tWelcome Movie Ticket System of 'XYZ Cineplex' Movie Booking System");//print output
        printf("\n");//display output
        printf("\n*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*#*");//display *#


        printf("\nEnter >1< To Insert Movie");//display output
        printf("\nEnter >2< To Show All Movie List");//display output
        printf("\nEnter >3< Find Movie");//print output
        printf("\nEnter >4< Book Ticket");//print output
        printf("\nEnter >5< To Show All Purchased History");//print output
        printf("\nEnter >0< Quit");//print output


        printf("\nEnter your Choice ::");//entering choice
        scanf("%d",&ch);//taking character value from the user
        system("cls");//refresh output screen

        switch (ch)//here switch case start
        {
        case 1 ://for inserting output
            printf("\t\tPlease Fill All The Information To Add a New Movie.\n");//display output
            insertNewMovie();//for inserting movie
            break;//condition break
        case 2://for inserting output
            printf("\t\t\tAll Movie List from the FILE.\n");//display output
            viewAllMovieList();//for view movie list
            break;//condition break

        case 3://for inserting output
            printf("\t\t\tEnter Movie Code to Find Details of the Movie\n");//display output
            find();//for finding movie code
            break;//condition break

        case 4://for inserting output
            bookTicket();//for booking ticket
            break;//condition break

        case 5://for inserting output
            printf("\t\tPrevious All Transaction History\n");//display output
            oldTransectionHistory();//for seeing old transaction history
            break;//condition break

        case 0://for inserting output
            exit(0);//for exiting loop
            break;//condition break

        default://for wrong choice
            printf("Wrong choice !");//printing output
            break;//condition break
        }
    }
    while(ch!=0);//condition checking

}
void login()//login function
{
    system("cls");//refresh output screen
    int count=0,i=0;//integer value
    char ch;//character data type
    char username[10],password[10];//character data type
    do//loop start
    {
        printf("\t\t\tWELCOME TO 'XYZ CINEPLEX' BOOKING SYSTEM\n");//display output
        printf(" \t\t\t\t PLEASE LOG IN FIRST\n");//display output
        printf("\n *************************  LOGIN SECTION  ************************* ");//display output
        printf(" \n\nEnter USERNAME:-");//display output
        scanf("%s",&username);//taking input
        printf(" \n\nEnter PASSWORD:-");//display output
        while(1)//for condition
        {
            ch = getch();//taking input
            if(ch==ENTER)//checking condition
            {
                password[i]='\0';//statement
                break;//loop break
            }
            else//checking condition for second time
            {
                password[i]=ch;//taking input in password [i]
                i++;//increase value of i
                printf("*");//printing output
            }

        }
        if(strcmp(username,uname)==0 && strcmp(password,pass)==0)//comparing user name and password
        {
            printf("  \n\n\n       WELCOME TO 'XYZ CINEPLEX' BOOKING SYSTEM !!!! LOGIN IS SUCCESSFUL");//printing output
            printf("\n\n\n\t\t\t\tPress any key to continue...");//printing output
            getch();//taking input from keyboard
            break;//braking loop
        }
        else//checking condition for second time
        {
            printf("\n\n\n       SORRY !!!!LOGIN IS FAILED....WRONG USERNAME/PASSWORD..PLEASE TRY AGAIN.\n\n");//printing output
            count++;//increase value of i
            getch();//taking input from keyboard
        }
    }
    while(count<=2);//condition

    if (count>2)//condition
    {
        printf("\n\n\nSORRY YOU HAVE ENTERED WRONG USERNAME/PASSWORD FOR THREE TIMES.PLEASE TRY AGAIN LATER!!\n\n");//display output

        exit(1);//exiting loop
        getch();//taking input from keyboard

    }
    system("cls");//refresh output screen

}

void insertNewMovie()//for inserting new movie
{

    FILE *fp;//pointer file declaration

    struct book b;//define structure variable

    printf("Enter Movie Code  :- ");//display output
    scanf("%s",b.code);//taking input
    printf("Enter Movie Name  :- ");//display output
    fflush(stdin);//refresh memory
    scanf("%s",b.name);//taking input
    printf("Enter Release Date:- ");//display output
    fflush(stdin);//refresh memory
    scanf("%s",b.date);//taking input
    printf("Enter Ticket Price:- ");//display output
    fflush(stdin);//refresh memory
    scanf("%d",&b.cost);//taking input

    fp=fopen("data.txt","a");//file creation

    if(fp == NULL)//checking file
    {
        printf("File not Found");//print output
    }
    else//checking condition for second time
    {
        fprintf(fp,"%s %s %s %d \n",b.code,b.name,b.date,b.cost);//printing data from the file
        printf("Recorded Successfully");//print output
    }
    printf("\n");//print new line
    fclose(fp);//closing file
}

void viewAllMovieList()//for viewing movie list
{

    char ch;//character variable

    FILE *fp;//file declaration

    fp = fopen("data.txt","r");//open and reading the file
    if(fp == NULL)//checking file
    {
        printf("FILE does not found!");//print output
    }
    else//checking condition for second time
    {
        while( ( ch = fgetc(fp) ) != EOF )//getting input from file
            printf("%c",ch);//print character value
    }

    fclose(fp);//file close
}


void find()//for find movie
{
    struct book b;//declare structure data type
    FILE *fp;//file declaration

    char ch[20],line[80];// character type array
    printf("Enter Movie Code :");//print output
    fflush(stdin);//refresh memory
    scanf("%s",ch);//taking string type input from the user

    fp = fopen("data.txt","r");//file open and reading from the file
    if(fp == NULL)//checking file
    {
        printf("file does not found !");//print output
        exit(1);//exiting loop
    }
    else//checking condition for second time
    {
        while((fgets(line,80,fp)) != NULL)//take data from the fp file and checking condition
        {

            sscanf(line,"%s %s %s %d",b.code,b.name,b.date,&b.cost);//scanning data from the file
            if(strcmp(b.code,ch) == 0)//string compare
            {
                printf("\n   Record Found\n");//print output
                printf("\n\t\tCode                 ::%s",b.code);//print output
                printf("\n\t\tMovie name           ::%s",b.name);//print output
                printf("\n\t\tMovie Release date   ::%s",b.date);//print output
                printf("\n\t\tPrice of ticket      ::%d",b.cost);//print output
                break;//braking loop
            }
        }
        if(strcmp(b.code,ch) != 0)//string compare
        {
            printf("\nMovie Not Found!! Please try with another movie code.");//print output
        }
    }
    fclose(fp);//file close
}

void bookTicket()//declare void type function
{
    struct book b;//structure type variable declaration
    FILE *fp;//pointer file declaration
    FILE *ufp;//another pointer file declaration

    int total_seat,mobile,total_amount;//integer type variable declaration
    char name[20],line[80];//character type array declare


    char ch;//character type variable declare
    char movie_code[20];//character type array declare

    fp = fopen("data.txt","r");//opening file for reading
    if(fp == NULL)//
    {
        printf("file does not found !");//print output
        exit(1);//exiting loop
    }
    else
    {
        system("cls");
        while( ( ch = fgetc(fp) ) != EOF )//getting input from file
            printf("%c",ch);//output will be shown which has taken by ch variable

    }
    fclose(fp);//file close

    printf("\n For Book ticket Choice Movie Code From the Above Movie Code\n");//print output
    printf("\n Enter Movie Code :");//print output
    fflush(stdin);//refresh memory
    scanf("%s",&movie_code);//taking input for movie code
    fp = fopen("data.txt","r");//opening file for reading
    if(fp == NULL)//checking condition file
    {
        printf("File does not found !");//print output
        exit(1);//exit loop
    }
    else// another condition part of (fp==NULL)
    {
        while((fgets(line,80,fp)) != NULL)//take data from the fp file and checking condition
        {
            sscanf(line,"%s %s %s %d",b.code,b.name,b.date,&b.cost);//scanning data from the file
            if(strcmp(b.code,movie_code) == 0)//string compare

            {
                printf("\n           Record Found\n");//print output
                printf("\n\t\tMovie Code         ::%s",b.code);//print output
                printf("\n\t\tMovie Name         ::%s",b.name);//print output
                printf("\n\t\tMovie Release Date ::%s",b.date);//print output
                printf("\n\t\tPrice of Ticket    ::%d",b.cost);//print output


                printf("\n\t\t\t*** Fillup These Details  ***");//print output
                printf("\n Customer Name :");//print output
                fflush(stdin);//refresh memory
                scanf("%s",name);//taking input
                printf("\n Mobile Number :");//print output
                fflush(stdin);//refresh memory
                scanf("%d",&mobile);//taking input
                printf("\n Total Number of Ticket(s) :");//print output
                fflush(stdin);//refresh memory
                scanf("%d",&total_seat);//taking input


                total_amount = b.cost * total_seat;//calculating for total amount which is related between b.cost and total_seat

                printf("\n ENJOY MOVIE \n");//print output
                printf("\n\t\tName            : %s",name);//display output
                printf("\n\t\tMobile Number   : 0%d",mobile);//display output
                printf("\n\t\tMovie Name      : %s",b.name);//display output
                printf("\n\t\tTotal Seat(s)   : %d",total_seat);//display output
                printf("\n\t\tCost Per Ticket : %d",b.cost);//display output
                printf("\n\t\tTotal Amount    : %d",total_amount);//display output

                ufp=fopen("oldTransection.txt","a");//opening file for editing and inserting data at last
                if(ufp == NULL)//checking file
                {
                    printf("FILE not Found");//printing out output and will be shown "file not open"
                }
                else//another condition part of if
                {
                    fprintf(ufp,"%s %d %d %d %s %d \n",name,mobile,total_seat,total_amount,b.name,b.cost);//printing data in the file
                    printf("\n Record Insert Successfully to the Old Record FILE");//print output
                }
                printf("\n");//taking new line
                fclose(ufp);//file close

                break;//exit the loop
            }
        }

        if(strcmp(b.code,movie_code) != 0)//compare between b.code string and movie_code string
        {
            printf("\nMovie Not Found.Try with Correct Movie Code");//display output
        }
    }
    fclose(fp);//file has been closed.
}

void oldTransectionHistory()//viewing old transection history
{
    char ch;//character type variable declare
    FILE *fp;//pointer file declaration

    fp = fopen("oldTransection.txt","r");//opening and reading the file
    if(fp == NULL)//checking file
    {
        printf("file does not found !");//print output
        exit(1);//exit loop
    }
    else//another part of if condition
    {
        while( ( ch = fgetc(fp) ) != EOF )//getting input from file
            printf("%c",ch);//output will be shown which has taken by ch variable
    }
    fclose(fp);//file has been closed
}

