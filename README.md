# Cnek
#include<stdio.h>
#include<conio.h>
#include<malloc.h>
 	void Init(int *B, int n){
 		for (int i=0;i<n; i++){
 			printf("Nhap phan tu thu %d : ",i+1);
 			scanf("%d",(B+i));
		}
	}
	void Display(int *B, int n){
 		for (int i=0;i<n; i++){
 			printf("%d\t",*(B+i));	
		}
	}
 	float Average(int *B,int n) {
 		float A=0;
		for (int i=0;i<n; i++){
 			A=A+*(B+i);
 		}
 		return A/n;
	}
	void Dec(int *B,int n) {
		for (int i = 0; i < n ; i++){
			for (int j = i+ 1; j<n;j++){
				if(*(B + i)> *(B + j)){
					int temp = *(B+j);
					*(B+i) = *(B+j);
					*(B+j) = temp;
				}
			}
		}
	}
 int main(){
 	int n;
 	printf("Nhap so phan tu cua mang : ");
 	scanf("%d",&n);
 	int *B;
 	B= (int *)malloc(n*sizeof(int));
 	Init(B,n);
 	Display(B,n);
 	printf("\nTrung binh cong gia tri cac phan tu trong mang: %f\n", Average(B,n));
 	printf("Sap xep mang theo trat tu tang dan: ");
 	Dec(B,n);
	Display(B,n);
	
}
