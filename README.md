## MLKit_simulator
### 설치
``` bash
git clone https://gitlab.dev-merge.com/joy/mlkit_simulator.git && cd vision
pod install 
// 생성된 .xcworkspace 실행
```
### 실행
   1. Run Scheme 수정
   : 중앙 상단에서 Excutable을 VisionExample.app으로 변경 및 원하는 Simulator 설정
   2. VisionExample 프로젝트 설정에서 Signing & Capabilities 계정 설정
   3. VisionExample/ViewController.swift 에서 입력 경로, 출력 경로 수정
   ``` swift
   // 경로 문자열 뒤에 "/" 붙혀야함.
   let datasetPath = "./root1/" // input path        
   let resultPath = "./root2/" // output path
   ```
   4. 실행
### 상세설명
1. Input 구조
    ``` python
    Root/
        /class1/
               /imagename.jpg (jpg, png 등 image file)
        /class2/
               /imagename.jpg (jpg, png 등 image file)
        /class3/
               /imagename.jpg (jpg, png 등 image file)
    ```
2. Output 구조
    ``` python
    Root/
        /class1/
               /imagename-mlkit.json
        /class2/
               /imagename-mlkit.json
        /class3/
               /imagename-mlkit.json
    ```
3. Json 형식 (예시)
    ``` json
    {
	    "Mlkit class name": "FOOD" // bbox 좌표가 있어도 unknown인 경우 존재
	    "MLKit class confidence": 0.85546875,
	    "xmin": 156,
	    "ymin": 159,
	    "xmax": 307,
	    "ymax": 473
    }
    ```
