# Arithmetic-operation-using-8086
# 8086 Assembly Language Programs for Arithmetic Operations

## AIM

To write and execute Assembly Language Programs to perform arithmetic operations for the 8086 microprocessor.

---

## APPARATUS REQUIRED

* Personal Computer with MASM Software

---

## 1. ADDITION

#### Algorithm

1. Initialize memory location in HL register.
2. Store 1st data.
3. Increment HL to enter 2nd data.
4. Move 2nd number to accumulator.
5. Decrement HL.
6. Add value in memory with accumulator.
7. Store result.
8. Stop.


## FLOW CHART
<img width="707" height="1024" alt="image" src="https://github.com/user-attachments/assets/b5a7062d-e294-47cd-9683-a40de25e82de" />


#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV CL,00H
MOV AX,[SI]
MOV BX,[SI+02H]
ADD AX,BX
JNC L1
INC CL
L1:
MOV [SI+04H],AX
MOV [SI+06H],CL
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|     1200 : 12           |      1204 : 24           |
1201 : 34  |  1205 : 68
1202 : 12   | 1206 : 00
1203 : 34    |1207 : C4


#### Manual Calculations

![IMG-20250907-WA0016](https://github.com/user-attachments/assets/4189b2e5-c702-45ba-9d38-767742f07d29)


---

## OUTPUT IMAGE FROM MASM SOFTWARE

<img width="639" height="426" alt="Screenshot 2025-09-07 152251" src="https://github.com/user-attachments/assets/15a10d11-21ec-40b9-9fad-2d0dd6e4b6f8" />
<img width="633" height="430" alt="Screenshot 2025-09-07 152208" src="https://github.com/user-attachments/assets/fc1e9efd-5534-465c-8584-b6812e4ec70e" />

## 2. SUBTRACTION

#### Algorithm

1. Initialize memory and store 1st data.
2. Increment to get 2nd data.
3. Move 2nd data to accumulator.
4. Subtract memory content.
5. Store result.

## FLOWCHART

<img width="578" height="797" alt="image" src="https://github.com/user-attachments/assets/564c3c7a-33ce-4a1c-8920-beb5c24b9b47" />


#### Program
```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV CL,00H
MOV AX,[SI]
MOV BX,[SI+02H]
SUB AX,BX
JNC L1
INC CL
L1:
MOV [SI+04H],AX
MOV [SI+06H],CL
MOV AH,4CH
INT 21H
CODE ENDS
END
```


#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|               1200 : 12          |      1204 : 00                    |
1201 : 34 | 1205 : 00
1202 : 12 | 1206 : 00
1203 : 34 | 1207 : C4
#### Manual Calculations
![IMG-20250907-WA0015](https://github.com/user-attachments/assets/868819e7-5d2d-4997-9ab6-f0a5f23bbfd9)


---


## OUTPUT SCREEN FROM MASM SOFTWARE
<img width="634" height="425" alt="Screenshot 2025-09-07 154021" src="https://github.com/user-attachments/assets/5700e0b1-cdaa-436b-a5b0-14b109af39fa" />
<img width="632" height="423" alt="Screenshot 2025-09-07 154617" src="https://github.com/user-attachments/assets/283c7d80-1563-4c9c-8f3c-e2237580360a" />

## 3. MULTIPLICATION

#### Algorithm

1. Initialize memory and store operands.
2. Move operands to registers.
3. Multiply.
4. Store result.

##FLOWCHART

<img width="569" height="906" alt="image" src="https://github.com/user-attachments/assets/88be88ff-2896-4a88-b73d-84ccffd2fcf9" />



#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV DX,0000H
MOV AX,[SI]
MOV BX,[SI+02H]
MUL BX
MOV [SI+04H],AX
MOV [SI+06H],DX
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|         1200 : 12                |       1204 : 44                   |
1201 : 34 | 1205 : 51
1202 : 12 | 1206 : 97
1203 : 34 | 1207 : 0A

#### Manual Calculations

![IMG-20250907-WA0018](https://github.com/user-attachments/assets/b7e70960-708f-415d-b218-098c0b724f54)

---

## OUTPUT SCREEN FROM MASM SOFTWARE
<img width="641" height="429" alt="Screenshot 2025-09-07 152352" src="https://github.com/user-attachments/assets/88e5c93f-2ed5-47f1-b974-f1e89910317c" />
<img width="644" height="404" alt="Screenshot 2025-08-20 161235" src="https://github.com/user-attachments/assets/3652838e-30ce-43c0-96a6-cd99db3c2edc" />

## 4. DIVISION

#### Algorithm

1. Load memory location of operands.
2. Perform division.
3. Store result.

   ## FLOWCHART
<img width="1065" height="802" alt="image" src="https://github.com/user-attachments/assets/25b4a483-0d42-494b-8639-1af3ea17191b" />


#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV DX,0000H
MOV AX,[SI]
MOV BX,[SI+02H]
DIV BX
MOV [SI+04H],AX
MOV [SI+06H],DX
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | MEMORY LOCATION (OUTPUT) |
| ----------------------- | ------------------------ |
|       1200 : 12                  |              1204 : 01            |
1201 : 34 | 1205 : 00
1202 : 12 | 1206 : 00
1203 : 34 | 1207 : 00
#### Manual Calculations

![IMG-20250907-WA0017](https://github.com/user-attachments/assets/886fcaf2-6652-45e4-95de-d1542eecb9b3)

---

## OUTPUT FROM MASM SOFTWARE
<img width="630" height="428" alt="Screenshot 2025-09-07 153433" src="https://github.com/user-attachments/assets/f24908e5-9500-429c-b7da-9a63b60a44d0" />
<img width="642" height="426" alt="Screenshot 2025-09-07 153341" src="https://github.com/user-attachments/assets/6bbfe2be-50d5-406d-a8e3-ada7cc5de459" />


## RESULT

Thus, the Assembly Language Programs for 8086 to perform arithmetic operations (Addition, Subtraction, Multiplication, and Division) using both direct and indirect methods were successfully written and executed using MASM.
