#include<stdio.h>
#pragma warning(disable:4996)
#include <stdio.h>
#include <time.h>
int main()
{
	time_t current_time = time(NULL);
	struct tm* timer = localtime(&current_time);
	int year = timer->tm_year + 1900;												//1900年以后
	int month = timer->tm_mon + 1;													//0-11
	int day = timer->tm_mday;
	int hour = timer->tm_hour;
	int min = timer->tm_min;
	int sec = timer->tm_sec;

	int week_int = timer->tm_wday;													//星期0-6，周日为0
	const char* week_map[] = { "日","一","二","三","四","五","六" };
	int yeek_int = timer->tm_yday;													//今年一年已经过了多少天
	/*提醒*/
	switch (hour)
	{
	case 6:
		printf("清晨呼吸新鲜空气，先生，请开始你美好的一天吧！！\n");
	case 7:
	case 8:
	case 9:
	case 10:
		printf("上午好，先生\n");
		break;
	case 11:
	case 12:		
		printf("中午好，先生\n");
		break;
	case 13:
		printf("中午好，先生，睡一会吧，下午会更有精神！！\n");break;
		break;
	case 17:
		printf("下午好，先生，不如出门转转吧！！\n");break;
	case 14:
	case 15:
	case 16:
	case 18:
		printf("下午好，先生\n");
		break;
	case 19:
	case 20:
	case 21:
		printf("晚上好，先生\n");
	case 22:
	case 23:
		printf("晚上好，先生，早点洗漱吧，休息好，才能更好奋斗！！\n");
		break;
	default:printf("夜深了，注意休息！\n");
		break;
	}

	printf("现在时间是；%d年%d月%d日%d时%d分%d秒 星期%s\n今年只剩下%d天\n\n", year, month, day, hour, min, sec, week_map[week_int], 365 - yeek_int);

	printf("今天的课程有：\n");

	switch (week_int)
	{
	case 0:
		printf("今天没有课哦！建议去图书馆学习。\n");break;
	case 1:
		printf("上午 10:15-11:55到南苑操场上体育课了\n,下午 14:00-15:40到信息楼304上信息技术,		15:50-17:30到南楼112上政治,");break;
	case 2:
		printf("上午 8:20-10:00到南楼113上英语课	10:15-11:55到北楼112上高等数学\n下午 14:00-15:40到南楼103上电路基础	15:50-17:30到信息楼304上信息技\n晚上 19：00-20：40到南楼102上电路基础");break;
	case 3:
		printf("上午 8:20-10:00到南楼114上英语课	10:15-11:55到信息楼304上信息技术\n下午 14:00-15:40到南楼403上安全教育15:50-17:30到南楼112上政治,");break;
	case 4:
		printf("上午 8:20-10:00到南楼113上英语课	10:15-11:55到北楼207上电路基础\n下午 14:00-15:40到北楼113上高等数学	15:50-17:30到南楼102上电路基础,");break;
	case 5:
		printf("上午 8:20-10:00112上职业发展与就业	10:15-11:55到南苑操场上体育课\n下午 14:00-15:40到南楼107上电路基础	15:50-17:30到南楼112上政治,");break;
	default:
		printf("上午 10:15-11:55到南苑操场上体育课了，下午\n14:00-15:40到南苑操场上体育课了");break;
		break;
	}
	return 0;
}
