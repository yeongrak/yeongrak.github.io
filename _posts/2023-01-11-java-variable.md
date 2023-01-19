---
layout: single
title: "변수"
categories: Java
tag: [자바의 정석 - 변수]
toc: true
author_profile: false
sidebar:
  nav: "docs"
---

# 1. 변수

1. ##### 변수란?

   - 단 하나의 값을 저장할 수 있는 메모리 상의 공간을 의미한다.

2. ##### 변수의 선언

   1. 변수의 선언 이유
      - 값(data)을 저장할 공간을 마련하기 위해서
   2. 변수의 선언 방법
      - 변수 타입	변수 이름;
        - ex) int age; // 정수(int) 타입의 변수 age를 선언
        - age 라는 이름의 저장 공간이 생성

3. ##### 변수에 값 저장하기

   1. 변수에 값 저장하기('=' 는 등호가 아니라 대입)
      - int age;	// 정수(int)타입의 변수 age 선언
      - age = 25;    // 변수 age에 25를 저장
      - int age = 25;    // 위의 두 줄을 한 줄로
   2. 변수의 초기화(initialization) - 변수에 처음으로 값을 저장하는 것
      - 메모리에는 여러 프로그램이 공유하는 자원이므로 전에 다른 프로그램에 의해 저장된 '알 수없는 값' 이 남아있을 수 있기 때문
      - 지역변수는 사용되기 전에 초기화를 반드시 해야 하지만 클래스변수와 인스턴스변수는 초기화를 생략할 수 있다.

4. ##### 변수의 타입

   1. 값의 종류에 따라 값이 저장될 공간의 크기와 저장 형식을 정의한 것이 자료형이다.

      - 자료형 - 문자형(char), 정수형(byte, short,  int, long), 실수형(float, double)
      - 변수를 선언할 때는 저장하려는 값의 특성을 고려하여 가장 알맞은 자료형을 변수의 타입으로 선택하면 된다.

   2. 기본형과 참조형

      1. 기본형 변수는 실제 값(data)를 저장하고, 참조형 변수는 어떤 값이 저장되어 있는 주소(memory address)를 값으로 갖는다.

         - 참조형변수를 선언할 때는 변수의 타입으로 클래스 이름을 사용하므로 클래스의 이름이 참조변수의 타입이 된다.

         - 클래스이름 변수이름;    //변수의 타입이 기본형이 아닌 것들은 모두 참조변수이다.

         - ```java
           Date today = new Date(); //Date 객체를 생성해서, 그 주소를 today에 저장
           ```

           - 객체를 생성하는 연산자 new의 결과는 생성된 객체의 주소이다. 이제 참조변수 today를 통해서 생성된 객체를 사용할 수 있게 된다.

5. ##### 변수, 상수, 리터럴

   - 변수(variable) - 하나의 값을 저장하기 위한 공간    //변경 가능

   - 상수(constant) - 한 번만 값을 저장 가능한 변수    // 변경 불가

   - 리터럴(literal) - 그 자체로 값을 의미하는 것

     - ```java
       int score = 100;
           score = 200;	// score : 100 -> 200
       final int MAX = 100; // MAX는 상수
                 MAX = 100; // 에러
       char ch = 'A';
       String str = "abc";
       ======================================================
       변수 : score, ch, str
       상수 : MAX
       리터럴 : 100, 200, 'A', "abc"
       ```

6. ##### 리터럴의 접두사와 접미사

   - | 종류   | 리터럴                       | 접미사 |
     | ------ | ---------------------------- | ------ |
     | 논리형 | false, frue                  | 없음   |
     | 정수형 | 123, 0b0101, 077, 0xFF, 100L | L      |
     | 실수형 | 3.14, 3.0e8, 1.4f, 0x1.0p-1  | f, d   |
     | 문자형 | 'A', '1', '\n'               | 없음   |
     | 문자열 | "ABC", "123", "A", "true"    | 없음   |

   - 정수와 실수형에는 여러 타입이 존재하므로, 리터럴에 접미사를 붙여서 타입을 구분한다.

   - long, float의 리터럴에 접미사를 붙이는 것에 주의

7. ##### 변수와 리터럴의 타입 불일치

   1. 범위가 '변수 > 리터럴' 인 경우 OK
   2. 범위가 '변수 < 리터럴' 인 경우 Error
   3. byte, short 변수에 int 리터럴 저장가능
      - 단, 변수의 타입의 범위 이내이어야 

8. ##### 형식화된 출력 - printf()

   - println()의 단점 - 출력형식 지정 불가

   - printf()로 출력형식 지정가능

   - | 지시자 | 설명                                        |
     | ------ | ------------------------------------------- |
     | %b     | boolean 형식으로 출력                       |
     | %d     | 10진(decimal) 정수의 형식으로 출력          |
     | %o     | 8진(octal) 정수의 형식으로 출력             |
     | %x, %X | 16진(hexa-deciaml) 정수의 형식으로 출력     |
     | %f     | 부동 소수점(floating-point)의 형식으로 출력 |
     | %e, %E | 지수(exponent) 표현식의 형식으로 출력       |
     | %c     | 문자(character)로 출력                      |
     | %s     | 문자열(string)로 출력                       |

   - 특수 문자 다루기

   - | 특수 문자            | 문자 리터럴 |
     | -------------------- | ----------- |
     | tab                  | \t          |
     | backspace            | \b          |
     | form feed            | \f          |
     | new line             | \n          |
     | carriage return      | \r          |
     | 역슬래쉬             | \\\         |
     | 작은따옴표           | \ '         |
     | 큰따옴표             | \ "         |
     | 유니코드(16진수)문자 | \u          |

     

9. ##### 화면에서 입력받기 - Scanner

   - Scanner란?

     - 화면으로부터 데이터를 입력받는 기능을 제공하는 클래스

   - Scanner를 사용하려면

     1. import문 추가

        - import java.util.*;

     2. Scanner 객체의 생성

        - ```java
          Scanner scanner = new Scanner(System.in); //System.in -> 화면입력
          ```

     3. Scanner 객체를 사용

        - ```java
          int num = scanner.nextint(); //화면에서 입력받은 정수를 num 에 저장
          String input = scanner.nextLine(); // 화면에서 입력받은 내용을 input 에 저장
          int num = Integer.parseInt(input); // 문자열(input)을 숫자(num)로 변환
          ```

        - ```java
          package chapter.variable;
          
          import java.util.Scanner;
          
          public class Variable2 {
              public static void main(String[] args) {
                  Scanner scanner = new Scanner(System.in);
          
                  System.out.println("두자리 정수를 하나 입력해주세요:");
                  String input = scanner.nextLine();
                  int num = Integer.parseInt(input);
          
                  System.out.println("입력내용 : " + input);
                  System.out.println(num);
              }
          }
          ==================================================
          실행결과
          두자리 정수를 하나 입력해주세요: 33
          입력내용 : 33
          33
          ```

10. ##### 형변환

    1. 형변환(캐스팅, casting)이란?

       - 변수 또는 상수의 타입을 다른 타입으로 변환하는 것

    2. 형변환 방법

       - 형변환하고자 하는 변수나 리터럴의 앞에 변환하고자 하는 타입을 괄호와 함께 붙여 주기만 하면 된다.

         - (타입)피연산자

       - ```java
         double d = 85.4;
         int score = (int)d; //double 타입의 변수 d 를 int 타입으로 형변환(캐스팅)
         ```

       - ```java
             public static void main(String[] args) {
                 double d = 85.4;
                 int score = (int) d;
         
                 System.out.println("score = " + score);
                 System.out.println("d=" + d);
             }
         ======================================================
         실행결과
         score = 85
         d=85.4 <- 형변환 후에도 피연산자에는 아무런 변화가 없다.
         ```

         - |     변환     |   수식    | 결과  |
           | :----------: | :-------: | :---: |
           | int -> char  | (char)65  |  'A'  |
           | char -> int  | (int)'A'  |  65   |
           | float -> int | (int)1.6f |   1   |
           | int -> float | (float)10 | 10.0f |

    3. 자동 형변환의 규칙

       - 기본의 값을 최대한 보존할 수 있는 타입으로 형변환한다.
       - boolean을 제외한 나머지 7 개의 기본형은 서로 형변환이 가능하다.
       - 기본형과 참조형은 서로 형변환할 수 없다.
       - 서로 다른 타입의 변수간의 연산은 형변환을 하는 것이 원칙이지만, 값의 범위가 작은 타입에서 큰 타입으로의 형변환은 생략할 수 없다.





































​	



