# Find-the-area
# c program
# It is a machine that outputs the area using struct() in the order of triangle, rectangle, and circle. Input the width and height of the rectangle, the area of ​​the rectangle is output, then the radius of the circle is input and the area of ​​the circle is output. 삼각형,사각형,원 순서로 struct()를 이용해서 면적을 출력하는 기계로사각형을 가로,세로를 입력하고 사각형의면적이 출력되고 그다음인 원의 반지름을 입력하고 원의 면적이 출력된다.
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <string.h>
struct shape{
	int type;
	union{
		struct{
			int b,h;}tri;
		struct{
			int w,h;}rect;
	    struct{
	    	int r;}circ;
	}data;
};
int main(void){
	struct shape s;
	printf("도형의 타입을 입력하시오(0,1,2):");
	scanf("%d",&s.type);
	switch(s.type){
		case 0:
			printf("밑변과 높이 입력:");
			scanf("%d %d",&s.data.tri.b,&s.data.tri.h);
			printf("면적은 %d\n",(int)(s.data.tri.b*s.data.tri.h/2));
		case 1:
			printf("가로와 세로 입력:");
			scanf("%d %d",&s.data.rect.w,&s.data.rect.h);
			printf("면적은 %d\n",(int)(s.data.rect.w*s.data.rect.h));
		case 2:
			printf("반지름 입력:");
			scanf("%d",&s.data.circ.r);
			printf("면적은 %d\n",(int)(3.14*s.data.circ.r*s.data.circ.r));
		default:
			break;
	}
    return 0;
}
#result--> 도형의 타입 입력(0,1,2):1  가로와 세로 입력:100 200  반지름 입력:2 면적은 12
