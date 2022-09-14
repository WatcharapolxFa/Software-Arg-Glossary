# Architectural Patterns Styles
##  นาย วัชรพล โยธาดี

- Matplotlib
 
  Matplotlib เป็นหนึ่งในไลบรารีของไพทอนมีหน้าที่ใช้ในการพล็อตค่าต่างๆ ใช้ได้ทั้งในระบบ 2D และ 3D แต่ใน 3D มีบางฟังก์ชั่นที่ยังไม่รองรับ 
ด้วยในปัจจุบันคนส่วนใหญ่นิยมใช้ภาษาไพทอนจึงทำให้ Matplotlib ถูกนิยมตามไปด้วยเนื่องจากสามารถคำนวนทางวิทยาศาสตร์เป้าหมายของ Matplotlib
คือทำให้สามารถใช้งานได้หลากหลายมีกราฟฟิคใช้สำหรับติดต่อกับผู้ใช้งานโดยระบบปฏิบัติการเดสก์ท็อปหลักทั้งหมดโดยใช้ GTK+, Qt, Tk, FLTK, wxWidgets และ Cocoa ซึ่งสามารถเรียก แบบโต้ตอบจาก interactive Python shell เพื่อสร้างกราฟิกด้วยคําสั่งขั้นตอนง่าย ๆ เช่น Mathematica, IDL หรือ MATLAB matplotlib และยังสามารถฝังตัวใน headless webserver เพื่อจัดเตรียมเอกสารทั้งในรูปแบบ raster-based เช่น Portable Network Graphics (PNG) และรูปแบบเวกเตอร์ เช่น PostScript, Portable Document Format (PDF) และ Scalable Vector Graphics (SVG)

วัตถุประสงค์

    - เพื่อให้สามารถสร้างพล็อตที่มีคุณภาพที่มีความง่ายและความสะดวกมากยิ่งขึ้น 
    - เพื่อแสดงภาพแบบคงที่และแบบเคลื่อนไหวด้วยภาษา Python

Architectural Patterns Styles
    รูปแบบสถาปัตยกรรมที่ Matplotlib ใช้คือ Layer architectural มีทั้งหมด 3 Layer
    
 
![image](https://user-images.githubusercontent.com/69455513/190139327-54c6cfea-397f-44c1-a9a6-19da01d1a72f.png)


```
- Scripting Layer 
เป็น Layer ชั้นบนสุดที่ออกแบบมาเพื่อให้ Matplotlib ทํางานเหมือนสคริปต์ MATLAB เป็นชุดของฟังก์ชันรูปแบบคําสั่ง ดังนั้นจึงถือว่าเป็นเลเยอร์ที่ใช้งานง่ายที่สุด
```
```
- Artist Layer 
เป็น Layer ที่ช่วยให้สามารถควบคุมและปรับแต่งองค์ประกอบต่างๆได้มากที่สุด Layer  นี้ประกอบด้วยวัตถุหลักหนึ่งชิ้นคือ Artist ที่ช่วยให้คุณปรับแต่งได้มากขึ้นเมื่อเทียบกับ Scripting Layer และ สะดวกกว่าสําหรับพล็อตขั้นสูง
```
```
- Backend Layer
เป็น Layer ที่จัดการงานทั้งหมดผ่านการสื่อสารกับชุดเครื่องมือ เช่น wxPython หรือ PostScript และ Layer นี้เป็นชั้นที่ซับซ้อนที่สุดของ Matplotlib
```
```
Quality Attribute Scenarios 
    - Modifiability
Source:            Developer
Stimulus:          Wishes to modify 3D function
Artifact:          Code
Environment:       Development Time
Response:          Modification is made with no side effects
Response measure:  In Three hours
```
```
    - Portability
Source:            OS
Stimulus:          Wishes to run on another OS
Artifact:          Resource
Environment:       Runtime
Response:          Can run without error occurs
Response measure:  In 30 minutes
```
```
    - Testability
Source:            Tester
Stimulus:          Prefoms end to end test
Artifact:          Complete application
Environment:       At deployment time
Response:          Perform a test sequence
Response measure:  Path coverage of 85% is achieved within three hours
```
