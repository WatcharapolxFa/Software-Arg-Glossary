# Architectural Patterns Styles
##  นาย วัชรพล โยธาดี

- Matplotlib
 
  Matplotlib เป็นหนึ่งในไลบรารีของไพทอนมีหน้าที่ใช้ในการพล็อตค่าต่างๆ ใช้ได้ทั้งในระบบ 2D และ 3D แต่ใน 3D มีบางฟังก์ชั่นที่ยังไม่รองรับ 
ด้วยในปัจจุบันคนส่วนใหญ่นิยมใช้ภาษาไพทอนจึงทำให้ Matplotlib ถูกนิยมตามไปด้วยเนื่องจากสามารถคำนวนทางวิทยาศาสตร์เป้าหมายของ Matplotlib
คือทำให้สามารถใช้งานได้หลากหลายมีกราฟฟิคใช้สำหรับติดต่อกับผู้ใช้งานโดยระบบปฏิบัติการเดสก์ท็อปหลักทั้งหมดโดยใช้ GTK+, Qt, Tk, FLTK, wxWidgets และ Cocoa ซึ่งสามารถเรียก แบบโต้ตอบจาก interactive Python shell เพื่อสร้างกราฟิกด้วยคําสั่งขั้นตอนง่าย ๆ เช่น Mathematica, IDL หรือ MATLAB matplotlib และยังสามารถฝังตัวใน headless webserver เพื่อจัดเตรียมเอกสารทั้งในรูปแบบ raster-based เช่น Portable Network Graphics (PNG) และรูปแบบเวกเตอร์ เช่น PostScript, Portable Document Format (PDF) และ Scalable Vector Graphics (SVG)

วัตถุประสงค์
    - เพื่อให้สามารถสร้างพล็อตที่มีคุณภาพที่มีความง่ายและความสะดวกมากยิ่งขึ้น 
    - เพื่อแสดงภาพแบบคงที่และแบบเคลื่อนไหวด้วยภาษา Pyton

Architectural Patterns Styles
    รูปแบบสถาปัตยกรรมที่ Matplotlib ใช้คือ Layer architectural มีทั้งหมด 3 Layer
![image](https://user-images.githubusercontent.com/69455513/190139327-54c6cfea-397f-44c1-a9a6-19da01d1a72f.png)

    
