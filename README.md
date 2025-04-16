# Force-Distance Work Calculation Assignment<br>힘-거리 일 계산 과제

* Please work on `exercise.py`.<br>`exercise.py` 파일을 수정하여 제출하세요.

## Objective 목표

This assignment introduces **lists** in Python to store and process sequences of data. You will collect forces and distances, store them in lists, and calculate the **work done** (force × distance in joules[J]). This is a fundamental concept in mechanical engineering, such as analyzing energy transfer in machines.\
이 과제는 Python에서 **리스트** 를 사용하여 일련의 순차적 데이터 시퀀스를 저장하고 처리하는 방법을 소개합니다. 힘과 거리를 입력 받아 리스트에 저장하고, **힘이 (반력을 이기고 물체를 움직여)  한 일** (단위 줄 Joule [J], 힘 × 거리로 구함)을 계산합니다. 이는 기계 공학, 예들 들어 기계 내부 에너지 전달 분석 등, 에서의 기본 개념입니다.

## Instructions 지침

Write a Python program that:<br>다음 작업을 수행하는 Python 프로그램을 작성하세요:

1. Prompts the user for the number of force-distance pairs (`n`), between 1 and 10.<br>힘, 거리의 측정 횟수 `n`을 1에서 10 사이로 사용자에게 입력받습니다.
2. Collects `n` forces (in Newtons[N]) and distances (in meters[m]) into respective lists.<br>`n`개의 힘(단위 뉴턴 Newton [N])과 `n`개의 거리(단위 미터 meter [m])를 각각의 리스트에 저장합니다.
3. Prints the collected lists and a table showing each pair’s index, force, distance, and work done.<br>수집된 리스트를 출력합니다: 인덱스, 힘, 거리, 힘이 한 일을 표시합니다.

Use only Python constructs covered in class: `print`, `input`, `if`, `for`, `list`, and f-strings.\
강의에서 다룬 Python 구조만 사용하세요: `print`, `input`, `if`, `for`, `list`, f-문자열.

Do **not** use `while`, `map`, `lambda`, `def`, `return`, `try`, `except`, or file I/O.\
`while`, `map`, `lambda`, `def`, `return`, `try`, `except`, 파일 입출력은 사용하면 **안됩니다**.

## Input Output Specification 입출력 명세

* **Number of pairs** **입력 횟수**: Prompt with following 아래 입력 프롬프트 적용

    ```Enter number of force-distance pairs (1 to 10):```

  * Convert input to integer.<br>입력을 정수로 변환
* Partition 파티션 : print `==========` 출력

* If not between 1 and 10, print following message and do not process further.<br>1에서 10 사이가 아니면 아래 메시지를 출력하고 이후의 처리를 하지 않음.

   ```Error: Number must be between 1 and 10.```
* If valid, print using following sample f-string 유효하면 아래 예시 f-string 을 이용하여 출력

   ```f'Expected number of force-distance pairs: {n}'```

* Initialize two lists for forces and distances. Recomend following names.<br>힘과 거리 입력값을 저장할 `list`를 각각 초기화. `list` 이름은 다음을 추천.

   ``` python
   forces_N = [0.0] * n
   distances_m = []
   ```

- **Forces and distances**: For each pair `i` within interval $[0, n)$ :<br>**힘과 거리**: $[0, n)$ 범위 내 각 인덱스 `i` 에 대해:
  - Prompt for force with 힘 입력 프롬프트:<br>`Enter force[{i}] in Newtons:`
  - Prompt for distance with 거리 입력 프롬프트:<br>`Enter distance[{i}] in meters:`
  - Convert both inputs to `float`s and store respective lists.<br>두 입력을 모두 실수 `float` 로 변환하여 각각의 `list`에 저장.

    ``` python
    forces_N[i] = ...
    distances_m.append(...)
    ```

  - Assume inputs are valid numbers (if invalid, `float()` would raise an error and quit).<br>입력은 유효한 숫자라고 가정 (입력이 유효하지 않은 경우 `float()`가 오류를 발생시키고 중단시킬 것임).

* Partition 파티션 : print `==========` 출력

* **Collected lists** **입력된 리스트**: After collecting inputs, print lists<br>입력값을 저장한 `list` 출력: 

   ```
   Collected forces (N): {forces_N}
   Collected distances (m): {distances_m}
   ```

* Partition 파티션 : print `==========` 출력

* Print a table header with columns as follows<br>아래와 같이 열 이름을 담은 표 머릿줄 출력:

    ```
    f"{'Index':^6}|{'Force(N)':^12}|{'Distance(m)':^12}|{'Work Done(J)':^12}"
    ```

* Print the collected forces and distances with their respective indices.<br>저장된 힘과 거리, 인덱스 출력
   - Use right-aligned formatting with 2 decimal places for floats.<br>실수는 소수점 이하 2자리로 오른쪽 정렬
   - Example f-string for a table row 표 행 예시 f-문자열:<br>`f'{i:6d}|{forces_N[i]:12.2f}|{distances_m[i]:12.2f}|{forces_N[i] * distances_m[i]:12.2f}'`

* Partition 파티션 : print `==========` 출력

* Calculate the total work done by summing the work done for each pair.<br>표 각 행의 힘이 한 일을 합산하여 표시하시오.

    ```
    f'Total work done = {total_work_done:.2f} J'
    ```

### Sample Input Output 입출력 예

```
Enter number of force-distance pairs (1 to 10): 3
==========
Expected number of force-distance pairs: 3
==========
Enter force[0] in Newton = 10.5
Enter distance[0] in meter = 2.0
Enter force[1] in Newton = -5.0
Enter distance[1] in meter = 1.5
Enter force[2] in Newton = 8.0
Enter distance[2] in meter = -3.0
==========
Collected forces (N): [10.5, -5.0, 8.0]
Collected distances (m): [2.0, 1.5, -3.0]
==========
Index |  Force(N)  |Distance(m) |Work Done(J)
     0|       10.50|        2.00|       21.00
     1|       -5.00|        1.50|       -7.50
     2|        4.00|       -3.00|      -12.00
==========
Total work done = 1.50 J
```

## Tips 힌트

- To add elements to your `list`s, use `.append()` <br>`list`에 요소를 추가하려면 `.append()`를 사용
- Access an element at index position `i` with `[i]` for calculations and printing.<br>`[i]`로 리스트 의 `i`번째 인덱스 위치 요소를 읽어 계산 & 출력
- Negative forces or distances are also valid (e.g., opposite direction or backward motion).<br>음수 힘 또는 거리도 유효 (예: 반대 방향 또는 뒤로 이동)
- See sample f-strings for formatted output.<br>예시 f-문자열 참고
- Test your code with different values, possibly including negative numbers.<br>다양한 값으로, 음수도 포함하여 시험

__Happy coding!__

## Grading Criteria 채점 기준

| Criteria | Points |
|:--------:|:------:|
| Is the code written according to Python syntax?<br>코드가 파이썬 문법에 따라 작성되었는가? | 2 |
| Does the code satisfy the requirements?<br>코드가 요구사항을 충족하는가? | 3 |

``From here is common to all assignments.``

## Submission 제출 방법

1. Modify the contents of the `exercise.py` file to write your program.<br>`exercise.py` 파일의 내용을 수정하여 프로그램을 작성합니다.
2. Use the GitHub online editor to commit and push your changes. (See below for detailed instructions)<br>GitHub 온라인 편집기를 사용하여 수정 사항을 커밋하고 푸시합니다. (자세한 사용법은 아래 참조)
3. At the Actions tab of your Github repository, please check the result.<br>깃헙 저장소의 Actions 탭에서 결과를 확인 바랍니다.

## How to Use the GitHub Online Editor<br>Github 온라인 편집기 사용법

* Press the <kbd>.</kbd> key while viewing the files in your repository on GitHub. This will launch a web version of VS Code.<br>저장소의 [Code] 탭을 선택 후 <kbd>.</kbd> 키를 누르면 MS VS Code 의 Web version 이 시작됨
* Make your changes to the `exercise.py` file.<br>`exercise.py` 파일을 수정
* To commit your changes, click on the branch icon on the left sidebar (the third icon after the magnifying glass).<br>수정 사항을 commit 등록 하려면 왼쪽에서 줄 셋 아래 (확대경 다음) 세번째 가지치기 아이콘 선택
* Click the "+" sign next to the filename to stage your changes.<br>파일 이름의 오른쪽 + 기호 선택 (staging)
* Write a brief description of your changes in the text box above.<br>위 빈칸에 변경 사항 설명 입력
* Click "Commit & Push."<br>[커밋 & 푸시] 선택
* Click "Back to Repository" on the branch icon to return to your repository.<br>줄 셋 의 [리포지토리로 이동] 선택하여 저장소로 복귀

## NOTICE REGARDING STUDENT SUBMISSIONS<br>제출 결과물에 대한 알림

* Your submissions for this assignment may be used for various educational purposes. These purposes may include developing and improving educational tools, research, creating test cases, and training datasets.<br>제출 결과물은 다양한 교육 목적으로 사용될 수 있을 밝혀둡니다. (교육 도구 개발 & 개선, 연구, 테스트 케이스 & 교육용 데이터셋 생성 등).

* The submissions will be anonymized and used solely for educational or research purposes. No personally identifiable information will be shared.<br>제출된 결과물은 익명화되어 교육 & 연구 목적으로만 사용되며, 개인 식별 정보는 공유되지 않을 것입니다.

* If you do not wish to have your submission used for any of these purposes, please inform the instructor before the assignment deadline.<br>위와 같은 목적으로 사용되기 원하지 않는 경우, 과제 마감일 전에 강사에게 알려주기 바랍니다.

``Until here is common to all assignments.``
