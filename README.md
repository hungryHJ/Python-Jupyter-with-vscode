Python Jupyter 환경 구성 방법 with vscode
========

python은 Open-Source 인터프리터 언어로써, 다양한 분야에서 활용되며 pyCharm, Jupyter Notebok, Spider 등  다양한 IDE가 존재한다.

특히 머신러닝 분야에서는 Jupyter 환경(Jupyter Notebook, Jupyter Lab)을 선호하며, 이는 _Cell_ 단위로 코드를 실행하는 _ipynb_ (줄여서 노트북)파일에 코드와 출력이 같이 저장된다는 특징이 있다. Visual Studio Code 에서도 Jupyter 익스텐션을 통해 ipynb를 작성가능하며, 이 글은 vscode에서 ipynb를 작성하고 실행하는 환경을 소개한다.

> 최종작성일 : 2025-MAR-10



# 1. Anaconda 설치

## 1.1. anaconda 페이지 이동
아나콘다 공식 사이트: https://www.anaconda.com/  
아나콘다 배포 다운로드: https://www.anaconda.com/download/success  
![alt](img/이미지%20023.png)



## 1.2. anaconda 다운로드
![alt](img/이미지%20024.png)  
![alt](img/이미지%20024-1.png)  
![alt](img/이미지%20024-2.png)  
본인의 환경이 윈도우즈가 아니라면, 본인 환경에 맞게 다운로드  
(아나콘다 배포 다운로드: https://www.anaconda.com/download/success)  

## 1.3. 설치프로그램 실행
![alt](img/이미지%20027.png)  
전부 다음 버튼을 눌러 설치

![alt](img/이미지%20029.png)  
![alt](img/이미지%20028.png)  
![alt](img/이미지%20029-1.png)  
일반적인 경우에는 다음을 눌러서 설치가 가능하다.  

> 단, 경로에 영어 외의 글자가 있다면 설치할 수 없다는 메세지가 뜬다. 이전으로 돌아가 _"Just Me"_ 가  아닌 _"All Users"_ 로 설치하면 해결되기는 하지만,대부분의 기능을 **관리자 권한으로 실행** 해야하므로 추천하지 않는다.

<br><br><br><br>  

# 2. 파이썬 가상환경 추가 및 패키지 설치
## 2.1. anaconda prompt 실행
![alt](img/이미지%20030.png)  
시작버튼을 누르고, 검색 창에 anaconda 를 입력하여, **Anaconda Prompt (anaconda3)** 를 실행한다. (powershell Prompt 가 아님을 주의)

## 2.2. 가상환경 생성 및 활성화
![](img/이미지%20031.png)  
    
    conda create -n 가상환경명 python


예시  

    conda create -n lecture python


실행결과   
![](img/이미지%20033.png)  
![](img/이미지%20034.png)  
생성된 가상환경을 활성화
    
    conda activate 가상환경명

예시

    conda activate lecture

> 가상환경을 활성화가 성공적으로 작동하면, 명령줄 앞에 **(가상환경)** 이 표시된다.

## 2.3. 파이썬 패키지 설치  

<br>

> [!WARNING]  
> 반드시 가상환경이 활성화가 먼저 되어야함. [챕터2.2. ](#22-가상환경-생성-및-활성화) 참고

<br>

![](img/이미지%20035.png)  

패키지 설치법

    pip install 패키지이름


머신러닝을 위해 설치할 패키지는 다음과 같다.  
* numpy : 수학관련 모듈
* matplotlib : 그래프 그리기 위한 모듈
* pandas : 엑셀데이터를 다루기 위한 모듈
* **scikit-learn : 머신러닝 모델 지원 모듈**
* **ipykernel : vscode에서 주피터를 이용하기 위한 모듈**
* sklearn-som : Self Organization Map 모델을 구현한 모듈
* mlxtend : Association Rule 모델을 구현한 모듈

예시

    pip install numpy matplotlib pandas scikit-learn ipykernel sklearn-som mlxtend

실행결과  
![](img/이미지%20035.png)  
> 스크린샷의 첫번째 줄 끝에 ip가 아니라 ipykernel 임을 주의

<br><br><br><br>  

# 3. vscode 설치

## 3.1. vscode 페이지 이동
https://code.visualstudio.com/
![alt](img/이미지%20025.png)



## 3.2. vscode 다운로드
![alt](img/이미지%20026.png)

## 3.3. 설치프로그램 실행
![](img/이미지%20036.png)  
![](img/이미지%20037.png)  
![](img/이미지%20038.png)  
동의 후 전부 다음 버튼을 눌러 설치

<br><br><br><br>  

# 4. vscode 익스텐션 설치
## 4.1. jupyter 익스텐션 설치
![](img/이미지%20040.png)  
왼쪽에 익스텐션 버튼을 누른 후, jupyter 를 검색해서 설치한다.
jupyter 설치버튼을 누르면 다음 확장이 자동으로 설치된다.
* Jupyer
* Jupyter Keymap
* Jupyter Slide Show
* Jupyter Cell Tags
* Jupyter Notebook Renderers

## 4.2. python 익스텐션 설치
![](img/이미지%20041.png)  
4.1과 마찬가지로, 익스텐션에서 python 을 검색해서 설치한다.

<br><br><br><br>

# 5. vscode에서 ipynb 실행

## 5.1. 폴더 열기
![](img/이미지%20042.png)  
File - Open Folder 를 통해 폴더를 열어준다.

![](img/이미지%20043.png)
프로젝트를 진행할 폴더를 만들어준다.
스크린샷은 홈디렉토리이지만, 바탕화면, 내 문서 등에 만들어도 무방하다. 폴더이름은 lecture로 하였다.  
폴더가 만들어진 후, 폴더를 클릭하고 **폴더 선택** 버튼을 눌러 폴더를 지정한다.


![](img/이미지%20044.png)  
새 윈도우가 열리면서 해당폴더가 열리며, 신뢰성 검사 창이 뜨면, **Yes**를 클릭한다.


## 5.2. 노트북 파일 생성
![](img/이미지%20045.png)  
File - New File 을 클릭한다.

![](img/이미지%20046.png)  
상단의 Command Palette가 열리면, Jupyter Notebook 을 선택한다.  

## 5.3. 노트북 파일과 파이썬 가상환경 연결
![](img/이미지%20048.png)  
![](img/이미지%20049.png)  
노트북 파일이 열리면, 우측 상단에 _select Kernel_ 버튼을 누른 후, _Python Environments..._ - _가상환경_ 을 선택한다.
([챕터2. ](#2-파이썬-가상환경-추가-및-패키지-설치)에서 _lecture_ 가상환경에 필요한 패키지를 설치하였으므로 lecture를 선택하였다.)

![](img/이미지%20050.png)  
방화벽 경고가 뜨면 _엑세스 허용_ 을 클릭한다. (우측 상단에서 커널이 연결 중인지, 연결 완료 되었는지 확인 가능하다.)

## 5.4. Hello World
![](img/이미지%20053.png)  
Code Cell 에 다음 코드를 작성하고 왼쪽의 실행버튼을 클릭하여 정상 작동하는지 확인한다.
```python
print("Hello")
```
정상작동하면, 아래쪽에 초록색 체크 ✅ 표시가 뜨면서, hello 가 정상 출력 된다. 혹시 실행버튼이 없다면, 노란박스의 언어 선택이 Python 인지 확인한다. 클릭하여 변경가능하다.  

<br>

[챕터2.3. ](#23-파이썬-패키지-설치) 에서 설치한 패키지가 잘 설치되었는지 확인하기 위해 다음과 같은 코드를 작성하고 실행한다. **+Code** 버튼을 누르면 아래에 코드 Cell 이 추가된다.  
![](img/이미지%20053-1.png)  
<br>  
  
아래쪽에 새로 생성된 코드 Cell에 다음 코드를 입력한다.  
```python
import numpy as np
import matplotlib.pyplot as plt

plt.plot(np.random.randn(100))
```
실행결과  
![](img/이미지%20054.png)    
(랜덤 숫자 100개를 이어서 그린 그래프이므로, 실선의 패턴은 모두 다르다.)

<br><br><br><br>

# 6. 결론
여기까지 문제가 없다면, vscode에서 ipynb 파일을 생성하고 실행이 가능하다. vscode를 재실행하면, 파이썬 커널이 종료되어 작업중인 변수는 사라지므로, 그럴 때는 **_Run All_** 버튼을 눌러 전체 재실행하면 된다.  

  
추가적인 패키지가 필요하다면 노트북 파일을 **가상환경을 연결한뒤([챕터5.3. ](#53-노트북-파일과-파이썬-가상환경-연결))** 코드 Cell에서 

    !pip install 패키지명

를 입력하거나,  
  
[챕터 2.](#2-파이썬-가상환경-추가-및-패키지-설치) 에서 처럼 Anaconda Prompt 실행 후,

    conda activate 환경명
    pip install 패키지명

을 이용하면 된다.

