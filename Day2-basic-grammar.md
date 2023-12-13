## 다시 볼 내용

- 함수 파라미터 설정 시 [int y = 20,int z = 30] 이렇게 표시하면 optional
- 꼭 필요한 파라미터는 required 를 붙일 수 있다.

### typedef

- typedef를 사용해서 같은 형식의 함수들을 묶어서 나타낼 수 있다. -> 타입스크립트의 함수 타입 선언과 비슷
- 이렇게 선언한 Operation 타입의 함수들은 Operation operation = add; 으로 적용 가능하다.
- typedef 선언은 다음과 같다.

```dart
 //signature
typedef Operation = double Function(int x, int y, int z);
```

## loop

- for loop

```dart
void main() {
for (int i = 0 ; i < 10 ; i ++ ) {
	print(i);
}
}

for (int number in numbers) {
	print(number);
}
```

- while loop

```dart
while (total<10) {
	total+=1;
	if(total == 5) {
		break;
	}
}

```

- do - while loop

```dart
do-while

do{} while(){}
```

- break
- continue

## enum

```dart
 enum Status{
	appreoved, pedngin, rejected
}

void main(){
	Status status = Status.pending;

	if (status == Status.approved){
		print('승인입니다')
	}
}
```

## 함수 선언법

- 함수 기능 : 반복되는 코드 재사용
- [] -> optional parameter
- named parameter : 이름이 있는 파라미터(순서 중요하지 않음)

```dart
//함수의 역할 적어두기

void main() {
	int result1 = addNumbers(10,20,30);
	int result2 = subNumbers(x:10, y:20, z:30);
}
//세 개의 숫자를 더하고 짝수인지 홀수인지 알려주는 함수
//parameter, argument - 매개변수
int addNumbers(int x, [int y = 20,int z = 30]){
	int sum = x + y + z
	if (sum %2 == 0 ) {
		print('짝수입니다');
	} else {
		print('홀수입니다');
	}
	return sum
}

int subNumbers({required int x,required int y,required int z }){
	int sun = x - y - z
	if (sub %2 == 0 ) {
		print('짝수입니다');
	}else {
		print('홀수입니다');
	}
	return sub
}

//이때 required를 지우면 named이면서 optional이 된다.
```

- void → return 값이 없다.

### arrow 함수

```dart
int addNumbers(int x, [int y = 20,int z = 30]){
	int sum = x + y + z
	if (sum %2 == 0 ) {
		print('짝수입니다');
	}else {
		print('홀수입니다');
	}
	return sum
}

-----
int addNumbers(int x, int y , int z) => x+y+z;
//화살표 뒤가 반환값
```

### typedef

```dart
void main() {
	Operation operation = add;
	int result = operation(10,20,30);
	print(result);
	operation = subtract;
	int result2 = operation(10,20,30);
	print(result2);
	int result3 = calculate(30,40,50,add);
	print(result3);
}

//signature
typedef Operation = double Function(int x, int y, int z);

//더하기
int add(int x, int y , int z) => x+y+z;

//빼기
int subtract(int x, int y , int z) => x-y-z;

//계산
int calculate(int x , int y , int z, Operation operation) {
	return operation(x,y,z);
}
```
