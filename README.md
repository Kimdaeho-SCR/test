# test

#include<iostream>
#include<string>

using namespace std;

int main(void) {
	int len, i_5 = 0;
	int arr[26] = { 0, };
	int arr_n[26] = { 1, };
	int tmp = 0;
	string st1;

	for (int i_0 = 0;i_0 < 26;i_0++) {									//arr_n -1로 초기화
		arr_n[i_0] = 0;
	}

	getline(cin, st1);
	len = st1.length();
	for (int i_1 = 0;i_1 < len;i_1++)	arr[(int(st1[i_1]) - 97)]++;	//알파벳 검사,계산

	for (int i_2 = 0;i_2 < 26;i_2++) {									//정렬
		if (i_2 % 7 == 0)	cout << "\n";
		cout << char(i_2 + 97) << " : " << arr[i_2] << "    ";
	}
	for (int i_3 = 0;i_3 < len;i_3++) {									//최다문자 개수 계산
		(arr[i_3] > tmp) ? tmp = arr[i_3] : tmp = tmp;
	}

	for (int i_4 = 0;i_4 < len;i_4++) {									//중복 검사
		if (arr[i_4] == tmp) {
			arr_n[i_5] = i_4;
			arr_n[i_5]++;
			i_5++;
		}
	}
	cout << "\n\n 최다빈도수 알파벳,갯수";
	for (int i_6 = 0;i_6 < 26;i_6++) {
		if (arr_n[i_6] == 0) break;
		cout << "\n" << char(arr_n[i_6] + 96) << " = " << tmp;
	}
}
