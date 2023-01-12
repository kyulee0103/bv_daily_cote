풀이 시간
15분

코드
#include <string>
#include <vector>
#include <ctype.h>

using namespace std;

string solution(string s) {
    string answer = "";
    string low = "";
    bool up = false;
    
    for(int i = 0; i < s.length(); i++){
        low += tolower(s[i]);
    }
    
    answer += toupper(low[0]);
    //
    for(int i = 1; i < low.length(); i++){
      if(low[i] == ' '){
          if(low[i+1] != ' '){
              up = true;
            }
          answer += low[i];
      } else {
        if(up == true){
            answer += toupper(low[i]); 
            up = false;
        } else {
            answer += low[i];
        }
      }
                      
    }
    return answer;
}
풀이 과정
일단 전체를 tolower합니다.
연속적인 공백이 등장할 수 있으니, 공백중 마지막 공백이 등장했을 때, up을 true로 바꿔줍니다.
이러면 그다음 문자는 무조건 upper로 바꿔주게 된다.
리뷰
연속적인 배열을 탐색할때 인덱스를 사용해 문제를 풀면 더 간단한거 같다.
