## 문제2 - 휴가 신청 시스템
휴가 신청 시스템이 유용하게 잘 쓰이기 시작하자, 조금씩 요구사항이 더 생기기 시작했습니다.
문제 1의 코드를 그대로 가져와서, 조금씩 개선해 보겠습니다.

문제 2-1
------------------------------------------
팀 멤버가 자기 허락없이 바뀌는 것을 권위적인 부장님은 허락치 않으셨어요.
TeamMember가 생성자에서만 결정되도록 코드를 변경해주세요.

#### Main
```kotlin
fun main(args: Array<String>) {
    // 팀 멤버가 TeamLeader 객체 생성 이후에 바뀌지 않도록 아래 코드를 수정해주세요!
    /*val leader = TeamLeader(name = "TeamLeader").apply {
        teamMembers.add(TeamMember(name = "A", memberRequest = this)) // memberRequest is TeamLeader Reference.
        teamMembers.add(TeamMember(name = "B", memberRequest = this))
        teamMembers.add(TeamMember(name = "C", memberRequest = this))
        teamMembers.add(TeamMember(name = "D", memberRequest = this))
    }*/
                .
                .
                .

}
```

문제 2-2
--------------------------------
인재팀에서 조직도에 있는 정보를 연동해달라는 요구가 들어왔습니다.

* 기존 데이터를 잘 담을 수 있도록 자유롭게 클래스를 생성/변경/제거해 주세요.
* 조직도 시스템이 분산되어있어, 세가지 형태의 데이터를 따로따로 받아와야 합니다.

#### 텍스트 포맷
```text
전경주|담당|휴가(2018.02.18~2018.02.19)
김인혁|선임|
김상현|담당|
황인규|담당|휴가(2018.03.01~2018.03.03)
김지환|선임|
강영길|담당|휴가(2018.03.22~2018.04.01)
박귀남|선임|
```
#### 기존 사내 시스템 (메소드를 변경 없이 그대로 가져다 쓰세요)
```kotlin
fun getRawTeamMembers(): List<StringBuilder> {
    return StringBuilder("A|사원|휴가(2018.04.02~2018.04.05)\nB|과장|\nC|차장|")
}

fun getRawTeamLeader(): StringBuffer {
    return StringBuffer("김부장|부장|")
}
```

#### Main
```kotlin
fun main(args: Array<String>) {
    /*받아온 데이터를 TeamLeader 혹은 본인이 만든 클래스에 넣어주세요!*/
    val leader = TeamLeader(name = "TeamLeader", /* 연동된 조직도 */)
}
```

문제 2-3
--------------------------------------------
휴가신청을 의미하는 클래스가 생겼습니다. 이 클래스를 사용하도록 휴가 신청 메소드를 변경해주세요.

#### Vaction 클래스
```kotlin
class Vacation(
    val member: TeamMember,
    val period: LongRange // 휴가 기간
)
```

#### Main
```text
fun main(args: Array<String>) {
                .
                .
                .
    // 이 구문을 사용해서 vacation을 만들어 주세요.
    val vacation = me leaveUntil 20180823
    me.applyForALeave(vacation)
                .
                .
                .
}
```

더불어, 기존 휴가신청의 포맷에 휴가 기간이 추가되어야 합니다.

#### 출력 포맷
```text
[Mail Of A] [20180302~20180304] D Leave OK from.TeamLeader
[Mail Of B] [20180302~20180304] D Leave OK from.TeamLeader
[Mail Of C] [20180302~20180304] D Leave OK from.TeamLeader
[Mail Of D] [20180302~20180304] D Leave OK from.TeamLeader
```


### 큰 틀을 벗어나지 않는 선에서 main을 포함해서 문제의 내용을 바꾸셔도 무관합니다. 3챕터에 있는 내용을 최대한 사용해 주세요 😊
