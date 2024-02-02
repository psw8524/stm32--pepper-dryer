# STM32__Pepper_Dryer
STM32F103C8T6을 이용하여 실내 온도를 적정 온도로 유지하게끔 제어하는 건조기 프로젝트입니다.
STM32CubeIde와 HAL Driver 를 사용하여 제어과정을 가져보았습니다.

## STEP 1
전원 인가 시, OLED 화면에 Start! Pepper dryer!! 문장이 5초간 Display 되면서 Peripheral Devices가 작동을 한다

1. 설정 온도값은 25도가 Default value 이다
2. Polling 방식으로 현재 온도값을 온도센서(Ds18b20)모듈이 읽어들여 실시간으로 Fnd모듈에 Display 한다

## STEP 2
OLED 화면에 설정 온도(Temper), 동작 상태(Work)를 표시하고 스위치를 조작하여 사용자가 설정한다

1. (왼쪽부터) 1번 푸시버튼 스위치를 누르면, 설정 온도를 1도씩 증가 시킨다
2. 2번 푸시버튼 스위치를 누르면, 설정 온도를 1도씩 감소 시킨다
3. 3번 푸시버튼 스위치를 누르면, 실내 온도를 설정 온도로 맞추는 동작을 시작할 준비를 한다
4. 슬라이드 스위치를 밀면, Relay를 통하여 가열 장치가 가열을 시작한다

## STEP 3
가열 장치 동작 조건

1. if (설정 온도가 현재 온도 보다 높을때), 현재 온도가 서서히 증가하다가 (설정 온도 - 5도) 일때 가열을 중단한다
2. (설정 온도 - 5도) 보다 현재 온도가 낮아질때, 다시 가열 장치가 동작한다
3. 위의 과정을 반복하여 설정 온도에 가깝게 현재 온도를 상시 유지하는 과정을 가진다
4. 가열 동작 중 슬라이드 스위치를 다시 밀면, 가열 동작이 중단 된다

+ 오차범위 (설정 온도 +- 2도)



사용한 언어 : ![js](https://img.shields.io/badge/C-00599C?style=for-the-badge&logo=c&logoColor=white)

(동작 영상) ![js](https://img.shields.io/badge/YouTube-FF0000?style=for-the-badge&logo=youtube&logoColor=white) : 

https://youtube.com/shorts/OR36uxfubtw?feature=share

https://youtu.be/V-RhyAZlyn8
