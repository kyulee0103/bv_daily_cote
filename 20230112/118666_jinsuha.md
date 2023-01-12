풀이 시간
15분

코드
#include <string>
#include <vector>

using namespace std;

string solution(vector<string> survey, vector<int> choices) {

    string answer = "";
    int point[4] = {0,};//RCJA
    for(int i = 0; i < survey.size(); i++){
        switch(survey[i][0]){
            case'R':
                    point[0] -= (choices[i]-4);
                break;
            case'T':
                    point[0] += (choices[i]-4);//TR 7 -> R: +3
                break;
            case'C':
                    point[1] -= (choices[i]-4);//3 C: +1
                break;
            case'F':
                    point[1] += (choices[i]-4);//
                break;
            case'J':
                    point[2] -= (choices[i]-4);
                
                break;
            case'M':
                    point[2] += (choices[i]-4);
                break;
            case'A':
                    point[3] -= (choices[i]-4);//5 A: -1
                break;
           
            case'N':
                    point[3] += (choices[i]-4);
                break;
        }
    }
    
    if(point[0] >= 0){
        answer += "R";
    } else {
        answer += "T";
    }
    
    if(point[1] >= 0){
        answer += "C";
    } else {
        answer += "F";
    }
    
    if(point[2] >= 0){
        answer += "J";
    } else{
        answer += "M";
    }
    
    if(point[3] >= 0){
        answer += "A";
    } else{
        answer += "N";
    }
    
    return answer;

}
풀이 순서
RCJA의 특성을 갖는 배열 선언, 해당 특성의 값이 양수이거나 0이면 그 해당값을 가지게됨.
switch 문으로 해당 점수를 추가
마지막에 출력
리뷰
switch 문 사용시 정수값만 case로 사용, 문자열의 경우 hashfunction을 추가해야함. 난 문자하나로 케이스를 나눔.
문제가 기니까 정리하면서 읽어야겠다 ㅋㅋ;
