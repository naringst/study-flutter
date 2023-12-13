# Dart OOP

## OOP란?

- Object Oriented Programming, 객체지향 프로그래밍
- 쉽게 말하면, 클래스를 사용하는 프로그래밍
- 클래스를 정의하고, 변수와 함수를 정의하면 이에 대한 인스턴스를 생성해 `반복적으로` 활용 가능하다.

## 클래스 선언

```jsx
class Idol {}
```

```jsx
// Idol class
// name
// memebers
// sayHello
// introduce

class Idol {
	String name = '블랙핑크';
	List<String> memebers = ['Jisu', 'Jenny', "Lisa", "Rose"]
	void sayHello(){
		print('안녕하세요 블랙핑크입니다.')
	}
	void introduce() {
		print('Our members are Jisu Jenny Lisa Rose')
	}
}
```

- 재사용가능하도록 클래스를 변수로 동작하게 바꾸기

  → constructor 활용

  ```jsx
  void main() {
  	Idol blackPink = Idol('블랙핑크', ['Jisu', 'Jenny', "Lisa", "Rose"]);
  	print(blackPink.name); // 블랙핑크

  // Idol class
  // name
  // memebers
  // sayHello
  // introduce
  // constructor
  class Idol {
  	String name = '블랙핑크';
  	List<String> memebers = ['Jisu', 'Jenny', "Lisa", "Rose"]

  	Idol() // 가장 기본인 constructor
  	Idol(String name, List<String> memebers)
  		: this.name = name;
  			this.members = members;
  //괄호 안의 애들을 받아서 해당 클래스의 인스턴스를 초기화를 해준다.
  	void sayHello(){
  		print('안녕하세요 ${this.name}입니다.')
  	}
  	void introduce() {
  		print('Our members are ${this.members}');
  	}
  }

  ```

- 이 constructor를 더 간단히 작성하는 방법

  ```jsx
  void main() {
  	Idol blackPink = Idol('블랙핑크', ['Jisu', 'Jenny', "Lisa", "Rose"]);
  	print(blackPink.name); // 블랙핑크

  }

  class Idol {
  	String name;
  	List<String> memebers;

  	Idol(this.name, this.members);

  //괄호 안의 애들을 받아서 해당 클래스의 인스턴스를 초기화를 해준다.
  	void sayHello(){
  		print('안녕하세요 ${this.name}입니다.')
  	}
  	void introduce() {
  		print('Our members are ${this.members}');
  	}
  }

  ```

- named constructor → named 파라미터와 유사

  ```jsx
  void main() {
  	Idol blackPink = Idol('블랙핑크', ['Jisu', 'Jenny', "Lisa", "Rose"]);
  	print(blackPink.name); // 블랙핑크
  	Idol bts = Idol.fromList([['rm', 'jin','suga','jhope','jimin'. 'v', 'jk'] // values[0] , 'bts' // values[1]])
  }
  //어떤 constructor를 사용해도 인스턴스 생성 가능
  class Idol {
  	String name;
  	List<String> memebers;

  	Idol(this.name, this.members);  // 기본 컨스트럭터
  	Idol.fromList(List values) : //named constructor -> 다른 형태로 인스턴스 생성 가능, 여기서는 fromList가 name
  		this.members = values[0]
  		this.name = values[1]
  //괄호 안의 애들을 받아서 해당 클래스의 인스턴스를 초기화를 해준다.
  	void sayHello(){
  		print('안녕하세요 ${this.name}입니다.')
  	}
  	void introduce() {
  		print('Our members are ${this.members}');
  	}
  }
  ```

- immutable 프로그래밍
  → 원래 [bts.name](http://bts.name) = ‘귀염둥이들’ 로 바꿀 수 있다.
  → 이걸 막기 위해 `final` 키워드 사용 → 값을 바꿀 수 없게 됨.
  → `final` 쓰는 습관 들여야 버그 방지 가능
  ```jsx
  class Idol {
  	final String name;
  	final List<String> members;
  }
  ```
  → `const` 키워드
  → constructor 앞에 사용.
  ```jsx
  const	Idol(this.name, this.members);
  ```
  → 위와 같이 생성자 앞에 const 를 붙여서 선언하고,
  ```jsx
  Idol blackPink = const Idol('블랙핑크', ['Jisu', 'Jenny', "Lisa", "Rose"]);
  ```
  → 인스턴스 생성할 때에도 앞에 `const`를 붙여주면
  → 한번 선언하면 값을 바꿀 수 없게 된다.
    <aside>
    💡  이때 `const`로 선언할 수 있는 변수들로 구성된 constructor의 파라미터들을 사용했을때 `const` constructor 사용 가능.
    ex. new Date() 같은 동적으로 생성되는 것들은 안됨. 빌드타임에 값을 알수 있는 값만 const 가능
    
    </aside>


### const 키워드로 만든 인스턴스의 차이점

- const 로 만들지 않은 두 개의 인스턴스는 값이 같아도 메모리 저장 공간 다름
- 둘다 const로 같은 파라미터로 선언하면 같은 메모리 공간. 비교 시 true
