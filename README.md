# BaiTap

#include<iostream>
#define max 1000
using namespace std;
//nhap mang
void NhapMang(int A[], unsigned int n) {

    for(int i = 1; i<=n; i++)
    {
        cout <<"điểm của sinh viên thứ "<< i << ":";
        cin >> A[i];
    }
}

//dem so lan xuat hien 
unsigned int Count(int A[], unsigned int n, int x){
    unsigned int temp = 0;
    for(int i = 1; i<=n; i++)
        if(A[i]==x)
            temp++;
    return temp;
}
//tim phan tu xuat hien nhat lan nhat trong mang
unsigned int Count(int A[], unsigned int n) {
    unsigned int temp1, temp = Count(A,n,A[0]), index = 0;
    for(int i = 1; i<n; i++)
    {
        temp1 = Count(A,n,A[i]);
        if(temp<temp1)
        {
            temp = temp1;
            index = i;
        }
    }
    return A[index];
}

//coded by QuangNguyen

int main(){
    int B[max];
    unsigned int n;
    cout <<"Nhap n = ";
    cin >>n;
    NhapMang(B,n);
    cout <<"\nĐiểm có tần suất lớn nhất là:"<<Count(B,n)<<""<<endl;
    return 0;
}
