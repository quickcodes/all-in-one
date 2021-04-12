#include<stdio.h>
#include<stdlib.h>
// function to display the value of array
void printArray(int* a, int n)
{
    printf("  Sorted array :-\n");
    for(int i=0; i<n; i++)
    {

        printf("  %d,",a[i]);
    }
    printf("\n");
}


//while loop sorting
void bubblesort(int* arr, int size)
{
    int j=0 ;
    int temp=0;
    while(j<5)
    {
        int i=0;     // main quiz
        while(i<5)
        {
            //printf("in k loop\n");
            if(arr[i]>arr[i+1])
            {
                //printf("in if statement\n");
                temp= arr[i];
                arr[i]= arr[i+1];
                arr[i+1]= temp;
            }
        i++;
        }
    j++;
    }

}

// function to sort the array
//for loop sorting
void bubbleSort(int *a, int n)
{
    int temp;
    //int isSorted = 0;
    for(int i=0; i<n-1; i++)
    {
        //printf("Working on pass number %d\n", i+1);
        for(int j=0; j<n-1; j++)
        {
            if(a[j]>a[j+1])
            {
                temp = a[j];
                a[j] = a[j+1];
                a[j+1] = temp;
                //isSorted = 0;
            }
        }
    }
}
// find the length of string
int strlen(char *st)
{
    char *ptr = st;
    int len;
    while(*ptr!='\0')
    {
        len++;
        ptr++;
    }
    return len;
}


void main()
{
    char game;
    int task;
    printf("\n  Hello...\n");


        START:

        printf("  Choose the operation ->\n");
        printf("\n");
        printf("  1 -> I want to arrange the values in assending order.\n");
        printf("  2 -> i want to cheque how many entered numbers are positive or negative..\n");
        printf("  3 -> I want to find the length of your name.\n");
        printf("  4 -> I want find how many year, month, weeks, day, hours you live.\n");
        printf("\n");
        task=0;
        printf("  Enter the operation here : \n  ");
        scanf("  %d",&task);


        // first task
        if(task==1)
        {
            printf("\n  1 task is working\n");

            int i = 0;//, a[100];
            int *ptr;
            //  (type cast)    (space calculation)
            ptr = (int *) malloc(20 * sizeof(int));
            int count = 0;
            printf("  Enter numbers :-)\n  -> ");

            /*
            while (scanf("%d", &a[i]))
            {
                printf("  -> ");
                if (a[i] == '=')
                {
                    printf("\n");
                    break;
                }
                i++;
                count++;
            }
            */
            while (scanf("%d", &ptr[i]))
            {
                printf("  -> ");
                if (ptr[i] == '=')
                {
                    printf("\n");
                    break;
                }
                i++;
                count++;
            }

            printf("\n");

            bubblesort(ptr,count);        //work with while loop
            //bubbleSort(ptr,count);       /// work with for loop
            printArray(ptr,count);
            free(ptr);
        }


        // second case
        else if(task==2)
        {
            printf("\n  2 task is working... (press '=' for exit)\n");

            int number, p = 0, n = 0;

            while (1) {
                printf("   -> ");
                if (scanf("%d", &number) == 0) {
                    printf("Done...\n");
                    break;
                }

                if (number > 0) p++;
                else if (number < 0) n++;
                else break; /* 0 given */
            }

            printf("  Read %d positive and %d negative numbers\n", p, n);
        }


        // third task
        else if(task == 3)
        {
            char name[20];
            printf("  Enter your Name.\n  ");
            scanf("%s",&name);

            int l = strlen(name);
            printf("  The length of name is %d\n",l);

        }


        // third task
        else if(task == 4)
        {
                int bd;
                int bm;
                int by;


                int day=0,month=0,year=0;




                printf("\n");
                printf("\tEnter your birthday (DD/MM/YYYY)\n");

                printf("\tDD -> ");
                scanf("%d",&bd);

                printf("\tMM -> ");
                scanf("%d",&bm);

                printf("\tYYYY -> ");
                scanf("%d",&by);
                printf("\n");

                int cd;
                int cm;
                int cy;

                printf("\n");
                printf("\tEnter current date (DD/MM/YYYY)\n");

                printf("\tDD -> ");
                scanf("%d",&cd);

                printf("\tMM -> ");
                scanf("%d",&cm);

                printf("\tYYYY -> ");
                scanf("%d",&cy);
                printf("\n");


                //calculate days
                if(cd>=bd){
                    day=cd-bd;
                }
                else if(bd>cd)
                {
                    day=(30+cd)-bd;
                    cm = cm- 1;
                }
                else {
                    printf("\terror found");
                }



                // calculate months
                if(cm>=bm)
                {
                    month=cm-bm;
                }
                else if(bm>cm)
                {
                    month=(12+cm)- bm;
                    cy = cy- 1;
                }

                else{
                    printf("\terror found");
                }


                // calculate year
                year=cy-by;


                printf("\tyou live (DD/MM/YY) ->  %d,%d,%d\n",day,month,year);


                int Tday = day + (month*30) + (year * 365);
                int Tmonth = month + (year * 12);
                int weeks = Tday / 7;
                int hours = Tday * 24;

                printf("\tYour live more than -> %d+ <- years \n",year);
                printf("\tYour live more than -> %d+ <- month \n",Tmonth);
                printf("\tYour live more than -> %d+ <- weeks \n",weeks);
                printf("\tYour live more than -> %d+ <- days \n",Tday);
                printf("\tYour live more than -> %d+ <- hours \n",hours);
                printf("\n\t **********BE THANK FULL********* ");
                printf("\n\t      **********AND*********      ");
                printf("\n\t  **********SAY AWEOSME*********  ");

                    }

        // last task
        else
        {
            printf("\n  Please choose correct operation\n");

        }

        // restart the game
        char a;
        printf("\n\tPRESS '1' TO PLAY MORE : ");
        a = getch();
        if(a==1){
            goto START;
        }
        else printf("\n\t On the way to success\n");
        getch();
}
