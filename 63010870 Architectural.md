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
- Audacity
  Audacity เป็นโปรแกรม OpenSource ที่ใช้ตัดต่อและบันทึกเสียงด้วยการใช้ Effect ต่างๆ ซึ่งมีอยู่มากมายและครบครันเช่น Noise Reduction
(ลดเสียง) Amplify(เพิ่มเสียง) ปรับระดับของเดซิเบล ฯลฯ ถึงแม้ว่า Audacity จะเป็นโปรแกรมที่มีเครื่องมือในการใช้งานเป็นจำนวนมาก 
แต่ก็เป็นโปรแกรมที่สามารถใช้ง่าย เพราะโปรแกรมนี้ได้แปลเป็นหลายๆภาษาทั่ว Audacity สามารถดาวน์โหลดฟรีได้ในทุกๆแพลตฟอร์ม ไม่ว่าจะเป็น Windows, Macs, Ubuntu
```
วัตถุประสงค์

- อย่างแรกคือ การอัดเสียง เพียงแค่เชื่อมต่อกับไมโครโฟน แล้วกดอัดเมนู Record New Track (ปุ่มสีแดง) โปรแกรมก็จะเริ่มบันทึกเสียงและแสดงข้อมูลว่าอัดไปแล้วกี่นาที ซึ่งฟีเจอร์นี้ใช้ไม่ยากเลย ถ้าหากต้องการจะตัดต่อเสียงก็ไม่ต้องไปหาโปรแกรมอื่นในการช่วยตัดเลย เพราะเราสามารถตัดต่อได้ผ่านโปรแกรมได้เลย

- การเพิ่มเสียง และลดเสียง โปรแกรมสามารถทำได้เช่นกัน ในการเพิ่มเสียง คลุมส่วนที่จะเพิ่มเสียงและลดเสียง ถ้าหากต้องการเพิ่มเสียง ให้กดไปที่Effect จากนั้นก็เลือกที่ Amplify แล้วปรับความดังว่าจะให้ดังเท่าไร ซึ่งเราสามารถเพิ่มหรือลดได้ตามใจชอบเลย

- การปรับเสียงให้เท่ากัน สำหรับไฟล์เสียงที่มีความสม่ำเสมอไม่เท่ากัน อาจจะทำให้เสียงฟังดูไม่ Smooth ซึ่งเราสามารถปรับให้เสียงเท่ากันทั้งคลิปได้ โดยกดไปที่ Effect แล้วเลือกไปที่ Normalize ระบบก็จะแปลงไฟล์เสียงให้มีความดังเท่ากันทั้งคลิป
```
Architectural Patterns Styles

  Layer ที่ติดต่อกับผู้ใช้งาน(GUI) คือ Lib wxWidgets ส่วน GUI ถูกแบ่งออกมาหลายๆส่วน เช่น Blockfiles, ShuttleGUI โดยในส่วนนี้ทำหน้าที่รับคำสั่งและแสดงผลต่อผู้ใช่งาน
  Layer ส่วนที่ติดต่อกับ Hardware ใช้ Lib PortAudioโดยในส่วนนี้ทำหน้าที่ติดต่อกับระบบปฏิบัติการ(OS)เพื่อใช้งาน(Interface)ต่างๆของHardwawre
    ![image](https://user-images.githubusercontent.com/69455513/190145210-e7360fdc-76dd-453e-b1c8-72120e890454.png)

```
Quality Attribute Scenarios 
    - Usability
Source:            User
Stimulus:          Learn to use
Environment:       Run Time
Response:          Help facilitate
Response Measure:  Satisfaction
```
```
    - Integrability
Source:            User
Stimulus:          Want to add a plugin to Audacity?
Environment:       Deployment, Deployment, Runtime, Integration)
Response:          New Configuration
Response Measure:  There is a new plugin.
```
```
Quality Attribute Scenarios 
    - Performance
Source:            Hacker
Stimulus:          Insecure libraries
Environment:       Plugin Online
Response:          Data, Resource
Response Measure:  Intrustion detection devices
```
- Jitsi
  Jitsi เป็นแอปพลิเคชั่นที่ช่วยให้ผู้คนสามารถโทรผ่านวิดีโอและสนทนา แชร์เดสก์ท็อป และแลกเปลี่ยน ไฟล์และข้อความ ที่สําคัญกว่านั้นคืออนุญาตให้ผู้คนทําสิ่งนี้ผ่านโปรโตคอลต่างๆ ตั้งแต่ XMPP มาตรฐาน (Extensible Messaging and Presence Protocol) และ SIP (Session Initiation Protocol) ไปจนถึงกรรมสิทธิ์ เช่นYahoo!และWindowsLiveMessenger(MSN) ซึ่งJitsiสามารถทํางานบน Windows,Mac OS, Linux และ FreeBSD ส่วนใหญ่เขียนด้วยภาษา Java แต่ก็มีส่วนที่เขียนด้วย native code
  
```
วัตถุประสงค์

- เพื่อ Video Conference , Text Chat , Sip call ได้

- สนทนาได้หลายคนและสามารถบันทึกภาพและเสียงในการสนทนาได้

```
Attribute Scenarios 

 รูปแบบสถาปัตยกรรมที่ Jitsi ใช้คือรูปแบบ Layer architectural
 
- แอปพลิเคชัน JavaScript ที่เข้ากันได้กับ Jitsi Meet WebRTC ซึ่งใช้ Jitsi Videobridge เพื่อจัดการประชุมทางวิดีโอคุณภาพสูงและปรับขนาดได้ สร้างจาก React และ React Native

- Jitsi Videobridge (jvb) เซิร์ฟเวอร์ที่เข้ากันได้กับ WebRTC ออกแบบมาเพื่อกำหนดเส้นทางสตรีมวิดีโอระหว่างผู้เข้าร่วมในการประชุม

- คอมโพเนนต์โฟกัสฝั่งเซิร์ฟเวอร์ Jitsi Conference Focus (jicofo) ที่ใช้ในการประชุม Jitsi Meet ที่จัดการเซสชันสื่อระหว่างผู้เข้าร่วมแต่ละคนและสะพานวิดีโอ

- Jitsi Gateway to SIP (jigasi) แอปพลิเคชันฝั่งเซิร์ฟเวอร์ที่อนุญาตให้ไคลเอ็นต์ SIP ปกติเข้าร่วมการประชุม Jitsi Meet

- เครื่องมือ Jitsi Broadcasting Infrastructure (jibri) สำหรับบันทึกและ/หรือสตรีมการประชุม Jitsi Meet ที่ทำงานโดยเปิดใช้อินสแตนซ์ Chrome ที่แสดงผลในเฟรมบัฟเฟอร์เสมือน และบันทึกและเข้ารหัสเอาต์พุตด้วย ffmpeg
![image](https://user-images.githubusercontent.com/69455513/190150300-cdba8c7a-401a-411d-881e-f8393b437085.png)

```
Quality Attribute Scenarios 
    - Usability
Source:            User
Stimulus:          User system efficiently
Artifact:          System
Environment:       Runtime
Response:          Wishes to record audio and video
Response Measure:  Video and audio recording takes less than a second
```
```
    - Modifiability
Source:            Developer
Stimulus:          Wishes to add screen sharing function
Artifact:          Code
Environment:       Development time 
Response:          Modifications were made without side effects
Response Measure:  In Six hours
```
```
    - Performance
Source:            IOS
Stimulus:          Wishes to run on ios
Artifact:          Resource
Environment:       Runtime
Response:          Can run on IOS without error occurs
Response Measure:  In 30 minutes
```
