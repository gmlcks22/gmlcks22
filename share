#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <stdlib.h> //malloc 사용 위해 필요
#include <string.h>
char* mystrcpy(char* to, char* from)
{
	char* f = from, * t = to;
	while (*f != '\0') {
		*t = *f;
		t++;
		f++;
	}
	*t = '\0'; //from의 마지막이 \0이기 때문에
	return to;
}
int mystrlen(char* str)
{
	char* p = str;
	int len = 0;
	while (*p != '\0') {
		len++;
		p++;
	}
	return len;
}
int mystrcmp(char* s1, char* s2)
{
	char* f1 = s1, * f2 = s2;
	while (*f1 != '\0') {
		if (*f1 == *f2) {
			f1++;
			f2++;
		}
		else if (*f1 < *f2)
			return -1;
		else if (*f1 > *f2)
			return 1;
	}
	if (*f2 == '\0')
		return 0;
}
char* mystrcat(char* to, char* from)
{
	char* f = from, * t = to;
	while (*t != '\0')
		t++; //맨 끝까지 이동하기 위해서, 공간확보 위함
	while (*f != '\0') {
		*t = *f;
		t++;
		f++;
	}
	*t = '\0'; //from의 마지막이 \0이기 때문에
	return to;
}

void reverse(char* to, char* from) //한글 포함해서 reverse 완성하기
{
	int length = strlen(from);
	int j = length - 1; //length 끝의 '\0'
	for (int i = 0; i < length; i++) {
		if ((unsigned char)from[j - i] >= 0x80 && (unsigned char)from[j - i - 1] >= 0x80) { //한글 판별
			//한글은 2byte. 이기 때문에 j-i-1 ~ j-i 범위에서 조사
			to[i] = from[j - i - 1];
			to[i + 1] = from[j - i];
			i++; //2byte 이기 때문에 추가로 i++
		}
		else {
			to[i] = from[j - i]; //from[]의 끝=to[]의 시작
		}
	}
	to[length] = '\0';
}

void main()
{
	char str1[100] = "한성대학교";
	char str2[100] = "University";
	char str3[100] = "Computer";
	char str4[100] = "Engineering";
	char str5[100];
	char str6[100];
	int ret;

	ret = mystrlen(str1);
	printf("mystrlen(%s)=%d\n", str1, ret);

	ret = mystrcmp(str1, str1);
	printf("mystrcmp(%s, %s) = %d\n", str1, str1, ret);
	ret = mystrcmp(str1, str2);
	printf("mystrcmp(%s, %s) = %d\n", str1, str2, ret);
	ret = mystrcmp(str1, str3);
	printf("mystrcmp(%s, %s) = %d\n", str1, str3, ret);

	mystrcpy(str5, str1);
	printf("mystrcpy str5 = %s\n", str5);
	mystrcat(str5, " ");
	mystrcat(str5, str2);
	printf("mystrcat str5 = %s\n", str5);
	reverse(str6, str5);
	printf("reverse str5 = %s\n", str6);
}
