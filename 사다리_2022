// 1. 처음 풀 때는 어떻게든 수학적으로 식을 찾으려고 많이 생각하고 적어봤지만 식이 깔끔하게 정리가 되지 않음
// 2. 대입하는 방법으로 접근
//    (1) 숫자 대입을 적게하는 방법을 생각하다가 simulated anealing 처럼 처음에는 크게크게 숫자를 바꾸다가
//        숫자가 좀 작아지면 0.001씩 더하거나 빼는 식으로 접근했는데 시간초과 나옴
//    (2) 어떻게 접근해야하나 찾다가 다른 사람들이 '이분탐색'으로 풀었다길래 찾아서 적용함.
//        계속 답이 존재하는 범위를 줄여나가는 식으로 답을 찾는 방식, 신기했고 대학에서 수치해석학 배우는데 거기서 배운
//        구간법이라는 방법과 거의 같았음. 


#include <stdio.h>
#include <math.h>
#define min(x,y) ((x) < (y)? (x):(y))
#define max(x,y) ((x) > (y)? (x):(y))


int main() {
    long double a, b, c; scanf("%Lf %Lf %Lf", &a, &b, &c);
    
    long double y = min(a,b), x = max(a,b);
    long double w1_start = 0, w1_end = y, w1 = 0, w2 = 0;
    
    while(true) {
    
    w1 = (w1_start+w1_end)/2;
    w2 = w1*(y-(sqrt(w1*w1 + c*c)))/sqrt(w1*w1 + c*c);
    
    long double h1 = sqrt(x*x - (w1+w2)*(w1+w2)), h2 = sqrt(y*y - (w1+w2)*(w1+w2));
    long double predicted_c= h1*h2/(h1+h2);
    
    if (c < predicted_c) w1_start = w1;
    else w1_end = w1;
    
    if (abs(c-predicted_c) < 0.001 || (float) w1_start == (float) w1_end) break;
    }
    printf("%Lf\n", w1 + w2);
}
