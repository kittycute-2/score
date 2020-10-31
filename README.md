# score
Score Enquiry System
C++
#include <iostream>
#include <ctime>
#include <iomanip>
using namespace std;
int main()
{    
	time_t timer;
	time(&timer);
	tm *t_tm = localtime(&timer);	
	int year = t_tm->tm_year + 1900;   //显示日期的函数部分、注意加源文件 
	int month = t_tm->tm_mon + 1;
	int day = t_tm->tm_mday;


 string username,classroom;
 cout<<"请输入你的姓名："; 
 cin >> username;
 cout<<"请输入你的班级：";
 cin >> classroom;
 cout << "*******************************************"<<endl;
 cout << "*       欢迎使用学生成绩管理系统1.1       *"<<endl;
 
 if(username.length()==4) //两个字的名字  一个汉字两个字节数 
 cout << "*      "<<username<<"  "<<"计算机"<<classroom<<"班"<<"  "<< year << "." << month << "." << day <<"     *"<<endl;
 else if(username.length()==6)   // 三个字的名字 
 cout << "*    "<<username<<"  "<<"计算机"<<classroom<<"班"<<"  "<< year << "." << month << "." << day <<"     *"<<endl;
 else if(username.length()==8)   //四个字的名字 
 cout << "*    "<<username<<"  "<<"计算机"<<classroom<<"班"<<"  "<< year << "." << month << "." << day <<"   *"<<endl;
 else
 {cout << "*                用户名错误               *"<<endl;
  cout << "*                已退出系统               *"<<endl;
  return 0;} 
  
 cout << "*      1、输入4个同学的代号和成绩         *"<<endl;
 cout << "*      2、显示4个同学的代号和成绩列表     *"<<endl;
 cout << "*      3、求4人平均分                     *"<<endl;
 cout << "*      4、求4人总分                       *"<<endl;
 cout << "*      5、查询某同学的分数                *"<<endl;
 cout << "*      6、统计及格率                      *"<<endl;
 cout << "*      7、退出                            *"<<endl;
 cout << "*******************************************"<<endl;
 
 reselect:
 {
 cout << "请输入你的选择：" <<endl; 
 int a;
 cin >> a;
 char A,B,C,D;
 double score1,score2,score3,score4;
 switch(a) 
 {
 	case 1:cout<<"请输入4个同学的代号和成绩"<<endl;
	       cin>>A>>score1>>B>>score2>>C>>score3>>D>>score4;
	       cout<<"已成功录入同学成绩。" <<endl; 
	       goto  reselect;
    case 2:cout<<"学生："<<A<<"  成绩："<<score1<<endl;
	       cout<<"学生："<<B<<"  成绩："<<score2<<endl;
	       cout<<"学生："<<C<<"  成绩："<<score3<<endl;
	       cout<<"学生："<<D<<"  成绩："<<score4<<endl;
	       goto  reselect;
	case 3:double averagescore;
	       averagescore=(score1+score2+score3+score4)/4;
	       cout<<"这4个同学的平均分是"<<averagescore<<endl; 
	       goto  reselect;
	case 4:double totalscore;
	       totalscore=score1+score2+score3+score4;
	       cout<<"这4个同学的总分是"<<totalscore<<endl;
		   goto  reselect;
	case 5:char student;
	       cout<<"请输入查询同学代号："<<endl;
		   cin>>student;
		   switch (student)
		   {case 'A':cout<<"同学"<<A<<"的成绩为"<<score1<<endl;break; 
		   case 'B':cout<<"同学"<<B<<"的成绩为"<<score2<<endl;break; 
		   case 'C':cout<<"同学"<<C<<"的成绩为"<<score3<<endl;break; 
		   case 'D':cout<<"同学"<<D<<"的成绩为"<<score4<<endl;break; 
		   default:cout<<"请输入正确的同学代号。"<<endl; }
		   goto  reselect;
	case 6:double rate;
	       float i;
	        i=0.00;
	       if(score1>=60) 
		      i=i+1;
	       if(score2>=60) 
		      i=i+1;
		   if(score3>=60) 
		      i=i+1;
		   if(score4>=60) 
		      i=i+1;
		   cout<<i<<endl;
		   rate=i/4*100;
	       cout<<"这4个同学的及格率为"<<rate<<"%"<<endl;
		   goto  reselect; 
	case 7: cout<< "你已退出程序。" <<endl;
	        break; 
	default:cout<<"请根据提示，输入数字1-7。"<<endl; 
	       goto  reselect;
 }
}
 return 0;
}
