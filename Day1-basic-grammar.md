# Dart 기본기

## 규칙

- 꼭 ;를 마지막에 붙여야 한다.
- print()

## 타입

- 정수 integer : int 라고 선언
- 실수 double
- bool
- String
- dynamic

```dart
int number1 = 10; double number2 = 2.5; bool isTrue = false; String name =
'레드벨벳' var ? var name = '' -> 오른쪽 값으로 유추를 한다.
print(name.runtimeType) // runtime의 타입을 추론한다. dynamic
```

- 템플릿 리터럴도 선언 가능

```dart
print('${name} ${name2.runtimeType}');
```

### var vs dynamic

- dynamic은 타입이 변해도 가능
- var은 선언할 때 타입이 변하면 안됨.

## null ? !

- nullable : null이 될 수 있다.
- non-nullable : null이 될 수 없다.
- null : 아무런 값도있지 않다.
- String 타입에는 null안됨.
- String? 하면 null가지 담을 수 있음
- print(name2!)하면 이는 절대 null이 아니라는 말.

## final const

- final은 선언 앞에 넣어주면 됨 → 다른 값으로 변경 불가
- const 도 선언 앞에 넣어줌 → 다른 값으로 변경 불가
- final const는 타입 생략해도 됨.

### 차이?

- `DateTime` now = DateTime.now() // 버튼 누르고 코드 실행 될 때의 시간
- const → 빌드 타임에 값을 알고 있어야 한다.
- final → 빌드 타임에 값을 알고 있지 않아도 됨.

## operator

- % → 나머지 기호
- ++
- number ?? = 3.0; // null이면 오른쪽 값으로 바꿔라
- print( number1 is int) // 가능
- 논리연산자 && ||

## List

- List<String> blackPink = [’dsf’, ‘sdf’]
- List<Int> numbers = [1,2,3]
- print(blackPink.length); // 길이
- blackPink.add(’코드팩토리’); // 리스트에 요소 추가
- blackpink.remove(’코드팩토리’)
- blackPink.indexOf(’로제’)

## Map

- Map<String, String> dictionary = { ‘hary’ : ‘해리포터’}
- Map<String, bool> isharry = { ‘hary’ : ‘true’}
- isharry.addAll({’spider’ : false, ‘dsf’: treu}) → 여기 안에 있는게 다 합쳐짐
- ishary.remove(’key값’)
- ishary.keys
- ishary.values

## Set

- 중복 불가
- final Set<String> names ={ ‘code’, ‘code’, ‘flutter’}
- names.add(’jeeny’)
- names.remove(’jeeny’)
- names.contains(’fltter)

## if

```dart
if(number % 2) { print('even'); } else if ( number % 3 ==1) { print('odd'); }
else { }
```

## switch

```dart
switch(number % 3) {
	case 0 :
		print('no')
		break;
	case 1 :
		print('1')
		break;
	default :
		print('나머지 2')
		break;
}
```
