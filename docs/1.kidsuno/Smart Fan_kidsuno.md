#  Smart Fan for Kidsuno

## 1. Code

[DOWNLOAD](../Code.zip)

Download and unzip these files. Here all codes are in folder **1.Code_kidsuno**.

For convenience, <span style="color: rgb(2550, 10, 50);">we move the codes into: **D:\Code\1.Code_kidsuno**.</span> You can also choose to move it into any disks at will. 

---

## 2. Development Environment Configuration

### 2.1 KidsBlock Download

![2101](media/2101.png)

1. [KidsBlock Download](https://wiki.kidsbits.cc/projects/KidsBlock/en/latest/download/)
2. Installation
   - [Windows System](https://wiki.kidsbits.cc/projects/KidsBlock/en/latest/Windows/)
   - [MacOS System](https://wiki.kidsbits.cc/projects/KidsBlock/en/latest/MacOS/)
3. [Driver Installation](https://wiki.kidsbits.cc/projects/KidsBlock/en/latest/driver/)

---

### 2.2 KidsBlock Tutorial

1. Make sure the board is connected to computer. Open KidsBlock and choose a device.

![2201](media/2201.png)

Choose **kidsuno**.

![2202](media/2202.png)

Click **Connect**.

![2203](media/2203.png)

**Go to Editor**.

![2204](media/2204.png)

Click ![2216](media/2216.png): shift realtime mode into upload mode.

![2215](media/2215.png)

![2217](media/2217.png)

![line1](media/line1.png)

2. Build code blocks and upload.

**Method ①**: Directly drag blocks to the editing area.

![2207](media/2207.png)

After building your blocks, save it to your computer: **File --> Save to your computer**

![2209](media/2209.png)

Click ![2210](media/2210.png) to upload the code.

![line4](media/line4.png)

**Method ②**: Load code from your computer.

Download code in **1. Code** to your computer. For convenience, here we save it to D:\Code\1.Code_kidsuno.

**File --> Load from your computer** and choose code to open.

![2209](media/2209.png)

After loading code, connect to the corresponding port.

![2211](media/2211.png)

![2203](media/2203.png)

After that, click ![2210](media/2210.png) to upload code.

![line1](media/line1.png)

**Main Interface**

![2205](media/2205.png)

![2206](media/2206.png)

---

## 3. Modules

<span style="color: rgb(2550, 10, 50);">Please move the codes to a convenient path as your needs, for instance, path: **D:\Code\1.Code_kidsuno**.</span>

### Kidsuno Ports View

During experiments, <span style="color: rgb(2550, 10, 50);">modules can only be connected to ports in the same color.</span>

![KD2075](media/KD2075.png)

### 3.1 White LED Module

![1top](media/1top.png)

![KD2078](media/KD2078.png)

**LED (Light-Emitting Diode)**

LED is a commonly used light emitting device that converts electrical energy into light energy. Usually, it is used as an indicator in circuits and instruments, or as part of texts or numeric display.

It generally includes gallium(Ga), arsenic(As), phosphorus(P), nitrogen(N) and so on. 

|     LED components      | Emitting light colors |
| :---------------------: | :-------------------: |
| gallium arsenide diode  |          red          |
| gallium phosphide diode |         green         |
|  silicon carbide diode  |        yellow         |
|  gallium nitride diode  |         blue          |

![1bottom](media/1bottom.png)

#### Parameters

![2top](media/2top.png)

Operating voltage: DC 3.3 ~ 5 V

Operating current: 1.5 mA (Peak: 2.3mA)

Maximum power: 0.07 W

Control signal: digital signal

Dimensions: 24 x 48 x 18 mm (without housing)

Positioning holes: diameter of 4.8 mm

Interface: telephone socket

![2bottom](media/2bottom.png)

#### Principles

![3top](media/3top.png)

Modules with blue housing are digital ones, so we should connect to digital io pins of the mainboard (ports with blue).

![3112](media/3112.png)

In this experiment, we connect the white LED module to port 1. According to the board ports view, the digital io pin at port 1 is digital pin D5.

When we set the pin to high(1), the LED lights up in white; if we set to low(0), it will be off.

![3bottom](media/3bottom.png)

#### Wiring Diagram

![3101](media/3101.png)

#### Test Code

Open KidsBlock and connect to the board, click **File --> Load from your computer**.

![3111](media/3111.png)

Choose D:\Code\1.Code_kidsuno to open **3.1Light_on.sb3**.

![3102](media/3102.png)

Click ![3209](media/3209.png) to connect to COM port and then ![2210](media/2210.png).

#### Explanation

![5top](media/5top.png)

**Code Blocks**

|            Blocks             |          Code block           |
| :---------------------------: | :---------------------------: |
|  ![Events](media/Events.png)  |   ![begin](media/begin.png)   |
|       ![P](media/P.png)       | ![setmode](media/setmode.png) |
|       ![P](media/P.png)       |  ![setout](media/setout.png)  |
| ![Control](media/Control.png) | ![forever](media/forever.png) |
| ![Control](media/Control.png) |    ![wait](media/wait.png)    |

![line5](media/line5.png)

**Conceive**

1. **Initialization**

   Set pin mode.

   ![3103](media/3103.png)

   <br>

   **Build blocks:**

   ① Drag ![begin](media/begin.png) and ![setmode](media/setmode.png) to the editing area.

   ② Click the triangle to choose pin 5.

   ![3105](media/3105.png)

   ③ Modify the mode into output .

   Three pin mode:

   - input
   - output
   - input-pullup

   ![6top](media/6top.png)

   Q ：Why output?

   A ：<span style="color: rgb(10, 10, 200);">The code is written for the mainboard.</span> For the board, pin D5 is outputting power levels (high or low) to the connected module.

   ![6bottom](media/6bottom.png)

![line3](media/line3.png)

2. **Main Code**

   Loop: LED lights on for 1s and goes off for 1s, in a loop.

   ![3104](media/3104.png)

   <br>

   **Build blocks:**

   ① Drag ![forever](media/forever.png).This is a loop code, in which codes will run forever.

   ② Drag ![setout](media/setout.png) into "forever".

   There are two power level to output: 

   - high
   - low
   
   Choose pin to 5 and output high.

   ③ Drag ![wait](media/wait.png) into  "forever". This is a delay code.

   ![6top](media/6top.png)

   Q ：Why delay 1s?

   A ：If you output a high level to LED, it will be always on. Yet, we add a delay of 1s, so it lights up for only 1s. Delay time is the ON/OFF time of LED.

   ![6bottom](media/6bottom.png)

   Pin outputs high for 1s:

   ![3106](media/3106.png)

   ④ Right-click the code and choose "Duplicate".

   ![3107](media/3107.png)

   As follows:

   ![3108](media/3108.png)

   Set the output to low. Pin 5 outputs low for 1s.

   ![3109](media/3109.png)

   LED will lights on for 1s and goes off for 1s, in a loop.

![5bottom](media/5bottom.png)

#### Test Result

![4top](media/4top.png)

After uploading code, the LED module will flash with an interval of 1s (on for 1s and off for 1s).

![3102](media/3102.gif)

![4bottom](media/4bottom.png)

---

### 3.2 RGB LED Module (Common Anode)

![1top](media/1top.png)

![KD2079](media/KD2079.png)

RGB LED is imaged in the intersection of three primary colors (RGB): red, green and blue. Both white LED and RGB LED are able to emit white light. The former is presented directly in white, while the latter is mixed with red, green and blue.

**Trichromatic Theory**

![3201](media/3201.jpg)

Human eyes are sensitive to RGB colors. Most colors can be synthesized by RGB in different proportions. Therefore, the vast majority of monochromatic light can also be decomposed into RGB colors. This is the most basic principle of colorimetry --- trichromatic theory.

Red, green and blue lights are called additive primary colors because by the combination of these three primaries in different proportion, various colored lights will produce. Similarly, there are also subtractive ones. So we may add or/and subtract colors as needed. 

The three primary colors of the paint can not compose white, yet, with optical elements, those of light can do it, which is mixed by **three equal parts of R, G, B**.

![1bottom](media/1bottom.png)

#### Parameters

![2top](media/2top.png)

Operating voltage: DC 3.3 ~ 5V 

Current: 19.5 mA

Maximum power: 0.975 W

Operating temperature: -10°C ~ +50°C

Dimensions: 24 x 48 x 18 mm (without housing)

Positioning holes: diameter of 4.8 mm

Interface: telephone socket

![2bottom](media/2bottom.png)

#### Principle

![3top](media/3top.png)

This RGB LED integrates 3 LED inside: red, green and blue.

This RGB LED diode is designed with 4 pins, among which three control LED pins of R, G and B, and one is common anode, which need to be connect to power positive.

When using, we need to connect this module to the white ports of the mainboard.

In this experiment, we connect the RGB LED module to white port 1. According to the board ports view, R pin is connect to D3, G to D5 and B to D6.

When we set the pins to high(1), the LED lights up in corresponding color; if we set to low(0), it will be off.

![3bottom](media/3bottom.png)

#### Wiring Diagram

![3202](media/3202.png)

#### Test Code

Open KidsBlock and connect the board to computer. Choose **File --> Load from your computer**.

![3111](media/3111.png)

Choose path D:\Code\1.Code_kidsuno and open **3.2RGB.sb3**.

![3203](media/3203.png)

Click ![3209](media/3209.png) to connect to port and then ![2210](media/2210.png) the code.

#### Explanations

![5top](media/5top.png)

**Code Blocks**

|            Blocks             |          Code block           |
| :---------------------------: | :---------------------------: |
|  ![Events](media/Events.png)  |   ![begin](media/begin.png)   |
|       ![P](media/P.png)       | ![setmode](media/setmode.png) |
|       ![P](media/P.png)       |  ![setout](media/setout.png)  |
| ![Control](media/Control.png) | ![forever](media/forever.png) |
| ![Control](media/Control.png) |    ![wait](media/wait.png)    |

![line5](media/line5.png)

**Conceive:**

The framework of the code is similar to the previous project, so you may have a reference. 

1. **Initialization**

   Set pin mode.

   ![3204](media/3204.png)

![line3](media/line3.png)

2. **Main code**

   Loop: LED lights up in red, green, blue and white for 1s each. 

   ![3205](media/3205.png)

![5bottom](media/5bottom.png)

#### Test Result

![4top](media/4top.png)

After uploading code, the RGB LED will circulate to light up in red, green, blue and white respectively, each color for 1s, in a circulation.

![3202](media/3202.gif)



![4bottom](media/4bottom.png)

---

### 3.3 Photo Interrupter

![1top](media/1top.png)

![KD2086](media/KD2086.png)

Photo interrupter works based on photoresistor and light source. 

Generally, this module is composed of two photoelectric components: light source and the light receiver. The light source is usually an LED, while the light receiver consists of a photosensitive element and a signal amplifier. When light is blocked, the photosensitive element receives no light, so its resistance value changes. This change will be converted into an electrical signal and then processed.

![1bottom](media/1bottom.png)

#### Parameters

![2top](media/2top.png)

Operating voltage: DC 3.3 ~ 5V 

Operating current: 24 mA

Maximum power: 0.12 W

Operating temperature: -10°C ~ +50°C

Control signal: digital signal

Dimensions: 24 x 32 x 18 mm (without housing)

Positioning holes: diameter of 4.8 mm

Interface: telephone socket

![2bottom](media/2bottom.png)

#### Principle

![3top](media/3top.png)

Modules with blue housing are digital ones, so we should connect to digital io pins of the mainboard (ports with blue).

In this experiment, we connect the module to port 3. According to the board ports view, the digital pin at port 3 is D3.

When objects block lights, the module outputs high; if not, it outputs low.

![3bottom](media/3bottom.png)

#### Wiring Diagram

![3301](media/3301.png)

#### Test Code

Open KidsBlock and connect the board to computer. Choose **File --> Load from your computer**.

![3111](media/3111.png)

Choose path D:\Code\1.Code_kidsuno and open **3.3Photo_Interrupt.sb3**.

![3302](media/3302.png)

Click ![3209](media/3209.png) to connect to port and then ![2210](media/2210.png).

#### Explanations

![5top](media/5top.png)

**Code Blocks**

|              Blocks               |               Code block                |
| :-------------------------------: | :-------------------------------------: |
|    ![Events](media/Events.png)    |        ![begin](media/begin.png)        |
|         ![P](media/P.png)         |      ![setmode](media/setmode.png)      |
|         ![P](media/P.png)         |  ![readdigital](media/readdigital.png)  |
|    ![Serial](media/Serial.png)    |  ![serialbegin](media/serialbegin.png)  |
|    ![Serial](media/Serial.png)    |  ![serialprint](media/serialprint.png)  |
|      ![Vari](media/Vari.png)      | ![variablename](media/variablename.png) |
|      ![Vari](media/Vari.png)      |  ![setvariable](media/setvariable.png)  |
|      ![Vari](media/Vari.png)      |     ![variable](media/variable.png)     |
| ![Operators](media/Operators.png) |          ![not](media/not.png)          |
| ![Operators](media/Operators.png) |            ![=](media/=.png)            |
| ![Operators](media/Operators.png) |            ![+](media/+.png)            |
|   ![Control](media/Control.png)   |      ![forever](media/forever.png)      |
|   ![Control](media/Control.png)   |           ![if](media/if.png)           |
|   ![Control](media/Control.png)   |         ![wait](media/wait.png)         |

![line5](media/line5.png)

**Conceive:**

1. **Initialization**

   Set pin mode and serial monitor first.

   ![3303](media/3303.png)

   <br>

   **Build blocks:**

   ① Drag ![begin](media/begin.png), ![setmode](media/setmode.png) and ![serialbegin](media/serialbegin.png) to the editing area as above.

   ![serialbegin](media/serialbegin.png) is used to set baud rate and initialize serial monitor. If you need a serial port in an experiment, this code block will be necessary, or else the monitor may fails to print results. 

   ② Drag ![variablename](media/variablename.png) to the editing area and duplicate it twice, and set them as shown above. 

   This block will define a new variable whose range(Global or Local), type and initial value can be set.

![line3](media/line3.png)

2. **Main code:**

   Loop: Cumulatively read the values of the module and print them.

   ![3304](media/3304.png)

   <br>

   **Build blocks:**

   ① Drag ![forever](media/forever.png), ![setvariable](media/setvariable.png), ![readdigital](media/readdigital.png) to the editing area, and place them as follows:

   ![3305](media/3305.png)

   The module is connect to D3 on the board so we set to read D3 pin value and assign it to State.

   ② ![=](media/=.png) is an operation that it determines whether the two values equal each other. If yes, the condition is True.

   ![not](media/not.png) denies the condition in it.

   ![variable](media/variable.png) is a variable.

   Drag ![=](media/=.png), ![variable](media/variable.png) and ![not](media/not.png) to the editing area and put them as follows:

   ![3307](media/3307.png)

   Place it in the condition of ![not](media/not.png).

   ![3308](media/3308.png)

   It means: the value of variable State <span style="color: rgb(10, 10, 200);">**≠**</span> the value of variable lastState.

   ③ ![if](media/if.png) determines whether the condition is true. If it is, codes in it will be executed. If not, codes in it will be skipped.

   Put ![if](media/if.png) in "forever".

   Combine them as follows:

   ![3309](media/3309.png)

   These blocks reads the value of D3 and assigns it to variable State, and then it determines whether State ≠ lastState.

   ④ Build ![if](media/if.png), ![=](media/=.png) and ![variable](media/variable.png) as follows:

   ![3310](media/3310.png)

   Then put this combination into "if" as shown below:

   ![3311](media/3311.png)

   These blocks reads the value of D3 and assigns it to State, and then it determines whether State ≠ lastState.

   - State ≠ lastState: execute the second "if" block and determine whether State =1.
   - State = lastState: skip.
   
   ⑤ ![+](media/+.png) is an operation whose result is the sum of these two values.
   
   Drag ![+](media/+.png) into the editing area.
   
   Set the left one to PushCounter and the right one to 1: 
   
   ![3312](media/3312.png)
   
   Put ![setvariable](media/setvariable.png), ![3312](media/3312.png) and ![serialprint](media/serialprint.png) as follows:
   
   ![3313](media/3313.png)
   
   In these blocks, a **nested-if structure** is adopted: an **if statement** in another **if**. Let's have a look at the operational logic diagram:
   
   ![3314](media/3314.png)
   
   ① Assign the value output by the photo interrupter to State
   
   ② Determine whether State ≠ lastState
   
   - State ≠ lastState: execute the next if statement
   - State = lastState: exit if loop to execute ⑤
   
   ③ (Precondition: State ≠ lastState) Determine whether State = 1

   - State = 1: PushCounter +1 and output it.
   - State ≠ 1: exit if loop.
   
   ④ (Precondition: State ≠ lastState, State = 1) PushCounter +1 and print the value on Shell.
   
   ⑤  Assign the value of State to lastState
   
   
   
   Initial Settings:
   
   | Initial state                                                |          |
   | ------------------------------------------------------------ | -------- |
   | State: the present value output by the sensor signal terminal | set to 0 |
   | lastState: the last value output by the sensor signal terminal | set to 0 |
   | PushCounter: the number of times of light being interrupted  | set to 0 |
   
   Execution:
   
   | State                                      |                                                              |
   | ------------------------------------------ | ------------------------------------------------------------ |
   | the object passes through the groove once  | the initial value of lastState is 0; State detects object so its value is 1.<br>State ≠ lastState, State = 1<br>PushCounter+1, and output the value.<br/>lastState = State, lastState = 1 |
   | the object leaves from the groove          | lastState = 1; State detects no object so its value is 0.<br>State ≠ lastState, State = 0<br>lastState = State, lastState = 0 |
   | the object passes through the groove again | lastState = 0; State detects object so its value is 1.<br />State ≠ lastState, State = 1<br/>PushCounter+1, and output the value.<br/>lastState = 1 |
   | the object leaves from the groove          | lastState = 1; State detects no object so its value is 0.<br>State ≠ lastState, State = 0<br/>lastState = 0 |

![5bottom](media/5bottom.png)

#### Test Result

![4top](media/4top.png)

<span style="color: rgb(2550, 10, 50);">NOTE: Before uploading code, please set baud rate first to avoid garbled words.</span>

Click ![3316](media/3316.png) and set Buadrate to 9600.

![3317](media/3317.png)

After uploading code, place an opaque object in in the sensor groove and then remove it, so the light will be interrupted once. The serial monitor will print the number of times of light being interrupted. 

![3315](media/3315.gif)

![4bottom](media/4bottom.png)

---

### 3.4 Capacitive Touch Sensor

![1top](media/1top.png)

![KD2087](media/KD2087.png)

On the capacitive touch sensor, a touch switch is reserved to enable switch function through its variable area.

After powering on, the sensor requires about 0.5 seconds to stabilize itself. During this time, please do not touch it. Its all functions are disabled due to a self-calibration, whose cycle is about 4 seconds.

![1bottom](media/1bottom.png)

#### Parameters

![2top](media/2top.png)

Operating voltage: DC 3.3 ~ 5V 

Operating current: 3 mA

Maximum power: 0.015 W

Operating temperature: -10°C ~ +50°C

Input signal: digital signal

Dimensions: 24 x 48 x 18 mm (without housing)

Positioning holes: diameter of 4.8 mm

Interface: telephone socket

![2bottom](media/2bottom.png)

#### Principle

![3top](media/3top.png)

Modules with blue housing are digital ones, so we should connect to digital io pins of the mainboard (ports with blue).

In this experiment, we connect the module to port 4. According to the board ports view, the digital io pin at port 4 is D2.

When we touch the capacitive area on the sensor, the sensor outputs high(1) and the on-board red LED lights up; when we release, it outputs low(0) and the LED goes off.

![3bottom](media/3bottom.png)

#### Wiring Diagram

![3401](media/3401.png)

#### Test Code

Open KidsBlock and connect the board to computer. Choose **File --> Load from your computer**.

![3111](media/3111.png)

Choose path D:\Code\1.Code_kidsuno and open **3.4Touch.sb3**.

![3402](media/3402.png)

Click ![3209](media/3209.png) to connect to port and then ![2210](media/2210.png) the code.

#### Explanations

![5top](media/5top.png)

**Code Blocks**

|              Blocks               |              Code block               |
| :-------------------------------: | :-----------------------------------: |
|    ![Events](media/Events.png)    |       ![begin](media/begin.png)       |
|         ![P](media/P.png)         |     ![setmode](media/setmode.png)     |
|         ![P](media/P.png)         | ![readdigital](media/readdigital.png) |
|    ![Serial](media/Serial.png)    | ![serialbegin](media/serialbegin.png) |
|    ![Serial](media/Serial.png)    | ![serialprint](media/serialprint.png) |
| ![Operators](media/Operators.png) |           ![=](media/=.png)           |
|   ![Control](media/Control.png)   |     ![forever](media/forever.png)     |
|   ![Control](media/Control.png)   |      ![ifelse](media/ifelse.png)      |
|   ![Control](media/Control.png)   |        ![wait](media/wait.png)        |

![line5](media/line5.png)

**Conceive:**

1. **Initialization**

   Set pin mode and initialize serial port.

   ![3403](media/3403.png)

![line3](media/line3.png)

2. **Main Code**

   Loop: determine whether the value of pin D2 equals 1.

   - the value = 1: the module is touched and the serial monitor prints *You pressed the button !* 
   - the value ≠ 1: the module is not touched and the serial monitor prints *You loosen the button !* 

   Finally, add a delay of 0.1s: refresh the outputs every 0.1s.

![3404](media/3404.png)

![5bottom](media/5bottom.png)

#### Test Result

![4top](media/4top.png)

<span style="color: rgb(2550, 10, 50);">NOTE: Before uploading code, please set baud rate first to avoid garbled words.</span>

Click![3316](media/3316.png) and set Buadrate to 9600.

![3317](media/3317.png)

After uploading code, touch the capacitive area on the sensor, and the monitor will print *You pressed the button!*. Release the touch switch, and it prints *You loosen the button!* .

![3405](media/3405.png)

![4bottom](media/4bottom.png)

---

### 3.5 TM1650 4-digit Tube Display

![1top](media/1top.png)

![KD2088](media/KD2088.png)

The module integrates 0.36-inch common cathode 4-digit tube display which is in red when lighting up. Its driver chip is TM1650, a chip for LED drive control special circuit. When using, we only need 2 signal wires to control the digital tube.

![1bottom](media/1bottom.png)

#### Parameters

![2top](media/2top.png)

Operating voltage: DC 3.3 ~ 5V 

Operating current: 42 mA

Maximum power: 0.21 W

Operating temperature: -10°C ~ +50°C

Dimensions: 24 x 48 x 18 mm (without housing)

Positioning holes: diameter of 4.8 mm

Interface: telephone socket

![2bottom](media/2bottom.png)

#### Principle

![3top](media/3top.png)

TM1650 adopts a two-wire serial transmission protocol (not the standard I2C protocol). The chip communicates with MCU to drive digital tube only by two pins, which greatly saves pins. 

During using, this module needs to be connected to the ports in green on th board.

However, first of all, we need to import the TM1650 library.

![3bottom](media/3bottom.png)

#### Wiring Diagram

![3501](media/3501.png)

#### Test Code

Open KidsBlock and connect the board to computer. Choose **File --> Load from your computer**.

![3111](media/3111.png)

Choose path D:\Code\1.Code_kidsuno and open **3.5Four-digit numeral tube.sb3**.

![3502](media/3502.png)

Click ![3209](media/3209.png) to connect to port and then ![2210](media/2210.png) the code.

#### Explanations

![5top](media/5top.png)

**Code Blocks**

|                    Blocks                     |                         Code block                          |
| :-------------------------------------------: | :---------------------------------------------------------: |
|          ![Events](media/Events.png)          |                  ![begin](media/begin.png)                  |
| ![digital_display](media/digital_display.png) |  ![digital_display_clear](media/digital_display_clear.png)  |
| ![digital_display](media/digital_display.png) | ![digital_display_string](media/digital_display_string.png) |
|            ![Vari](media/Vari.png)            |           ![variablename](media/variablename.png)           |
|            ![Vari](media/Vari.png)            |               ![variable](media/variable.png)               |
|            ![Vari](media/Vari.png)            |             ![variable++](media/variable++.png)             |
|            ![Vari](media/Vari.png)            |            ![setvariable](media/setvariable.png)            |
|       ![Operators](media/Operators.png)       |                   ![less](media/less.png)                   |
|            ![Data](media/Data.png)            |                ![convert](media/convert.png)                |
|         ![Control](media/Control.png)         |                ![forever](media/forever.png)                |
|         ![Control](media/Control.png)         |                 ![ifelse](media/ifelse.png)                 |
|         ![Control](media/Control.png)         |                   ![wait](media/wait.png)                   |

![line5](media/line5.png)

**Conceive**

1. **Initialization**

   Initialize the digit tube first. Define an integer variable i with an initial value of 0.

   ![3503](media/3503.png)
   
   <br>
   
   **Build blocks:**
   
   ① Click ![add](media/add.png) and choose Display, find and click **Four Digital Tube TM1650_IIC** to add this module.
   
   ![3523](media/3523.png)
   
   Click Back.
   
   ![3524](media/3524.png)
   
   This module is successfully added.
   
   ![3525](media/3525.png)
   
   ② ![begin](media/begin.png).
   
   ③ Add ![digital_display_clear](media/digital_display_clear.png) under the "begin" block.
   
   ![3518](media/3518.png)
   
   This block initializes the TM1650 four-digit tube module. Three modes are optional: clear, ON, OFF.
   
   ![3519](media/3519.png)
   
   ④ Duplicate ![digital_display_clear](media/digital_display_clear.png).
   
   ![3520](media/3520.png)
   
   As follows: 
   
   ![3521](media/3521.png)
   
   Modify its mode to ON to turn on this module.
   
   ![3522](media/3522.png)
   
   ⑤ Put ![variablename](media/variablename.png) below and name the variable to i.

![line3](media/line3.png)

2. **Main Code**

   Loop: display 0 ~ 999 in order, refresh the display every 0.01s.

   ![3504](media/3504.png)

   <br>

   **Build blocks:**

   ① ![forever](media/forever.png)

   ② Place ![ifelse](media/ifelse.png) in the "forever".

   ③ Find ![less](media/less.png), and put  ![variable](media/variable.png) into the left of ![less](media/less.png) and name the variable to i; set the value on the right to 999.

   ![3505](media/3505.png)

   These blocks mean variable i < 999. Put them in "if else" to set as a condition.

   ![3506](media/3506.png)

   ④ Put ![digital_display_string](media/digital_display_string.png) under if. This block sets the module to display messages and number strings. By default, the message is abcd.

   <span style="color: rgb(10, 10, 200);">For this module, the displayed content must be in string form, so we cannot directly put the variable block into it. We need convert the variable to a string so that it can be shown on the tube.</span>

   ![3507](media/3507.png)

   Drag ![convert](media/convert.png) into the "display" block and set the output type. Three types are optional: integer, decimal, string.

   ![3508](media/3508.png)

   Duplicate the variable i and put it into the "display" block.

   ![3509](media/3509.png)

   ![3510](media/3510.png)

   As follows:

   ![3511](media/3511.png)

   Modify the type into string.

   ![3512](media/3512.png)

   These blocks will convert the variable i to string form, and display on the 4-digit tube.

   ⑤ Add ![variable++](media/variable++.png) in if and name the variable to i. This block enables a variable to automatically increase or decrease.

   ++: automatically increase 1

   --: automatically decrease 1

   ![3514](media/3514.png)
   
   We have learned a similar code in chapter 3.3, which also make the variable to increase 1: ![3515](media/3515.png)
   
   ![3513](media/3513.png)
   
   ⑥ Put ![setvariable](media/setvariable.png) under else and modify the variable name to i. It sets i to 0.
   
   ![3516](media/3516.png)
   
   **Examples:**
   
   In initialization, we set the initial value of i to 0.
   
   In first loop, i = 0, so i < 999, the value 0 will be converted into a string 0 to display on the tube. Next,  i++ executes so i = 1.
   
   In second loop, i = 1, so i < 999, the value 1 will be converted into a string 1 to display on the tube. Next,  i++ executes so i = 2.
   
   ... ...
   
   In the thousandth loop, i = 999, at this time i is not lower than 999, so i is set to 0.
   
   In the loop of number thousand and one, i = 0, the value 0 will be converted into a string 0 to display on the tube. Next,  i++ executes so i = 1.
   
   ... ...
   
   So then the displayed number will circulate within 0 ~ 999
   
   ⑦ Add a delay ![wait](media/wait.png) and set to 0.01s.
   
   Therefore, numbers on the tube will be refreshed every 0.01s.
   
   ![3517](media/3517.png)
   

![5bottom](media/5bottom.png)

#### Test Result

![4top](media/4top.png)

After uploading code, the module displays number from 0 to 999, and the results refreshes every 0.01s.

![3505](media/3505.gif)



![4bottom](media/4bottom.png)

---

###  3.6 DS18B20 Temperature Sensor

![1top](media/1top.png)

![KD2094](media/KD2094.png)

The DS18B20 sensor is a digital module used to detect temperature. It outputs digital signal and features small size, strong anti-interference ability and high precision.

![1bottom](media/1bottom.png)

#### Parameters

![2top](media/2top.png)

Operating voltage: DC 3.3 ~ 5V 

Current: 0.15 mA

Maximum power: 0.00075 W

Temperature detection range: -55°C ~ +125°C (accuracy of ±0.4°C within -10°C ~ +70°C)

Operating temperature: -10°C ~ +50°C

Dimensions: 24 x 32 x 18 mm (without housing)

Positioning holes: diameter of 4.8 mm

Interface: telephone socket

![2bottom](media/2bottom.png)

#### Principle

![3top](media/3top.png)

Modules with blue housing are digital ones, so we should connect to digital io pins of the mainboard (ports with blue).

In this experiment, we connect the module to port 6. According to the board ports view, the digital io pin at port 6 is D4.

![3bottom](media/3bottom.png)

#### Wiring Diagram

![3601](media/3601.png)

#### Test Code

Open KidsBlock and connect the board to computer. Choose **File --> Load from your computer**.

![3111](media/3111.png)

Choose path D:\Code\1.Code_kidsuno and open **3.6Temperature.sb3**.

![3602](media/3602.png)

Click ![3209](media/3209.png)to connect to port and then ![2210](media/2210.png) the code.

#### Explanations

![5top](media/5top.png)

**Code Blocks**

|            Blocks             |              Code block               |
| :---------------------------: | :-----------------------------------: |
|  ![Events](media/Events.png)  |       ![begin](media/begin.png)       |
|  ![Serial](media/Serial.png)  | ![serialbegin](media/serialbegin.png) |
|  ![Serial](media/Serial.png)  | ![serialprint](media/serialprint.png) |
|    ![Temp](media/Temp.png)    | ![temperature](media/temperature.png) |
| ![Control](media/Control.png) |     ![forever](media/forever.png)     |

![line5](media/line5.png)

**Build blocks:**

Click ![add](media/add.png) to add library **18b20**.

![3609](media/3609.png)

1. **Initialization**

   Initialize the serial port.

   ![3603](media/3603.png)

![line3](media/line3.png)

2. **Main Code**

   Loop: Read the temperature value detected by DS18B20 sensor and print it without wrapping.

   ![3604](media/3604.png)

   <br>

   **Build blocks:**

   ① Drag ![forever](media/forever.png), ![serialprint](media/serialprint.png) and ![temperature](media/temperature.png) to the editing area and place them as the following: 

   ![3610](media/3610.png)

   These blocks will print the the temperature value detected by pin D4 (DS18B20 temperature sensor) on the serial monitor without wrapping. The value is in the unit of °C, or you can change it to F in the code.

   ![6top](media/6top.png)

   Q ：Why outputting the temperature value without wrapping?

   No wrap: these results will be output in the same line.

   Wrap: these results will be output in the next line.

   If we set to wrap to output, the unit °C and the temperature value cannot be displayed on the same line.

   Wrap:

   ![3607](media/3607.png)

   No wrap:

   ![3608](media/3608.png)

   A ：We set to output without wrapping to make the value and °C in the same line.

   ![6bottom](media/6bottom.png)

   ② Add ![serialprint](media/serialprint.png) in "forever" and set the print message to "  °C". <span style="color: rgb(10, 10, 200);">There are two spaces before °C.</span>

   ![3611](media/3611.png)

   ![6top](media/6top.png)
   
   Q ：Why two spaces? 
   
   If here is no space, the unit °C will be very close to the value.
   
   No space:
   
   ![3605](media/3605.png)
   
   With spaces:
   
   ![3606](media/3606.png)
   
   A ：For convenient to check results, we add two spaces before °C.
   
   ![6bottom](media/6bottom.png)

![5bottom](media/5bottom.png)

#### Test Result

![4top](media/4top.png)

<span style="color: rgb(2550, 10, 50);">NOTE: Before uploading code, please set baud rate first to avoid garbled words.</span>

Click![3316](media/3316.png) to set Buadrate to 9600.

![3317](media/3317.png)

After uploading code, the serial monitor prints the temperature value detected by DS18B20 sensor.

![3605](media/3605.png)

![4bottom](media/4bottom.png)

---

### 3.7 Ultrasonic Sensor

![1top](media/1top.png)

![MD0017](media/MD0017.png)

When bats fly, they produce ultrasonic waves from their throats, which are emitted from their mouths. When ultrasonic waves encounter an insect or obstacle, they are reflected back and then picked up by the bats' ears. Bats calculate the distance by the reflected wave and also determine whether the target is an insect or an obstacle. 

Therefore, scientists developed ultrasonic ranging. The ultrasonic sensors in this experiment are based on bionic science.

![3701](media/3701.png)

![1bottom](media/1bottom.png)

#### Parameters

![2top](media/2top.png)

Operating voltage: DC 5V 

Operating current: 15 mA 

Operating frequency: 40 KHz

Measuring angle: ≤ 15°C

Ultrasonic range: 2 cm ~ 400cm (peak)

Operating temperature: -10°C ~ +50°C

Output signal: analog signal

Dimensions of ultrasonic sensor: 20 x 45 x 12 mm (without pins)

Dimensions of ultrasonic sensor converter: 24 x 32 x 18 mm (without housing)

Positioning holes: diameter of 4.8 mm

Interface: telephone socket

![2bottom](media/2bottom.png)

#### Principle

![3top](media/3top.png)

![3702](media/3702.png)

After the ultrasonic sensor receives the trigger signal (the board sends a high level to the Trig pin), the module automatically sends eight 40KHZ square waves and starts timing. 

The ultrasonic wave propagates in the air and immediately reflects back when it encounters the obstacle surface on the way (the Echo pin sends a high level to the board). 

The ultrasonic receiver stops timing as soon as it receives the reflected waves. So then the module will record the interval between the initial transmission of the ultrasonic wave and the reception of the echo.

This is how the sensor calculate the distance from the obstacle.

![3703](media/3703.png)

**Working Principle:**

1. Trig pin enables the distance detection and transmits a high level signal for at least 10us.

2. Circularly send eight 40KHz square waves, and automatically detect whether there is a response signal.

3. If there is a response, Echo pin will output high lasting from ultrasonic wave transmitting to receiving.

	Calculation of the distance between the ultrasonic sensor and the obstacle:

	Distance = high level duration × 340m/s ÷ 2

	(The sound speed varies from the nature and state of the medium. In air, the sound speed is about 340m/s at 1 standard atmosphere and 15 °C)

Since the ultrasonic module pins cannot be directly connected to the board, a converter module is required to connect it to the port in yellow on the board.

![KD2099](media/KD2099.png)

In this experiment, we connect the module to port 7. According to the board ports view, Trig pin is connected to D8 and Echo is to A0.

![3bottom](media/3bottom.png)

#### Wiring Diagram

![3704](media/3704.png)

#### Test Code

Open KidsBlock and connect the board to computer. Choose **File --> Load from your computer**.

![3111](media/3111.png)

Choose path D:\Code\1.Code_kidsuno and open **3.7Ultrasonic.sb3**.

![3705](media/3705.png)

Click ![3209](media/3209.png) to connect to port and then ![2210](media/2210.png).

#### Explanations

![5top](media/5top.png)

**Code Blocks**

|            Blocks             |              Code block               |
| :---------------------------: | :-----------------------------------: |
|  ![Events](media/Events.png)  |       ![begin](media/begin.png)       |
|  ![Serial](media/Serial.png)  | ![serialbegin](media/serialbegin.png) |
|  ![Serial](media/Serial.png)  | ![serialprint](media/serialprint.png) |
|       ![U](media/U.png)       |  ![ultrasonic](media/ultrasonic.png)  |
| ![Control](media/Control.png) |     ![forever](media/forever.png)     |
| ![Control](media/Control.png) |        ![wait](media/wait.png)        |

![line5](media/line5.png)

**Build blocks:**

Click ![add](media/add.png) to add library **Ultrasonic**.

![3709](media/3709.png)

1. **Initialization**

   Initialize the serial port.

   ![3603](media/3603.png)

![line3](media/line3.png)

2. **Main Code**

   Loop: print the distance value detected by the ultrasonic sensor, and refresh the results every 0.1s.

   ![3707](media/3707.png)

![5bottom](media/5bottom.png)

#### Test Result

![4top](media/4top.png)

After uploading code, the serial monitor prints the distance value between the ultrasonic sensor and the obstacle.

![3708](media/3708.png)

![4bottom](media/4bottom.png)

---

### 3.8 Five-channel AD Button Module

![1top](media/1top.png)

![KD2108](media/KD2108.png)

When using, the five-channel AD button module only occupies one analog port, which greatly saves ports and pins. In analog acquisition, when we press different buttons, it outputs different voltages.

![1bottom](media/1bottom.png)

#### Parameters

![2top](media/2top.png)

Operating voltage: DC 3.3 ~ 5V 

Operating current: 2.5 mA

Operating power: 0.0125 W

Operating temperature: -10°C ~ +50°C

Output signal: analog signal

Dimensions: 24 x 48 x 18 mm (without housing)

Positioning holes: diameter of 4.8 mm

Interface: telephone socket

![2bottom](media/2bottom.png)

#### Principle

![3top](media/3top.png)

Due to the circuit design, the corresponding output voltage varies when we press different button. 

The voltage value is read by the board ADC and then compared with the pre-determined voltage range of each button, so that we can determine which button is pressed.

![peg](media/peg.png)

![line3](media/line3.png)

**What is ADC?**

ADC(Analog to Digital Converter) converts analog values to digital ones. The ADC acquisition is integrated in our board, so you can call it directly. 

**Kidspico ADC Parameters**

1. Reference voltage: 5V

1. Resolution: 10bit

   A n-bit ADC means this ADC contains 2ⁿ scales. 

   10-bit ADC contains $2^{10}=1024$ scales, and it outputs totally 1024 digital values (including from 0～ 1023), each scale is $\frac{5}{1023}≈0.00489(V)$

2. General ADC input voltage calculation:

   <font face="courier New" color="black" size=6>$ Vin= \frac {AVDD_{ADC}}{2^{Resolution Bit}-1}*ReadData$</font> 
   
   $AVDD_{ADC}$: Reference voltage

![line3](media/line3.png)

Modules with red housing are analog ones, so we should connect to analog io pins of the mainboard (ports with red).

In this experiment, we connect the module to port 8. According to the board ports view, the analog io pin at port 8 is A7.

![3bottom](media/3bottom.png)

#### Wiring Diagram

![3801](media/3801.png)

#### Test Code

Open KidsBlock and connect the board to computer. Choose **File --> Load from your computer**.

![3111](media/3111.png)

Choose path D:\Code\1.Code_kidsuno and open **3.8Five-way AD.sb3**.

![3802](media/3802.png)

Click ![3209](media/3209.png) to connect to port and then ![2210](media/2210.png).

#### Explanations

![5top](media/5top.png)

**Code Blocks**

|              Blocks               |               Code block                |
| :-------------------------------: | :-------------------------------------: |
|    ![Events](media/Events.png)    |        ![begin](media/begin.png)        |
|         ![P](media/P.png)         |      ![setmode](media/setmode.png)      |
|         ![P](media/P.png)         |   ![readanalog](media/readanalog.png)   |
|    ![Serial](media/Serial.png)    |  ![serialbegin](media/serialbegin.png)  |
|    ![Serial](media/Serial.png)    |  ![serialprint](media/serialprint.png)  |
|      ![Vari](media/Vari.png)      | ![variablename](media/variablename.png) |
|      ![Vari](media/Vari.png)      |  ![setvariable](media/setvariable.png)  |
|      ![Vari](media/Vari.png)      |     ![variable](media/variable.png)     |
| ![Operators](media/Operators.png) |         ![less](media/less.png)         |
| ![Operators](media/Operators.png) |      ![greater](media/greater.png)      |
| ![Operators](media/Operators.png) |          ![and](media/and.png)          |
|   ![Control](media/Control.png)   |      ![forever](media/forever.png)      |
|   ![Control](media/Control.png)   |           ![if](media/if.png)           |
|   ![Control](media/Control.png)   |         ![wait](media/wait.png)         |

![line5](media/line5.png)

**Conceive**

1. **Initialization**

   Set pin mode and initialize the serial port.

   ![3803](media/3803.png)

![line3](media/line3.png)

2. **Main Code**

   Loop: Determine which button is pressed.
   
   ![3804](media/3804.png)
   
   <br>
   
   **Build blocks:**
   
   ① Add blocks ![forever](media/forever.png), ![setvariable](media/setvariable.png), ![readanalog](media/readanalog.png), ![serialprint](media/serialprint.png) and ![variable](media/variable.png) to the editing area as follows:
   
   ![3805](media/3805.png)
   
   ② Add blocks ![if](media/if.png), ![less](media/less.png),  ![variable](media/variable.png) and ![serialprint](media/serialprint.png) as follows: 
   
   ![3806](media/3806.png)
   
   So far, when the ADC value read by pin A7 is less than 100, the serial monitor print “  no key  is pressed”. Note that there are two spaces in the front of the messages, so that the value will be separated from the printing contents.
   
   ③ ![and](media/and.png) is an "and" block. When the two conditions in it are both satisfied, it outputs True.
   
   Add blocks ![less](media/less.png), ![and](media/and.png) and ![greater](media/greater.png)as follows:
   
   ![3808](media/3808.png)
   
   These conditions require the value at pin A7 is within 100 ~ 300.
   
   Add ![if](media/if.png) and ![serialprint](media/serialprint.png) as follows:
   
   ![3807](media/3807.png)
   
   When the ADC value at A7 is within 100 ~ 300, the serial monitor prints “  SW5 is pressed”. Note that there are two spaces in the front of the messages, so that the value will be separated from the printing contents.
   
   ④ Duplicate the "if" block in ③ four times.
   
   ![3809](media/3809.png)
   
   Finally add a delay ![wait](media/wait.png).
   
   ![3810](media/3810.png)
   
   In the same way:
   
   When the ADC value at A7 is within 300 ~ 500, the serial monitor prints “  SW4 is pressed”. 
   
   When the ADC value at A7 is within 500 ~ 700, the serial monitor prints “  SW3 is pressed”. 
   
   When the ADC value at A7 is within 700 ~ 900, the serial monitor prints “  SW2 is pressed”. 
   
   When the ADC value at A7 is within 900 ~ 1024, the serial monitor prints “  SW1 is pressed”. 

![5bottom](media/5bottom.png)

#### Test Result

![4top](media/4top.png)

<span style="color: rgb(2550, 10, 50);">NOTE: Before uploading code, please set baud rate first to avoid garbled words.</span>

Click ![3316](media/3316.png) to set Buadrate to 9600.

![3317](media/3317.png)

![3812](media/3812.png)

<center>Number of Five-channel AD Button Module</center>

After uploading code, press the buttons and the serial monitor will print the corresponding analog value and messages.

![3813](media/3811.png)

![4bottom](media/4bottom.png)

---

### 3.9 130 Motor

![1top](media/1top.png)

![KD2105](media/KD2105.png)

130 motor does not require an additional driver board to enable itself. Also, you may adjust the rotation speed via PWM. Therefore, it is perfect to DIY small projects or crafts.

Please mount the fan on the motor first.

![67800136](media/67800136.png)

![1bottom](media/1bottom.png)

#### Parameters

![2top](media/2top.png)

Operating voltage: DC 3.3 ~ 5V 

Operating current: ≤ 200 mA (peak 350±20% mA)

Maximum power: ≤2 W

Rotation speed: 3.3V (2500±10% rpm); 5V (16000±10% rpm)

Operating temperature: -10°C ~ +50°C

Dimensions: 24 x 48 x 18 mm (without housing)

Positioning holes: diameter of 4.8 mm

Interface: telephone socket

![2bottom](media/2bottom.png)

#### Principle

![3top](media/3top.png)

This motor is a two-channel digital module, so during using, we need to connect to ports in blue or yellow on the board.

We add voltage to both ends of the motor to control its rotation. Within the limit, the greater the voltage is, the faster the rotation speed will be; similarly, the lower the voltage is, the slower the rotation speed will be, and it even can be slow enough till stopping. Besides, the rotation direction also depends on the voltage direction.

There is a certain relationship between PWM duty cycle and voltage. During the PWM cycle, when the duty cycle changes, the high level duration will also change. When the duty cycle is small, the high level duration is short, and the corresponding average voltage is relatively low. On the contrary, when the duty cycle is large, the high level duration will be longer, and the corresponding average voltage is relatively high. 

In simple terms, the (PWM) output voltage is directly proportional to its duty cycle. As the duty cycle increases, the output voltage increases accordingly, and vice versa.

Therefore, <span style="color: rgb(10, 10, 200);">we control the  output voltage through the PWM duty cycle, so then we control the speed of the motor via PWM.</span>

![peg](media/peg.png)

![line3](media/line3.png)

**What is PWM?**

PWM (Pulse width modulation) is a scheme that simulates the change of analog signals by digital signal.

Pulse width is the high level part in a complete square wave cycle. Therefore, PWM is a modulation of high level. Of course, in other words, the cycle is fixed, so it adjust the low level part as well. 

![3901](media/3901.png)

- **PWM frequency**

  Frequency is the number of times the signal goes from high to low level and back to high in 1 second (this is one cycle), that is, how many cycles there are in a second PWM.

  Unit: Hz

  Expression: 50Hz; 100Hz

- **PWM cycle**

  <font face="courier New" color="black" size=6>$ T = \frac {1}{f}$</font>

  <font face="courier New" color="black" size=6>$ Cycle = \frac {1}{Frequency}$</font>

  When frequency is 50Hz, i.e., the cycle is 20ms, there are 50 PWM cycles within 1s.

- **PWM duty cycle**

  Duty cycle is the ratio of the time of the high level to the that of the whole cycle in a cycle.

  Unit: % (1% ~ 100%)

  For example, when we set the duty cycle of an LED, the greater the duty cycle is, the brighter the LED will be.

  ![3902](media/3902.gif)

- **Cycle**: The time of a pulse signal. Frequency is the number cycles in 1s.

- **Pulse width time**: high level time.

![line3](media/line3.png)

**The GPIO ports that outputs PWM on kidsuno: D3, D5, D6, D9, D10, D11.**

In this experiment, the motor we use is designed two control ports: INA and INB.

When the PWM of INA is greater than that of INB, the motor rotates counterclockwise. The greater the difference value is, the faster the speed will be.

![3905](media/3905.png)

When the PWM of INB is greater than that of INA, the motor rotates clockwise. The greater the difference value is, the faster the speed will be.

![3906](media/3906.png)

When both INA and INB are 0, the rotation stops.

In this experiment, we connect the module to port 9. According to the board ports view, we connect the motor INA pin to D10 and INB to D11.

![3bottom](media/3bottom.png)

#### Wiring Diagram

![3904](media/3903.png)

#### Test Code

Open KidsBlock and connect the board to computer. Choose **File --> Load from your computer**.

![3111](media/3111.png)

Choose path D:\Code\1.Code_kidsuno and open **3.9Motor.sb3**.

![3904](media/3904.png)

Click ![3209](media/3209.png) to connect to port and then ![2210](media/2210.png). 

#### Explanations

![5top](media/5top.png)

**Code Blocks**

|            Blocks             |                    Code block                     |
| :---------------------------: | :-----------------------------------------------: |
|  ![Events](media/Events.png)  |             ![begin](media/begin.png)             |
|   ![Motor](media/Motor.png)   | ![Motor_analogWrite](media/Motor_analogWrite.png) |
| ![Control](media/Control.png) |           ![forever](media/forever.png)           |
| ![Control](media/Control.png) |              ![wait](media/wait.png)              |

![line5](media/line5.png)

**Build blocks:**

Click ![add](media/add.png) to add library **DC Motor**.

![3907](media/3907.png)

1. **Initialization**

   Initialize the motor and zero out INA and INB.

   ![3908](media/3908.png)

![line3](media/line3.png)

2. **Main Code**

   Loop: The fan rotates clockwise at a full speed for 2s, at a slowing down speed for 2s, and then stops for 2s. After that, it performs the same actions but in different direction: it rotates counterclockwise.

   ![3909](media/3909.png)

   <br>

   **Build blocks:**

   ① ![forever](media/forever.png)

   ② Add ![Motor_analogWrite](media/Motor_analogWrite.png) and ![wait](media/wait.png) together in "forever".

   Duplicate them five times.

   ![3910](media/3910.png)

   

   So there will be six groups in total.

   (1) ![3911](media/3911.png)

   The PWM value of INA is 0; The PWM value of INB is 255. The PWM of INB is greater than that of INA, so the motor rotates clockwise. The greater the difference value is, the faster the speed will be.

   (2) ![3912](media/3912.png)

   The PWM value of INA is 0; The PWM value of INB is 100. The PWM of INB is greater than that of INA, so the motor rotates clockwise. The difference is smaller than Group One, so the speed will be lower.

   (3) ![3913](media/3913.png)

   The PWM value of INA and INB are both 0, so the motor stops working.

   (4) ![3914](media/3914.png)

   The PWM value of INA is 255; The PWM value of INB is 0. The PWM of INA is greater than that of INB, so the motor rotates counterclockwise. The greater the difference value is, the faster the speed will be.

   (5) ![3915](media/3915.png)

   The PWM value of INA is 255; The PWM value of INB is 100. The PWM of INA is greater than that of INB, so the motor rotates counterclockwise. The difference is smaller than Group Four, so the speed will be lower.

   (6) ![3916](media/3916.png)

   The PWM value of INA and INB are both 255, so the motor stops working.

![5bottom](media/5bottom.png)

#### Test Result

![4top](media/4top.png)

<span style="color: rgb(2550, 10, 50);">**WARNING: Do not hold the fan with your hand before uploading the code. When using, please face the fan to an open place to avoid injury.**</span>

After uploading code, the fan rotates clockwise at a full speed for 2s, at a slowing down speed for 2s, and then stops for 2s. After that, it performs the same actions but in different direction: it rotates counterclockwise.

![4bottom](media/4bottom.png)

---

### 3.10 IR Receiver

![1top](media/1top.png)

![KD2109](media/KD2109.png)

Infrared remote control is one of the most widely used means of communication and remote control. 

IR remote control devices features small size, low power consumption, multiple functions and low cost, so that it is integrated in various equipments, such as recorders, audio equipments and air conditioners.

Herein, the internal IC of this module has been tuned. The receiver outputs digital signals and can receive the standard 38KHz modulated remote control signals.

![1bottom](media/1bottom.png)

#### Parameters

![2top](media/2top.png)

Operating voltage: DC 3.3 ~ 5V

Operating current: 1.5 mA

Maximum power: 0.0075 W

Carrier frequency: 38 KHz

Wave length: 940 λp(nm)

Receiving distance: 6m at 45°; 14m in parallel.

Operating temperature: -10°C ~ +50°C

Dimensions: 24 x 48 x 33.4 mm (without housing)

Positioning holes: diameter of 4.8 mm

Interface: telephone socket

![2bottom](media/2bottom.png)

#### Principle

![3top](media/3top.png)

The transmitting circuit is composed of infrared light-emitting diode, which emits the modulated infrared light wave.

The receiving circuit includes an infrared receiving diode, a triode, or a silicon photocell, which receives the modulated infrared light waves emitted by the transmitter and then converts them into electrical signals. After that, these electrical signals are amplified, filtered and demodulated to restore the encoded instruction signals. The decoded signals can be read and recognized by the board as to perform corresponding operations.

Modules with blue housing are digital ones, so we should connect to digital io pins of the mainboard (ports with blue).

In this experiment, we connect the module to port 1. According to the board ports view, the digital io pin at port 1 is D5.

![3bottom](media/3bottom.png)

#### Wiring Diagram

![31001](media/31001.png)

#### Test Code

Open KidsBlock and connect the board to computer. Choose **File --> Load from your computer**.

![3111](media/3111.png)

Choose path D:\Code\1.Code_kidsuno and open **3.10Infrared Receiver.sb3**.

![31002](media/31002.png)

Click ![3209](media/3209.png) to connect to port and then ![2210](media/2210.png).

#### Explanations

![5top](media/5top.png)

**Code Blocks**

|            Blocks             |              Code block               |
| :---------------------------: | :-----------------------------------: |
|  ![Events](media/Events.png)  |       ![begin](media/begin.png)       |
|  ![Serial](media/Serial.png)  | ![serialbegin](media/serialbegin.png) |
|  ![Serial](media/Serial.png)  | ![serialprint](media/serialprint.png) |
|      ![IR](media/IR.png)      |      ![IR_pin](media/IR_pin.png)      |
|      ![IR](media/IR.png)      | ![IR_Received](media/IR_Received.png) |
|      ![IR](media/IR.png)      |     ![IR_read](media/IR_read.png)     |
|      ![IR](media/IR.png)      |  ![IR_Refresh](media/IR_Refresh.png)  |
| ![Control](media/Control.png) |     ![forever](media/forever.png)     |
| ![Control](media/Control.png) |          ![if](media/if.png)          |
| ![Control](media/Control.png) |        ![wait](media/wait.png)        |

![line5](media/line5.png)

**Build blocks:**

Click ![add](media/add.png) to add library **ir remote**.

![31003](media/31003.png)

1. **Initialization**

   Initialize the serial monitor and set the IR receiver pin to 5.

   ![31004](media/31004.png)

![line3](media/line3.png)

2. **Main Code**

   Loop: Receive the data from IR receiver, and print them on the serial monitor in the format of HEX(hexadecimal). 

   ![31005](media/31005.png)

   <br>

   **Build blocks:**

   ① ![forever](media/forever.png)

   ② Add ![IR_Received](media/IR_Received.png) in the condition box of ![if](media/if.png).

   ③ Put ![serialprint](media/serialprint.png) in "if" and set the printing contents to ![IR_read](media/IR_read.png).

   ![31006](media/31006.png)

   When the receiver receives messages, they will be printed on the serial monitor.

   ④ Add a delay ![wait](media/wait.png) in "if" and set the delay time to 0.5s. A delay will eliminate the button jitters.

   If we do not add a delay, the monitor may outputs some messy strings.

   ![31007](media/31007.png)
   
   ⑤ ![IR_Refresh](media/IR_Refresh.png) refreshes the received data. Without this block, the serial monitor will always print the received data. The module only receives new data after being refreshed.
   

![5bottom](media/5bottom.png)

#### Test Result

![4top](media/4top.png)

<span style="color: rgb(2550, 10, 50);">Before using the infrared remote control, please firstly remove the transparent insulation sheet at the bottom.</span>

![31008](media/31008.png)

<center>Decimal Code of Remote Control</center>

<span style="color: rgb(2550, 10, 50);">NOTE: Before uploading code, please set baud rate first to avoid garbled words.</span>

Click ![3316](media/3316.png) to set the Buadrate to 9600.

![3317](media/3317.png)

After uploading code, align the remote control with the receiver and press any key on it. After receiving signals, the serial monitor prints the corresponding key value, meanwhile, the LED on the infrared receiver flashes.

![31009](media/31009.png)

![4bottom](media/4bottom.png)

---

## 4. Comprehension

### 4.1 Temperature Detection

The fan will monitor the operating temperature. When it is overheat, the fan will start to rotate automatically. 

This temperature detection device adopts a DS18B20 temperature sensor and an 130 motor.

#### Flow

![4101](media/4101.png)

#### Assembly

![line1](media/line1.png)

**Required Components**

![41_00](media/41_00.png)

![line1](media/line1.png)

**Step 1**

![41_01](media/41_01.png)

![line1](media/line1.png)

**Step 2**

![41_02](media/41_02.png)

![line1](media/line1.png)

**Step 3**

![41_03](media/41_03.png)

![line1](media/line1.png)

**Step 4**

![41_04](media/41_04.png)

![line1](media/line1.png)

**Step 5**

![41_05](media/41_05.png)

![line1](media/line1.png)

**Step 6**

![41_06](media/41_06.png)

![line1](media/line1.png)

**Completed**

![41_07](media/41_07.png)

![line1](media/line1.png)

#### Wiring Diagram

![4102](media/4102.png)

#### Test Code

Open KidsBlock and connect the board to computer. Choose **File --> Load from your computer**.

![3111](media/3111.png)

Choose path D:\Code\1.Code_kidsuno and open **4.1Temperature detection.sb3**.

![4103](media/4103.png)

Click ![3209](media/3209.png)  to connect to port and then ![2210](media/2210.png).

#### Explanations

![5top](media/5top.png)

**Code Blocks**

|              Blocks               |                    Code block                     |
| :-------------------------------: | :-----------------------------------------------: |
|    ![Events](media/Events.png)    |             ![begin](media/begin.png)             |
|      ![Vari](media/Vari.png)      |      ![variablename](media/variablename.png)      |
|      ![Vari](media/Vari.png)      |       ![setvariable](media/setvariable.png)       |
|      ![Vari](media/Vari.png)      |          ![variable](media/variable.png)          |
|    ![Serial](media/Serial.png)    |       ![serialbegin](media/serialbegin.png)       |
|    ![Serial](media/Serial.png)    |       ![serialprint](media/serialprint.png)       |
|      ![Temp](media/Temp.png)      |       ![temperature](media/temperature.png)       |
| ![Operators](media/Operators.png) |           ![greater](media/greater.png)           |
|     ![Motor](media/Motor.png)     | ![Motor_analogWrite](media/Motor_analogWrite.png) |
|   ![Control](media/Control.png)   |           ![forever](media/forever.png)           |
|   ![Control](media/Control.png)   |            ![ifelse](media/ifelse.png)            |

![line5](media/line5.png)

**Build blocks:**

Click ![add](media/add.png) to add libraries **18b20** and  **DC Motor**.

![4105](media/4105.png)

1. **Initialization**

   Initialize the serial monitor.

   ![4106](media/4106.png)

![line3](media/line3.png)

2. **Main Code**

   Loop: DS18B20 sensor reads the temperature values and the serial monitor prints them. Then, it determines whether the value is greater than 30°C(this threshold is adjustable).

   - Temperature > 30: fan rotates to cool down.
   - Temperature < = 30: fan stops working.

   ![4107](media/4107.png)

![5bottom](media/5bottom.png)

#### Test Result

![4top](media/4top.png)

After uploading code, the fan will rotate for cooling down when the temperature value exceeds 30°.

You can raise the temperature by pinching the DS18B20 sensor with your finger or lighting a lighter near the sensor. 

<span style="color: rgb(2550, 10, 50);">**WARNING: Please use lighters with the guidance of an adult!**</span>

![4103](media/4103.gif)

![4bottom](media/4bottom.png)

---

### 4.2 Trigger Mode

We design to trigger the fan to automatically work when something approaches to it. This trigger mode integrates an ultrasonic sensor and an 130 motor.

#### Flow

![4201](media/4201.png)

#### Assembly

![line1](media/line1.png)

**Required Components**

![42_00](media/42_00.png)

![line1](media/line1.png)

**Step 1**

![42_01](media/42_01.png)

![line1](media/line1.png)

**Step 2**

![42_02](media/42_02.png)

![line1](media/line1.png)

**Step 3**

![42_03](media/42_03.png)

![line1](media/line1.png)

**Step 4**

![42_04](media/42_04.png)

![line1](media/line1.png)

**Step 5**

![42_05](media/42_05.png)

![line1](media/line1.png)

**Step 6**

![42_06](media/42_06.png)

![line1](media/line1.png)

**Completed**

![42_07](media/42_07.png)

![line1](media/line1.png)

#### Wiring Diagram

![4202](media/4202.png)

#### Test Code

Open KidsBlock and connect the board to computer. Choose **File --> Load from your computer**.

![3111](media/3111.png)

Choose path D:\Code\1.Code_kidsuno and open **4.2Trigger mode.sb3**.

![4203](media/4203.png)

Click ![3209](media/3209.png) to connect to port and then ![2210](media/2210.png).

#### Explanations

![5top](media/5top.png)

**Code Blocks**

|              Blocks               |                    Code block                     |
| :-------------------------------: | :-----------------------------------------------: |
|    ![Events](media/Events.png)    |             ![begin](media/begin.png)             |
|      ![Vari](media/Vari.png)      |      ![variablename](media/variablename.png)      |
|      ![Vari](media/Vari.png)      |       ![setvariable](media/setvariable.png)       |
|      ![Vari](media/Vari.png)      |          ![variable](media/variable.png)          |
|    ![Serial](media/Serial.png)    |       ![serialbegin](media/serialbegin.png)       |
|    ![Serial](media/Serial.png)    |       ![serialprint](media/serialprint.png)       |
|         ![U](media/U.png)         |        ![ultrasonic](media/ultrasonic.png)        |
| ![Operators](media/Operators.png) |              ![less](media/less.png)              |
|     ![Motor](media/Motor.png)     | ![Motor_analogWrite](media/Motor_analogWrite.png) |
|   ![Control](media/Control.png)   |           ![forever](media/forever.png)           |
|   ![Control](media/Control.png)   |            ![ifelse](media/ifelse.png)            |
|   ![Control](media/Control.png)   |              ![wait](media/wait.png)              |

![line5](media/line5.png)

**Build blocks:**

Click ![add](media/add.png) to add libraries **DC Motor** and **Ultrasonic**.

![4205](media/4205.png)

1. **Initialization**

   Initialize the serial port.

   ![4206](media/4206.png)

![line3](media/line3.png)

2. **Main Code**

   Loop: the ultrasonic sensor reads the distance values and the serial monitor prints them. It determines whether the value is less than 10cm(this threshold can be modified).

   - Distance < 10, fan rotates.
   - Distance > = 10, fan stops.

![4207](media/4207.png)

![5bottom](media/5bottom.png)

#### Test Result

![4top](media/4top.png)

After uploading code, approach to the ultrasonic sensor. When the ultrasonic sensor detects things around itself with a distance less than 10, the fan will rotate. If the distance equals or is greater than 10, the fan will stop rotating.

![4203](media/4203.gif)

![4bottom](media/4bottom.png)

---

### 4.3 Remote Control Mode

In this project, we utilize an IR receiver and an 130 motor to construct a remote control fan, whose startup and rotation speed are controlled by a infrared remote control. 

#### Flow

 ![4301](media/4301.png)

#### Assembly

![line1](media/line1.png)

**Required Components**

![43_00](media/43_00.png)

![line1](media/line1.png)

**Step 1**

![43_01](media/43_01.png)

![line1](media/line1.png)

**Step 2**

![43_02](media/43_02.png)

![line1](media/line1.png)

**Step 3**

![43_03](media/43_03.png)

![line1](media/line1.png)

**Step 4**

![43_04](media/43_04.png)

![line1](media/line1.png)

**Step 5**

![43_05](media/43_05.png)

![line1](media/line1.png)

**Completed**

![43_06](media/43_06.png)

![line1](media/line1.png)

#### Wiring Diagram

![4302](media/4302.png)

#### Test Code

Open KidsBlock and connect the board to computer. Choose **File --> Load from your computer**.

![3111](media/3111.png)

Choose path D:\Code\1.Code_kidsuno and open **4.3Remote control.sb3**.

![4303](media/4303.png)

Click ![3209](media/3209.png)to connect to port and then ![2210](media/2210.png).

#### Explanations

![5top](media/5top.png)

**Code Blocks**

|              Blocks               |                    Code block                     |
| :-------------------------------: | :-----------------------------------------------: |
|    ![Events](media/Events.png)    |             ![begin](media/begin.png)             |
|      ![Vari](media/Vari.png)      |      ![variablename](media/variablename.png)      |
|      ![Vari](media/Vari.png)      |       ![setvariable](media/setvariable.png)       |
|      ![Vari](media/Vari.png)      |        ![variable++](media/variable++.png)        |
|      ![Vari](media/Vari.png)      |          ![variable](media/variable.png)          |
|        ![IR](media/IR.png)        |            ![IR_pin](media/IR_pin.png)            |
|        ![IR](media/IR.png)        |       ![IR_Received](media/IR_Received.png)       |
|        ![IR](media/IR.png)        |           ![IR_read](media/IR_read.png)           |
|        ![IR](media/IR.png)        |        ![IR_Refresh](media/IR_Refresh.png)        |
| ![Operators](media/Operators.png) |                 ![=](media/=.png)                 |
| ![Operators](media/Operators.png) |               ![mod](media/mod.png)               |
|     ![Motor](media/Motor.png)     | ![Motor_analogWrite](media/Motor_analogWrite.png) |
|   ![Control](media/Control.png)   |           ![forever](media/forever.png)           |
|   ![Control](media/Control.png)   |            ![ifelse](media/ifelse.png)            |
|   ![Control](media/Control.png)   |                ![if](media/if.png)                |

![line5](media/line5.png)

**Build blocks:**

Click ![add](media/add.png) to add libraries **DC Motor** and **ir remote**.

![4304](media/4304.png)

1. **Initialization**

   Define four variables with initial values of 0: *key1_press_num*; *key2_press_num*; *key3_press_num*; *key*.

   The first three variables are used to store the pressing times of key 1, key 2 and key 3; the last one records the data received by IR receiver.
   
   Zero out INA and INB, and initialize the IR receiver pin IO13.
   
   ![4305](media/4305.png)

![line3](media/line3.png)

2. **Main Code**

   Loop: Press key 1, key 2 and key 3, the fan will rotates at different speed. Press again, the fan stops. These three speeds can have a switchover without stopping the fan.

   ![4306](media/4306.png)
   
   <br>
   
   **Build blocks:**
   
   ① Build blocks as follows: 
   
   ![4307](media/4307.png)
   
   When an infrared signal is received, assign the received value to the variable *key* and then refresh the received value.
   
   ② Add blocks as follows: It determines whether the key 1 is pressed.
   
   ![4308](media/4308.png)
   
   If *key* = 16738455 (key 1 is pressed), *key1_press_num* will adds one, and *key2_press_num* and *key3_press_num* will zero out.
   
   ③ Add blocks as follows:
   
   ![4309](media/4309.png)
   
   These code blocks determine whether the remainder of *key1_press_num* divided by 2 equals 1.
   
   - remainder = 1: fan rotates.
   - remainder ≠ 1: fan stops. 
   
   ④ Put these blocks together: 
   
   ![4310](media/4310.png)
   
   For this whole, the fan will rotate at a high speed if key 1 is pressed; it stops when key 1 is pressed again. 
   
   **Analysis:**
   
   Press key 1 once, *key1_press_num*(initial value is 0) adds one, and *key2_press_num* and *key3_press_num* zero out.
   
   Determine whether the remainder of *key1_press_num* divided by 2 equals 1: herein, 1 ÷ 2 = 0......1, so the condition is met, and the fan rotates at high speed.
   
   Press key 1 again, *key1_press_num* adds one. Now it equals 2, and the other two values is 0.
   
   Determine whether the remainder of *key1_press_num* divided by 2 equals 1: herein,  2 ÷ 2 =1......0, so the condition is not satisfied, and the fan stops.
   
   ⑤ Duplicate the "if" block in ④ twice.
   
   ![4311](media/4311.png)
   
   As follows: 
   
   ![4312](media/4312.png)
   
   The working principles are the same. These two copies are used to control key 2 and key 3. For key 2, the fan will rotates at a medium speed; For key 3, it is at low speed.
   
   ⑥ Drag blocks of ⑤ into ①, as follows:
   
   ![4313](media/4313.png)
   
   When infrared signals are received, determine whether they are the decimal codes of key 1, key 2 and key 3.
   
   Then, determine the number of pressing time is odd or even. Odd: the fan rotates at corresponding speed; Even: fan stops.
   
   ![6top](media/6top.png)
   
   Q ：Why zero out the other two variables? 
   
   These three keys work according to the same principle. When the pressing times is an odd number, the fan rotates; otherwise, the fan stops. 
   
   If we do not zero out them, we cannot make sure every time these three speeds can have a switchover without stopping the fan. This is because we have no idea whether the value of the other two is always even, so the fan may change speed or stop when we press another key. We zero out  them when we press one key, therefore the fan can immediately change its speed without stopping when we press another key. 
   
   A :  This step ensures that, after we press one key, the values of the other two are always even, so that these three speeds can have a switchover without stopping the fan.
   
   ![6bottom](media/6bottom.png)


![5bottom](media/5bottom.png)

#### Test Result

![4top](media/4top.png)

After uploading code, we can control the startup and speed of the fan via the remote control.

Key 1: high speed

Key 2: medium speed

Key 3: low speed

These three speeds can have a switchover without stopping the fan. Press the same key again and the fan will stop.

![4303](media/4303.gif)

![4bottom](media/4bottom.png)

---

### 4.4 Manual Control Mode

In this project, we adopt a capacitive touch sensor and an 130 motor to combine a fan in manual mode. We can control the startup of the fan by the capacitive touch sensor.

#### Flow

![4401](media/4401.png)

#### Assembly

![line1](media/line1.png)

**Required Components**

![44_00](media/44_00.png)

![line1](media/line1.png)

**Step 1**

![44_01](media/44_01.png)

![line1](media/line1.png)

**Step 2**

![44_02](media/44_02.png)

![line1](media/line1.png)

**Step 3**

![44_03](media/44_03.png)

![line1](media/line1.png)

**Step 4**

![44_04](media/44_04.png)

![line1](media/line1.png)

**Step 5**

![44_05](media/44_05.png)

![line1](media/line1.png)

**Step 6**

![44_06](media/44_06.png)

![line1](media/line1.png)

**Completed**

![44_07](media/44_07.png)

![line1](media/line1.png)

#### Wiring Diagram

![4402](media/4402.png)

#### Test Code

Open KidsBlock and connect the board to computer. Choose **File --> Load from your computer**.

![3111](media/3111.png)

Choose path D:\Code\1.Code_kidsuno and open **4.4Manual mode.sb3**.

![4403](media/4403.png)

Click ![3209](media/3209.png) to connect to port and then ![2210](media/2210.png).

#### Explanations

![5top](media/5top.png)

**Code Blocks**

|              Blocks               |                    Code block                     |
| :-------------------------------: | :-----------------------------------------------: |
|    ![Events](media/Events.png)    |             ![begin](media/begin.png)             |
|         ![P](media/P.png)         |           ![setmode](media/setmode.png)           |
|         ![P](media/P.png)         |       ![readdigital](media/readdigital.png)       |
|      ![Vari](media/Vari.png)      |      ![variablename](media/variablename.png)      |
|      ![Vari](media/Vari.png)      |       ![setvariable](media/setvariable.png)       |
|      ![Vari](media/Vari.png)      |          ![variable](media/variable.png)          |
| ![Operators](media/Operators.png) |                 ![=](media/=.png)                 |
| ![Operators](media/Operators.png) |               ![and](media/and.png)               |
|     ![Motor](media/Motor.png)     | ![Motor_analogWrite](media/Motor_analogWrite.png) |
|   ![Control](media/Control.png)   |           ![forever](media/forever.png)           |
|   ![Control](media/Control.png)   |                ![if](media/if.png)                |
|   ![Control](media/Control.png)   |              ![wait](media/wait.png)              |

![line5](media/line5.png)

**Build blocks:**

Click ![add](media/add.png) to import library **DC Motor**.

![3907](media/3907.png)

1. **Initialization**

   Set the sensor pin to D2. Define a variable press with an initial value of 0 to monitor the state of motor.

   ![4404](media/4404.png)

![line3](media/line3.png)

2. **Main Code**

   Loop:

   - When the module is touched (D2 reads 1) and press = 0, the fan rotates, and press will be reassigned to 1.
   - When the module is touched (D2 reads 1) and press = 1, the fan stops, and press will be reassigned to 0.

   ![4405](media/4405.png)


![5bottom](media/5bottom.png)

#### Test Result

![4top](media/4top.png)

After uploading code, touch the module and the fan starts to work. Touch it again, and the fan will stop.

![4403](media/4403.gif)

![4bottom](media/4bottom.png)

---

### 4.5 Variable Speed Mode

In this experiment, we build a small fan with variable rotation speed: 40%, 60%, 80% and 100%. The required modules are a five-channel AD button module (speed control) and an 130 motor. 

#### Flow

![4501](media/4501.png)

#### Assembly

![line1](media/line1.png)

**Required Components**

![45_00](media/45_00.png)

![line1](media/line1.png)

**Step 1**

![45_01](media/45_01.png)

![line1](media/line1.png)

**Step 2**

![45_02](media/45_02.png)

![line1](media/line1.png)

**Step 3**

![45_03](media/45_03.png)

![line1](media/line1.png)

**Step 4**

![45_04](media/45_04.png)

![line1](media/line1.png)

**Step 5**

![45_05](media/45_05.png)

![line1](media/line1.png)

**Step 6**

![45_06](media/45_06.png)

![line1](media/line1.png)

**Completed**

![45_07](media/45_07.png)

![line1](media/line1.png)

#### Wiring Diagram

![4502](media/4502.png)

#### Test Code

Open KidsBlock and connect the board to computer. Choose **File --> Load from your computer**.

![3111](media/3111.png)

Choose path D:\Code\1.Code_kidsuno and open **4.5Gearshift mode.sb3**.

![4503](media/4503.png)

Click ![3209](media/3209.png) to connect to port and then ![2210](media/2210.png).

#### Explanations

![5top](media/5top.png)

**Code Blocks**

|              Blocks               |                    Code block                     |
| :-------------------------------: | :-----------------------------------------------: |
|    ![Events](media/Events.png)    |             ![begin](media/begin.png)             |
|         ![P](media/P.png)         |           ![setmode](media/setmode.png)           |
|         ![P](media/P.png)         |        ![readanalog](media/readanalog.png)        |
|    ![Serial](media/Serial.png)    |       ![serialbegin](media/serialbegin.png)       |
|    ![Serial](media/Serial.png)    |       ![serialprint](media/serialprint.png)       |
|      ![Vari](media/Vari.png)      |      ![variablename](media/variablename.png)      |
|      ![Vari](media/Vari.png)      |       ![setvariable](media/setvariable.png)       |
|      ![Vari](media/Vari.png)      |          ![variable](media/variable.png)          |
| ![Operators](media/Operators.png) |              ![less](media/less.png)              |
| ![Operators](media/Operators.png) |           ![greater](media/greater.png)           |
| ![Operators](media/Operators.png) |               ![and](media/and.png)               |
|     ![Motor](media/Motor.png)     | ![Motor_analogWrite](media/Motor_analogWrite.png) |
|      ![Data](media/Data.png)      |               ![map](media/map.png)               |
|   ![Control](media/Control.png)   |           ![forever](media/forever.png)           |
|   ![Control](media/Control.png)   |                ![if](media/if.png)                |
|   ![Control](media/Control.png)   |              ![wait](media/wait.png)              |

![line5](media/line5.png)

**Conceive:**

1. **Initialization**

   Set pin mode and initialize the serial port.

   ![4504](media/4504.png)

![line3](media/line3.png)

2. **Main Code**

   Loop:

   - Press button 5 to adjust the speed to 40%.
   - Press button 4 to adjust the speed to 60%.
   - Press button 3 to adjust the speed to 80%.
   - Press button 2 to adjust the speed to 100%.
   - Press button 1 to stop the fan.

   ![4505](media/4505.png)

**Build blocks:**

The code structure is similar to that in chapter 3.8. 

In addition, here we adopt a map block to configure the motor PWM.

![map](media/map.png)

![peg](media/peg.png)

![line3](media/line3.png)

![6top](media/6top.png)

Q ：What is MAP?

A ：In mathematics, MAP is the term for a relationship between two sets of elements that "correspond" to each other.

Set: a whole consisting of one or more defined elements.

There is a correspondence between Set A and B. For every Element a in Set A, there is always a unique element b corresponding to it in Set B, which is called map A to B.

The concept of mapping is not only used in mathematics, but in computer science. In a computer program, mapping is a way to map each element in one set to a unique element in another.

![6bottom](media/6bottom.png)

![line3](media/line3.png)

In chapter 3.9, we know that the rotation speed is effected by PWM duty cycle.

The range of PWM is 0 ~ 255. When PWM=255, the speed is at maximum. In this experiment, we set the speed range from 0 to 100, and map the speed values to PWM by the map block.

Divide PWM equally into 100 parts, so each part is 2.55, which corresponds to 1 speed.

- Maximum unit of PWM: 2.55
- Maximum unit of speed: 1

![4508](media/4507.png)

The speed value multiplied by 2.55 equals the corresponding PWM value: 

<font face="courier New" color="black" size=6>$ PWM{v}= \frac {255-0}{100-0}*V$</font> 

![map](media/map.png)

In a map block, five operators need to be set:

- The first is the value being mapped, here it is the speed value.
- The second and third are the range of the value being mapped, here is the speed range.
- The forth and fifth are the range of the mapping value, here is the range of motor PWM.



![4506](media/4506.png) returns the PWM value of speed of 40.

Put it into ![Motor_analogWrite](media/Motor_analogWrite.png) to set the mapped value to the duty cycle of the motor, so that the motor will rotate at the speed of 40%.

Similarly, we duplicate this block and set speed value (the first operator in map block) to 60, 80 and 100 to make the fan work at the speed of 60%, 80% and 100%.

This map block can directly set the range of mapped values and of mapping values, so we only need to modify the mapped values without calculating the corresponding mapping values one by one.

![5bottom](media/5bottom.png)

#### Test Result

![4top](media/4top.png)

After uploading code, press button 5 - 2 orderly, and the fan speed will be adjusted to 40, 60, 80,100 accordingly. When you press button 1, the fan turns off.

![4503](media/4503.gif)

![4bottom](media/4bottom.png)

---
