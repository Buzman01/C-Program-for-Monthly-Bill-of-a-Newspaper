# C-Program-for-Monthly-Bill-of-a-Newspaper
Algorithm for to calculate monthly bill of newspaper
#include<stdio.h>

int main()
{
    int no_of_days;
    float paper_per_day_cost, total_bill, service_charge;
    char service;

    // Read the Number of days paper delivered
    printf("Enter the number of days paper delivered:");
    scanf("%d", &no_of_days);
    //Number of days must be greater than 0 to calculate price
    if(no_of_days <= 0 || no_of_days > 31 )
    {
        printf("No paper bill for the month or wrong data entered.");
    }
    else
    {
        printf("Enter the paper cost per day:");
        scanf("%f", &paper_per_day_cost);

        // Paper cost must be greater than zero
        if(paper_per_day_cost<=0)
        {
            printf("Your paper bill is 0.");
        }
        else
        {
            // Service Charge is optional, add service charge if required
            printf("Do you have service charge? Enter Y or N :");
            scanf("%s", &service);

            if(service=='Y' || service=='y')
            {
                printf("Enter Service Charge : ");
                scanf("%f", &service_charge);
                total_bill = service_charge + no_of_days * paper_per_day_cost;
            }
            else
            {
                total_bill = no_of_days * paper_per_day_cost;
            }
            printf("Total bill is : $%0.2f", total_bill);
        }
    }
    return 0;
}
