#include<iostream>
#include<string.h>
#include<iomanip>
#include<fstream>
using namespace std;
struct nhanvien
{
	int mnv;
	string hoten,gioitinh,phongban,thidua;
	float ngaycong;
	float luong;
	float phucap;
	float thuclinh;
};
nhanvien nv[100];

//Nhap
void nhap(nhanvien nv[], int n)
{
	for(int	i=0;i<n;i++)
	{
	cout<<"\nNhan vien thu: "<<i+1<<""<<endl;
	cout<<"Ma nhan vien: "<<i+1<<":";cin>>nv[i].mnv;
	fflush(stdin);//xoa bo nho dem
	cout<<"Ho ten nhan vien: ";getline(std::cin,nv[i].hoten);
	cout<<"Gioi tinh(Nam/Nu): ";getline(std::cin,nv[i].gioitinh);
	fflush(stdin);
	cout<<"Ngay Cong: ";cin>>nv[i].ngaycong;
	fflush(stdin);
	cout<<"Phong Ban: ";getline(std::cin,nv[i].phongban);
	fflush(stdin);
	cout<<"Luong: ";cin>>nv[i].luong;
	fflush(stdin);
	cout<<"Phu Cap: ";cin>>nv[i].phucap;
	fflush(stdin);
	cout<<"Thi Dua: ";getline(std::cin,nv[i].thidua);
	nv[i].thuclinh=(nv[i].luong+nv[i].phucap);
	cout<<"Thuc Linh la: "<<nv[i].thuclinh<<endl;
	fflush(stdin);
}
}
//HienThi
void xuat(nhanvien nv[],int n)
{
 cout <<"STT\tMNV\tHo va ten\tGioi tinh\tNgay Cong\tPhong Ban\tLuong\tPhu Cap\t\tThi Dua\tThuc Linh";
	for(int i=0; i<n ;i++){
		cout<<"\n"<<i + 1;				
        cout<<"\t"<<nv[i].mnv ;
        cout<<"\t"<<nv[i].hoten;
        cout<<"\t"<<nv[i].gioitinh;
        cout<<"\t\t"<<nv[i].ngaycong;
        cout<<"\t"<<nv[i].phongban<<"\t\t"<<nv[i].luong<<"\t"<< nv[i].phucap;
        cout<<"\t\t"<<nv[i].thidua;
        cout<<"\t"<<nv[i].thuclinh<<endl;
    }
	}
	/*{
		cout<<""<<setw(23)<<nv[i].mnv<<setw(25)<<nv[i].hoten;
		cout<<""<<setw(12)<<nv[i].gioitinh<<setw(10)<<nv[i].ngaycong;
		cout<<""<<setw(10)<<nv[i].phongban<<setw(10)<<nv[i].luong;
		cout<<""<<setw(10)<<nv[i].phucap<<setw(10)<<nv[i].thidua<<setw(9)<<nv[i].thuclinh<<endl;
	}*/

//XepLoaiThiDua
void Thidua(nhanvien nv[],int n)
{
	for(int i=0; i<n ;i++)
	{
		if(nv[i].ngaycong>=26)
	{
			cout<<setw(10)<<nv[i].hoten<<" Ngay cong >= 26 Loai =>>2 Xuat Sac."<<endl;
	}
	else if (nv[i].ngaycong>=23)
	{
		cout<<setw(10)<<nv[i].hoten<<" Ngay cong >= 23 Loai =>> Tot."<<endl;
	}
	else if (nv[i].ngaycong<23)
	{
		cout<<setw(10)<<nv[i].hoten<<" Ngay cong < 23 Loai =>> KhongDat."<<endl;
	}
	}
}
//XetLoaiPhuCapCaoThap
void phucapMinMax(nhanvien nv[],int n)
{
	float min=nv[0].phucap;
	float max=nv[0].phucap;
	for(int i=0; i<n ;i++)
	{
		if(nv[i].phucap<min);
		{
			min=nv[i].phucap;
		}
	}
	cout<<"\n Phu cap thap nhat la: "<<min<<endl;
	for(int i=0; i<n ;i++)
	{
		if(nv[i].phucap>max);
		{
			max=nv[i].phucap;
		}
	}
	cout<<"\n Phu cap cao nhat la: "<<max<<endl;
}
//Luongcaonhat
void luongmax(nhanvien nv[],int n)
{
	float max=0;
	for(int i=0; i<n ;i++)
	{
		if(nv[i].luong>max);
		{
			max=nv[i].luong;
		}
	}
	cout<<"\n Nhan vien co luong cao nhat: "<<max<<endl;
}
//sapxepdanhsachnhanvien
void sapxep(nhanvien nv[],int n)
{
	nhanvien tg;
	for(int i=0; i<n ;i++)
	{
		for(int j=i+1;j<n;j++)
		{
			if(nv[i].phucap>nv[j].phucap)
			{
				tg= nv[i];
				nv[i]=nv[j];
				nv[j]=tg;
			}
		}
	}
	cout<<"\nSau khi sap xep la: "<<endl;
	for(int i=0; i<n ;i++)
	{
	cout <<"STT\tMNV\tHo va ten\tGioi tinh\tNgay Cong\tPhong Ban\tLuong\tPhu Cap\t\tThi Dua\tThuc Linh";
	    cout<<"\n"<<i + 1;				
        cout<<"\t"<<nv[i].mnv ;
        cout<<"\t"<<nv[i].hoten;
        cout<<"\t"<<nv[i].gioitinh;
        cout<<"\t\t"<<nv[i].ngaycong;
        cout<<"\t"<<nv[i].phongban<<"\t\t"<<nv[i].luong<<"\t"<< nv[i].phucap;
        cout<<"\t\t"<<nv[i].thidua;
        cout<<"\t"<<nv[i].thuclinh<<endl;
	}
}
void nv5tr(nhanvien nv[],int n)
{
	for(int i=0; i<n ;i++)
	{
		if(nv[i].thuclinh>5000)
		{
	    cout<<""<<setw(23)<<nv[i].mnv<<setw(18)<<nv[i].hoten;
		cout<<""<<setw(12)<<nv[i].gioitinh<<setw(13)<<nv[i].ngaycong;
		cout<<""<<setw(11)<<nv[i].phongban<<setw(12)<<nv[i].luong;
		cout<<""<<setw(10)<<nv[i].phucap<<setw(10)<<nv[i].thidua<<setw(9)<<nv[i].thuclinh<<endl;		
		}
	}
}
//TimKiemNhanVien
void Search(nhanvien nv[],int n)
{
	int z;
	cout<<"\nNhap ma nhan vien can tim: ";cin>>z;
	for(int i=0; i<n ;i++)
	{
		if(nv[i].mnv==z)
		{
	cout <<"STT\tMNV\tHo va ten\tGioi tinh\tNgay Cong\tPhong Ban\tLuong\tPhu Cap\t\tThi Dua\tThuc Linh";
		cout<<"\n"<<i + 1;				
        cout<<"\t"<<nv[i].mnv ;
        cout<<"\t"<<nv[i].hoten;
        cout<<"\t"<<nv[i].gioitinh;
        cout<<"\t\t"<<nv[i].ngaycong;
        cout<<"\t"<<nv[i].phongban<<"\t\t"<<nv[i].luong<<"\t"<< nv[i].phucap;
        cout<<"\t\t"<<nv[i].thidua;
        cout<<"\t"<<nv[i].thuclinh<<endl;		
		}
	}
}

//hammain
int  main()
{
	int key;
	int option,n;
    

	cout<<"Nhap so luong nhan vien: ";cin>>n;
	while(n>0)
	{
		cout<<"\tCHUONG TRINH QUAN LY NHAN VIEN.\t"<<endl;;
		cout<<"========================MENU========================\n";
		cout<<"==                                                ==\n";
		cout<<"==    1.Nhap thong tin nhan vien                  ==\n";
		cout<<"==    2.In ra danh sach nhan vien                 ==\n";
		cout<<"==    3.Xep loai nhan vien                        ==\n";
		cout<<"==    4.Danh sach phu cap Min,Max                 ==\n";
		cout<<"==    5.Nhan vien co luong Max                    ==\n";
		cout<<"==    6.Sap xep nhan vien                         ==\n";
		cout<<"==    7.Danh sach nhan vien co phu cap tren 5tr   ==\n";
		cout<<"==    8.Tim kiem nhan vien theo mnv               ==\n";
		cout<<"==    0.Exit                                      ==\n";
		cout<<"==                                                ==\n";	
		cout<<"====================================================\n";
		cout<<"Hay nhap tuy chon cua ban: ";
		cin>>option;
		switch(option)
		{
			case 1:
				cout<<"*Moi ban nhap thong tin nhan vien:\n";
				nhap(nv,n);
				cout<<"Bam phim bat ky de tiep tuc\n";
				system("pause");
				break;
			case 2:
				if(n>0)
				cout<<"Danh sach nhan vien la:\n";
				xuat(nv,n);
				cout<<"Bam phim bat ky de tiep tuc";
				system("pause");
				break;
			case 3:
				if(n>0)
				cout<<"Xep loai nhan vien:\n";
				Thidua(nv,n);
				cout<<"Bam phim bat ky de tiep tuc";
				system("pause");
				break;
			case 4:
				if(n>0)
				cout<<"Danh sach phu cap Max,Min:\n";
				phucapMinMax(nv,n);
				cout<<"Bam phim bat ky de tiep tuc";
				system("pause");
				break;
			case 5:
				if(n>0)
				cout<<"Nhan vien co luong cao nhat:\n";
				luongmax(nv,n);
				cout<<"Bam phim bat ky de tiep tuc";
				system("pause");
				break;
			case 6:
				if(n>0)
				cout<<"Sap xep nhan vien:\n";
				sapxep(nv,n);
				cout<<"Bam phim bat ky de tiep tuc";
				system("pause");
				break;
			case 7:
				if(n>0)
				cout<<"Danh sach nhan vien co thuc linh tren 10tr:\n";
				nv5tr(nv,n);
				cout<<"Bam phim bat ky de tiep tuc";
				system("pause");
				break;
			case 8:
				if(n>0)
			    Search(nv, n);
				cout<<"Bam phim bat ky de tiep tuc";
				system("pause");
				break;
			
                    break;
			case 0:
                cout << "\nBan da chon thoat chuong trinh!";
            
                return 0;
            default:
                cout << "\nKhong co chuc nang nay!";
                cout << "\nHay chon chuc nang trong hop menu.";
                system("pause");
                break;
		}
	}
}
  
