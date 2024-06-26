# PCar Model A
- version
- TwoWheelAndServoCar_with_HC06



# Hardware 
- 後輪兩輪驅動
- 前輪 servo 帶動轉向
- HC06 (optional)



# Testcase
- [ ]  測試接收資料格式
  
    ```json
    {
    	"target_vel": [10,10], // -35~35
        "direction": 90,       // 依照機構有所不同
    	"action": "turn_left"  // turn_left,turn_right
    }
    ```
    
- [ ]  測試輸出資料格式
  
    ```json
    {
      "vels": [
        10.69518757,
        9.8039217
      ],
      "encoders": [
        6269,
        5563
      ],
      "direction": 112
    }
    ```
    
- [ ]  測試輪子前進後退 encoder 讀取數值是否正確
    - 往前漸增
    - 往後漸減
- [ ]  測試輪子前進後退 是否正確
    - serial input
      
        ```json
        {     "target_vel": [10,10]  	}
        ```
        
        - result：往前
    - serial input
      
        ```json
        {     "target_vel": [-10,-10]  	}
        ```
        
        - result：往後
- [ ]  測試前輪 servo 左右是否正確
    - serial input
      
        ```json
        {
            "direction": 70
        }
        ```
        
        - result：左邊
    - serial input
      
        ```json
        {
            "direction": 110
        }
        ```
        
        - result：右邊



# Reverse

反向的 code 差別只有以下所列，改成反向只需將定義中的數字組合對調即可

```c++
#define PIN_MOTOR_P1 21 // S2
#define PIN_MOTOR_P2 17 // S1
```

```c++
#define PIN_MOTOR2_P1 22  // S3
#define PIN_MOTOR2_P2 23  // S4
```

```c++
#define PIN_ENCODER_P1 34
#define PIN_ENCODER_P2 35
```

```c++
#define PIN_ENCODER2_P1 16
#define PIN_ENCODER2_P2 27
```

