# Calculator in c language
This Calculator Perform Basic Artimetic problem 


#include <stdio.h>
#include <math.h>

void basic_problem(){

  printf("\n 0 ----> Sum(+) \n\n 1 ----> Minus(-) \n\n 2 ----> Multiply(*) \n\n 3 ----> Divide(/) \n\n");



  int fun, n, value,sum=0,minus=0;
  double divide, multiply=1.0;

  printf("Enter the Function : ");
  scanf("%d",&fun);



    if(fun==0){

      // Input the number of values
      printf("\nEnter the number of values for Performing : ");
      scanf("%d", &n);

      printf("\n<-------Sum Function Activate------>\n\n");

      // Input the values and calculate the sum
      for (int i = 1; i <= n; i++) {
          printf("Enter The %d value for sum : ", i);
          scanf("%d", &value);
          sum += value;
      }

      printf("\nThe sum of all the entered values is: %d\n", sum);
    } // Sum Function
    else if(fun==1){
      // Input the number of values
      printf("Enter the number of values for Performing : ");
      scanf("%d", &n);

      printf("\n<-------Minus Function Activate------>\n\n");

      // Input the values and calculate the minus
      for (int i = 1; i <= n; i++) {
          printf("Enter The %d value for Minus: ", i);
          scanf("%d", &value);
          minus -= value;
      }

      printf("\nThe Minus of all the entered values is: %d\n", minus);
    } // Minus Function
    else if(fun==2){
      // Input the number of values
      printf("Enter the number of values: ");
      scanf("%d", &n);

      // Input the values and calculate the multiply
      for (int i = 1; i <= n; i++) {
          double value;
          printf("Enter value %d: ", i);
          scanf("%lf", &value);
          multiply *= value;
      }

      printf("The sum of the entered values is: %lf\n", multiply);
    } // Multiply Function
    else if(fun==3){

      // Input the number of values
      printf("Enter the number of values: ");
      scanf("%d", &n);
      // Check if there are at least two values for division
      if (n < 2) {
          printf("Error: At least two values are needed for division.\n");
          divide = 1; // Exit with an error code
      }
      // Input the first value
      printf("Enter the first value: ");
      scanf("%lf", &divide);
      // Input the remaining values and perform division
      for (int i = 2; i <= n; i++) {

          double value;
          printf("Enter value %d: ", i);
          scanf("%lf", &value);

          // Check if the denominator is not zero
          if (value != 0) {
              divide /= value;
          } else {
              printf("Error: Division by zero is undefined.\n");
              divide = 1; // Exit with an error code
          }
      }
          printf("Result of division: %lf\n", divide);    
    } // Divide Function 
  else{

    printf("Error: Invalid operator entered.\n");
  }
}// Basic Problem
void factorial() {

  int num, fac = 1;

  printf("\nEnter the number for factorial : ");
  scanf("%d", &num);

  if (num < 0) {
    printf("\nFactorial for %d is not define ", num);
  } else {
    for (int i = 1; i <= num; i++) {
      fac *= i;
    }
    printf("\nFactorial of %d is %d \n", num, fac);
  }

} // FACTORIAL NUMBER
void prime_num() {
  int num, result = 0;

  printf("\nEnter a Number : ");
  scanf("%d", &num);

  if (num <= 1) {
    result = 1;
  } else {
    for (int j = 2; j * j <= num; j++) {
      if (num % j == 0) {
        result = 1;
      }
    }
  }
  if (result == 0) {
    printf("\n%d is Prime number \n", num);
  } else {
    printf("\n%d is not a Prime number \n", num);
  }

} // PRIME NUMBER
void reverse_num() {

  int num, reverse = 0, org, r;
  org = num;

  printf("\nEnter the number : ");
  scanf("%d", &num);

  while (num != 0) {
    r = num % 10;
    reverse = reverse * 10 + r;
    num /= 10;
  }
  printf("\nThe Reverseof %d is %d\n", org, reverse);

} // REVERSE NUMBER
void armstrong_num() {

  int num, arm = 0, org, r;

  printf("\nEnter the Number : ");
  scanf("%d", &num);
  org = num;

  while (num != 0) {
    r = num % 10;
    arm += r * r * r;
    num /= 10;
  }

  if (arm == org) {
    printf("\n%d is a Armstrong Number \n", org);
  } else {
    printf("\n%d is not a Armstrong Number \n", org);
  }

} // ARMSTRONG NUMBER
void pallindome_num() {
  int num, org, r, reverse = 0;

  printf("\nEnter the number : ");
  scanf("%d", &num);

  org = num;

  while (num != 0) {
    r = num % 10;
    reverse = reverse * 10 + r;
    num /= 10;
  }
  if (reverse == org) {
    printf("\n%d is  Pallindrome \n", org);
  } else {
    printf("\n%d is not Pallindrome \n", org);
  }

} // PALLINDROME NUMBER
void perfect_num() {
  int num, r, sum = 0;

  printf("\n Enter the Number : ");
  scanf("%d", &num);

  for (int i = 1; i < num; i++) {
    r = num % i;
    if (r == 0) {
      sum += i;
    }
  }
  if (sum == num)
    printf("\n %d is a Perfect Number \n", num);
  else
    printf("\n %d is not a Perfect Number \n", num);
} // PERFECT NUMBER 
void nCr(){
  printf("\nFirs We Know Formula of nCr = n! / (r! * (n - r)!)\n");

  int n, r;
  float nCr=1;
  printf("\nEnter the value of n : ");
  scanf("%d", &n);

  printf("\nEnter the value of r : ");
  scanf("%d", &r);

  // Calculate n!
  for (int i = 1; i <= n; i++) {
      nCr*= i;
  }

  // Calculate (n-r)!
  for (int i = 1; i <= n - r; i++) {
      nCr/= i;
  }

  // Calculate r!
  for (int i = 1; i <= r; i++) {
      nCr/= i;
  }

   printf("\nnCr is: %f\n", nCr);

} // nCr Formula
void sine_series(){

  double x, result = 0.0;
  int n;


  printf("\nEnter the value of x in radians: ");
  scanf("%lf", &x);

  printf("\nEnter the number of terms (n) in the series: ");
  scanf("%d", &n);

  // Calculate sine using Taylor series expansion
  for (int i = 0; i < n; i++) {
      int exponent = 2 * i + 1;
      double term = pow(-1, i) * pow(x, exponent) / tgamma(exponent + 1);
      result += term;
  }

  printf("\nsin(%lf) is approximately: %lf \n", x, result);
} // Sine seris
void cosine_series(){
  double x, result = 0.0;
  int n;

  // Input values for x and n
  printf("\nEnter the value of x in radians: ");
  scanf("%lf", &x);

  printf("\nEnter the number of terms (n) in the series: ");
  scanf("%d", &n);

  // Calculate cosine using Taylor series expansion
  for (int i = 0; i < n; i++) {
      int exponent = 2 * i;
      double term = pow(-1, i) * pow(x, exponent) / tgamma(exponent + 1);
      result += term;
    }

    printf("\ncos(%lf) is approximately: %lf \n", x, result);
} // cosine series
void star_pattern(){

  int n,space,i,j;

  printf("\nEnter the row : \n");
  scanf("%d",&n);

  for (i = 1; i <= n; i++) {
      // Loop to print spaces before the stars
      for (space = 1; space <= n - i; space++) {
          printf(" ");
      }
      // Loop to print stars in each row
      for (j = 1; j <= 2 * i - 1; j++) {
          printf("*");
      }
      // Move to the next line after each row
      printf("\n");
  }



} // Triangle star pattern
void matrix_add(){

  int arry[50][50],arry1[50][50],sum[50][50];
  int i ,j,n;


  printf("enter the size(3X3,2X2,etc ) of array : ");
  scanf("%d",&n);


  for(i=0;i<n;i++){
    for(j=0;j<n;j++){
      printf("Enter the [%d][%d] element for first array : ",i,j);
      scanf("%d",&arry[i][j]);
    }

  }
  for(i=0;i<n;i++){
    printf("\n");
    for(j=0;j<n;j++){
      printf("%d\t",arry[i][j]);

    }   


  }
   printf("<------------------> Your First matrix is  <------------------> ");
  printf("\n\n\n");

  for(i=0;i<n;i++){
    for(j=0;j<n;j++){
      printf("Enter the [%d][%d] element for second array : ",i,j);
      scanf("%d",&arry1[i][j]);
    }

  }
  for(i=0;i<n;i++){
    printf("\n");
    for(j=0;j<n;j++){
      printf("%d\t",arry1[i][j]);

    }
  }
  printf("<------------------> Your Second matrix is  <------------------> ");
  printf("\n\n\n");


  for(i =0;i<n;i++){
    for(j=0;j<n;j++){
      sum[i][j]=arry1[i][j]+arry[i][j];
    }
  }

  printf("<------------------> The Addition of two matrix is :<------------------> ");
  printf("\n\n\n");

  for(i =0;i<n;i++){
    printf("\n");
    for(j=0;j<n;j++){
      printf("%d\t",sum[i][j]);
    }
  }
  printf("\n\n\n");


}// matrix addition for two matrix 
void matrix_subt(){

  int arry[50][50],arry1[50][50],sum[50][50];
  int i ,j,n;


  printf("enter the size(3X3,2X2,etc ) of array : ");
  scanf("%d",&n);


  for(i=0;i<n;i++){
    for(j=0;j<n;j++){
      printf("Enter the [%d][%d] element for first array : ",i,j);
      scanf("%d",&arry[i][j]);
    }

  }
  for(i=0;i<n;i++){
    printf("\n");
    for(j=0;j<n;j++){
      printf("%d\t",arry[i][j]);

    }   


  }
   printf("<------------------> Your First matrix is  <------------------> ");
  printf("\n\n\n");

  for(i=0;i<n;i++){
    for(j=0;j<n;j++){
      printf("Enter the [%d][%d] element for second array : ",i,j);
      scanf("%d",&arry1[i][j]);
    }

  }
  for(i=0;i<n;i++){
    printf("\n");
    for(j=0;j<n;j++){
      printf("%d\t",arry1[i][j]);

    }
  }
  printf("<------------------> Your Second matrix is  <------------------> ");
  printf("\n\n\n");


  for(i =0;i<n;i++){
    for(j=0;j<n;j++){
      sum[i][j]=arry1[i][j]-arry[i][j];
    }
  }

  printf("<------------------> The Subtraction of two matrix is <------------------> ");
  printf("\n\n\n");

  for(i =0;i<n;i++){
    printf("\n");
    for(j=0;j<n;j++){
      printf("%d\t",sum[i][j]);
    }
  }
  printf("\n\n\n");


}// matrix Subtraction for two matrix 

void matrix_mult(){

  
  // Declare matrices and variables
  int arr1[50][50], brr1[50][50], crr1[50][50], i, j, k, r1, c1, r2, c2, sum = 0;

  // Display multiplication of two matrices
  printf("\n\nMultiplication of two Matrices :\n");
  printf("----------------------------------\n");

  // Input rows and columns of the first matrix
  printf("\nInput the rows and columns of the first matrix: ");
  scanf("%d %d", &r1, &c1);

  // Input rows and columns of the second matrix
  printf("\nInput the rows and columns of the second matrix: ");
  scanf("%d %d", &r2, &c2);

  // Check if multiplication is possible
  if (c1 != r2) {
        printf("Multiplication of matrices is not possible.\n");
        printf("Column of the first matrix and row of the second matrix must be the same.\n");
    } else {
        // Input elements in the first matrix
        printf("Input elements in the first matrix:\n");
        for (i = 0; i < r1; i++) {
            for (j = 0; j < c1; j++) {
                printf("element - [%d],[%d] : ", i, j);
                scanf("%d", &arr1[i][j]);
            }
        }

        // Input elements in the second matrix
        printf("Input elements in the second matrix:\n");
        for (i = 0; i < r2; i++) {
            for (j = 0; j < c2; j++) {
                printf("element - [%d],[%d] : ", i, j);
                scanf("%d", &brr1[i][j]);
            }
        }

        // Display the first matrix
        printf("\nThe First matrix is:\n");
        for (i = 0; i < r1; i++) {
            printf("\n");
            for (j = 0; j < c1; j++)
                printf("%d\t", arr1[i][j]);
        }

        // Display the second matrix
        printf("\nThe Second matrix is:\n");
        for (i = 0; i < r2; i++) {
            printf("\n");
            for (j = 0; j < c2; j++)
                printf("%d\t", brr1[i][j]);
        }

        // Matrix multiplication
        for (i = 0; i < r1; i++) { // Row of first matrix
            for (j = 0; j < c2; j++) { // Column of second matrix
                sum = 0;
                for (k = 0; k < c1; k++)
                    sum = sum + arr1[i][k] * brr1[k][j];
                crr1[i][j] = sum;
            }
        }

        // Display the result of matrix multiplication
        printf("\nThe multiplication of two matrices is:\n");
        for (i = 0; i < r1; i++) {
            printf("\n");
            for (j = 0; j < c2; j++)
                printf("%d\t", crr1[i][j]);
        }
    }
    printf("\n\n");
}

/*<----------HELLO JI ---------->*/
int main() {

  /* CALCULATOR FOR VARIOUS PROBLEM  */
  int calculator_option;

  printf("\n<-------------------------------CHOSE A TYPE OF CALCULATOR IN THE GIVEN OPTION-------------------------------> \n\n 0 ----> Basic Calculator \n\n 1 ----> for Factorial \n\n 2 ----> for checking Prime "
         "number \n\n 3 ----> For Reverse Number \n\n 4 ----> For Checking Armstrong  \n\n 5 ----> For Checking Pallindrome number \n\n 6 ----> For Checking "
         "Perfect Number \n\n 7 ----> For nCr Formula \n\n 8 ----> For Sines Series \n\n 9 ----> For Cosine Series \n\n 10 ----> For Triangle Star Pattern \n\n 11 ----> For matrix addition  \n\n 12 ----> For matrix subtraction \n\n 13 ----> For matrix multiplication \n\n");
  printf("\nEnter your Option : ");
  scanf("%d", &calculator_option);

  switch (calculator_option) {
  case 0:
    printf("\n<---------------Basic Calculator--------------->\n");
    basic_problem();
    break;  
  case 1:
    printf("\n<---------------For Factorial--------------->\n");
    factorial();
    break;
  case 2:
    printf("\n<---------------For Checking Prime Number--------------->\n");
    prime_num();
    break;
  case 3:
    printf("\n<---------------For Reverse Number--------------->\n");
    reverse_num();
    break;
  case 4:
    printf("\n<---------------For Checking Armstrong Number--------------->\n");
    armstrong_num();
    break;
  case 5:
    printf("\n<---------------For Checking Paalindrome Number--------------->\n");
    pallindome_num();
    break;
  case 6:
    printf("\n<---------------For Checking Perfect Number--------------->\n");
    perfect_num();
    break;
  case 7:
    printf("\n<---------------For nCr --------------->\n");
    nCr();
    break;
  case 8:
    printf("\n<---------------For Sine Series --------------->\n");
    sine_series();
    break;
  case 9: 
    printf("\n<---------------For Cosine Series --------------->\n");
    cosine_series();
    break;
  case 10 :
    printf("\n<---------------For Triangle Star Pattern --------------->\n");
    star_pattern();
    break;
  case 11 :
  printf("\n<---------------For Matrix Addition  --------------->\n");
  matrix_add();
  break;
  case 12 :
  printf("\n<---------------For Matrix Subtraction  --------------->\n");
  matrix_subt();
  break;
  case 13 :
  printf("\n<---------------For Matrix Multiplication  --------------->\n");
  matrix_mult();
  break;
  default:
    printf("<---------------Invalid Option( Please Write in Capital "
           ")---------------> \n");
  }

  printf("\n<--------------------------------------------------Thank You-------------------------------------------------->\n");

  return 0;
}
