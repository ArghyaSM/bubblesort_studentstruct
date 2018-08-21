#include<stdio.h>
struct stud
{
    char name[30];
    int roll;
    float marks;
}
main()
{
    struct stud stuar[100], swap;
    int i,j,n;
    printf("\n Enter the number of students- ");
    scanf("%d",&n);
    printf("\n Enter student details: \n ");
    for(i=0;i<n;i++)
    {
        printf("\n Enter Name, Roll No. & Marks of student %d- ",(i+1));
        scanf("%s%d%f",&stuar[i].name,&stuar[i].roll,&stuar[i].marks);
    }
    for(j=0;j<n-1;j++)
    {
        for(i=0;i<n-j-1;i++)
        {
            if(stuar[i].marks>stuar[i+1].marks)
            {
                swap=stuar[i];
                stuar[i]=stuar[i+1];
                stuar[i+1]=swap;
            }
        }
    }
    printf("\n The sorted list of students according to their marks : \n");
    for(i=0;i<n;i++)
        printf("\n %d\tName - %s\n\tRoll No.- %d\n\tMarks- %f\n\n",(i+1),stuar[i].name,stuar[i].roll,stuar[i].marks);
}
