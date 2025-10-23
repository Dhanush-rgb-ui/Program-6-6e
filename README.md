# Module-6 SEB
## AIM:
Create a structure for eb calculation bill for 3 Customers(use customer no,prev reading & curre reading as input) using nested structure ( first 100 unit 2 Rs per unit ,101 to 200 rs.3 per unit and above 200 rs 5 per unit).

## For example:

## Program:
```c
#include<stdio.h>
struct Read{
    int prev;
    int current;
};
struct EB{
    int cusno;
    struct Read read;
    int units;
    float bill;
};
float calbill(int units){
    float amount=0;
    if(units<=100){
        amount+=units*2;
    }
    else if(units>100 && units<=200){
        amount+=(100*2)+((units-100)*3);
    }
    else{
        amount+=(100*2)+(100*3)+((units-200)*5);
    }
    return amount;
}
int main(){
    struct EB c[3];
    int i;
    for(i=0;i<3;i++){
        scanf("%d",&c[i].cusno);
        scanf("%d",&c[i].read.prev);
        scanf("%d",&c[i].read.current);
        c[i].units=c[i].read.current-c[i].read.prev;
        c[i].bill=calbill(c[i].units);
    }
    printf("Details of the EB Customer\n");
    for(i=0;i<3;i++){
        printf("%d      %.2f\n",c[i].cusno,c[i].bill);
    }
    return 0;
}
```
## Result:
