## Problem
https://programmers.co.kr/learn/courses/30/lessons/42747

## Algorithm

1. int[] citations 정렬 
2. 현재원소 == 현재 원소를 포함한 남은 원소의 개수 : h = 현재원소
3. 현재원소 > 현재 원소를 포함한 남은 원소의 개수 : h = 현재 원소를 포함한 남은 원소의 개수 

## Code

```java
import java.util.*;
class Solution {
    public int solution(int[] citations) {
        Arrays.sort(citations);
        int answer = 0;
        int len = citations.length;
        if(citations[0]==citations[len-1])
            return citations[0];
        
        for(int i=0;i<len-1;i++){
            if(citations[i] == len-i){
                answer =  citations[i];
                break;
            }     
            else if(citations[i] > len-i){
                answer = len-i;
                break;
            }
        }
        return answer;
    }
}
```
+9점
## Design & Flow
## Compare 

내 코드와 성능은 비슷한 코드 
``` java
import java.util.*;

class Solution {
    public int solution(int[] citations) {
        Arrays.sort(citations);

        int max = 0;
        for(int i = citations.length-1; i > -1; i--){
            int min = (int)Math.min(citations[i], citations.length - i);
            if(max < min) max = min;
        }

        return max;
    }
}
```
## Comment
