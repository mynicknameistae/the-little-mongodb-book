# เกี่ยวกับหนังสือเล่มนี้ #

## License ##
The Little MongoDB Book book is licensed under the Attribution-NonCommercial 3.0 Unported license. **You should not have paid for this book.**

You are basically free to copy, distribute, modify or display the book. However, I ask that you always attribute the book to me, Karl Seguin and do not use it for commercial purposes.

You can see the full text of the license at:

<http://creativecommons.org/licenses/by-nc/3.0/legalcode>

## เกี่ยวกับผู้เขียน ##
Karl Seguin is a developer with experience across various fields and technologies. He's an expert .NET and Ruby developer.  He's a semi-active contributor to OSS projects, a technical writer and an occasional speaker. With respect to MongoDB, he was a core contributor to the C# MongoDB library NoRM, wrote the interactive tutorial [mongly](http://openmymind.net/mongly/) as well as the [Mongo Web Admin](https://github.com/karlseguin/Mongo-Web-Admin). His free service for casual game developers, [mogade.com](http://mogade.com/), is powered by MongoDB.

Karl has since written [The Little Redis Book](http://openmymind.net/2012/1/23/The-Little-Redis-Book/)

His blog can be found at <http://openmymind.net>, and he tweets via [@karlseguin](http://twitter.com/karlseguin)

## With Thanks To ##
A special thanks to [Perry Neal](http://twitter.com/perryneal) for lending me his eyes, mind and passion. You provided me with invaluable help. Thank you.

## Latest Version ##
This version was updated for MongoDB 2.6 by Asya Kamsky.  The latest source of this book is available at:

<http://github.com/karlseguin/the-little-mongodb-book>.

# บทนำ #
 > นี่ไม่ใช่ความผิดของผู้เขียนที่แต่ละบทนั้นแสนสั้น แต่การเรียนรู้ MongoDB นั้นง่ายจริง ๆ

มักมีคำกล่าวว่าเทคโนโลยีนั้นก้าวหน้าไปอย่างรวดเร็ว จริงอยู่ที่เทคโนโลยีและเทคนิคใหม่ต่าง ๆ ถูกเผยแพร่ออกมามากขึ้นเรื่อย ๆ อย่างไรก็ตาม โดยส่วนตัวแล้ว ผู้เขียนมองว่าความก้าวหน้าของเทคโนโลยีพื้นฐานที่ถูกใช้โดยโปรแกรมเมอร์นั้นกลับก้าวหน้าไปอย่างค่อนข้างเชื่องช้า โปรแกรมเมอร์คนหนึ่งอาจใช้เวลานานนับปีเพื่อเรียนรู้ทีละนิดแต่ความรู้นั้นยังคงเป็นปัจจุบัน แต่สิ่งที่น่าตกใจคือการที่เทคโนโลยีที่ดูมั่นคงกลับถูกแทนที่อย่างรวดเร็วราวกับใช้เวลาเพียงชั่วข้ามคืน เทคโนโลยีต่าง ๆ ที่มีรากฐานมายาวนานจึงพบว่าตนเองได้รับผลกระทบจากการเปลี่ยนแปลงแนวคิดของนักพัฒนา

คงไม่มีอะไรที่จะแสดงถึงการเปลี่ยนแปลงแนวคิดเช่นนี้ได้ดีกว่าความก้าวหน้าของเทคโนโลยี NoSQL ที่มีผลกระทบต่อฐานข้อมูลเชิงสัมพันธ์ที่มีรากฐานที่เข็มแข็ง ซึ่งราวกับว่าในวันหนึ่ง เว็บต่าง ๆ ถูกขับเคลื่อนโดย RDBMS เพียงไม่กี่โปรแกรม แต่ในวันต่อมา กลับมีระบบแบบ NoSQL ราวห้าชนิดที่สร้างตัวขึ้นมาเป็นทางเลือกที่คู่ควรต่อการพัฒนาเว็บ

แม้ว่าการเปลี่ยนแปลงนี้ดูราวจะเกิดขึ้นในชั่วข้ามคืน แต่ในความเป็นจริง การยอมรับจนกลายเป็นแนวทางปฏิบัติอาจต้องใช้เวลานานนับปี ความกระตือรือร้นในช่วงแรกนั้นถูกขับเคลื่อนโดยนักพัฒนาและบริษัทในกลุ่มเล็ก ๆ เท่านั้น หลังจากที่แนวทางนั้น ๆ ถูกกลั่นกรองและปรับปรุงจากบทเรียนที่ได้รับจนพบว่านี่คือเทคโนโลยีใหม่ที่พร้อมจะก้าวต่อไป นักพัฒนารายอื่นก็จะเริ่มนำไปใช้อย่างช้า ๆ นี่คือความจริงที่เกิดขึ้นในกรณีของ NoSQL หลายชนิดที่ไม่ได้เกิดขึ้นเพื่อแทนที่แนวทางจัดเก็บข้อมูลแบบดั้งเดิม แต่เป็นการแก้ปัญหาตามความต้องการอันเฉพาะเจาะจงที่เพิ่มขึ้นมาจากสิ่งที่มีให้ในระบบแบบดั้งเดิม

จากที่ได้กล่าวมาแล้วทั้งหมดนี้ เราจะมาเริ่มอธิบายถึงความหมายของ NoSQL กันเป็นอันดับแรก ซึ่งคำนี้เป็นคำที่มีความหมายกว้าง ๆ แตกต่างกันไปสำหรับบุคคลแต่ละกลุ่ม โดยส่วนตัวแล้ว ผู้เขียนใช้คำนี้เพื่อสื่อถึงระบบที่ทำหน้าที่เป็นส่วนหนึ่งในการจัดเก็บข้อมูล หรืออีกนัยหนึ่ง (ย้ำอีกครั้ง ในมุมมองของผู้เขียน) NoSQL คือความเชื่อว่าชั้นที่ทำหน้าที่เก็บรักษาข้อมูล (persistence layer) นั้น ไม่ได้เป็นหน้าที่ของระบบใดระบบหนึ่งเพียงอย่างเดียว ขณะที่ผู้ผลิตและจำหน่ายฐานข้อมูลเชิงสัมพันธ์ได้พยายามวางตำแหน่งซอฟต์แวร์ของตนในฐานะระบบเดียวใช้ได้ทั้งหมด (one-size-fits-all) มาโดยตลอด แต่ NoSQL จะเอนเอียงไปทางการใช้หน่วยย่อย ๆ ที่มีขนาดเล็กกว่า ในฐานะเครื่องมือที่รับผิดชอบต่องานที่กำหนด ดังนั้น ชั้นของระบบ NoSQL ของคุณอาจยังคงใช้ฐานข้อมูลเชิงสัมพันธ์เช่น MySQL แต่ใช้ Redis เป็นส่วนหนึ่งในการค้นหาข้อมูลค้าง (persistence lookup) สำหรับส่วนที่กำหนดในระบบ ตลอดจนใช้ Hadoop สำหรับการประมวลผลข้อมูลอย่างเข้มข้น กล่าวง่าย ๆ คือ NoSQL นั้นคือการเปิดกว้างและรับรู้ถึงทางเลือกอื่น ๆ ถึงแบบแผนและเครื่องมือที่สามารถนำมาใช้เพื่อจัดการข้อมูลของคุณได้

คุณอาจกำลังสงสัยว่าแล้ว MongoDB อยู่ตรงไหนจากที่กล่าวมาท้้งหมดนี้ ในฐานะของฐานข้อมูลที่มีพื้นฐานจากเอกสาร (document-oriented) แล้ว MongoDB เป็นระบบ NoSQL ที่ถูกทำให้ใช้ได้อย่างกว้างขวาง ซึ่งสามารถมองได้ว่าเป็นทางเลือกหนึ่งจากการใช้ฐานข้อมูลเชิงสัมพันธ์ได้ แต่ MongoDB ก็สามารถได้ประโยชน์จากการนำไปใช้ร่วมกับระบบแบบ NoSQL ที่มีวัตถุประสงค์โดยเฉพาะอื่น ๆ ด้วยเช่นกัน นอกจากนี้ MongoDB ยังมีทั้งจุดเด่นและจุดด้อย ซึ่งเราจะได้กล่าวถึงกันในช่วงท้ายของหนังสือเล่มนี้

# เริ่มการใช้งาน #
เนื้อหาส่วนใหญ่ในหนังสือเล่มนี้จะเน้นไปที่ความสามารถหลัก ๆ ของ MongoDB ดังนั้นเราจะใช้เชลล์ของ MongoDB เป็นหลัก แม้ว่าเชลล์จะเป็นประโยชน์อย่างยิ่งต่อการเรียนรู้และเป็นเครื่องมือบริหารจัดการระบบที่ดี แต่ในการเขียนโค้ดนั้น เราจะใช้ไดรฟ์เวอร์ตัวใดตัวหนึ่งของ MongoDB

ไดรฟ์เวอร์: จึงเป็นสิ่งแรกที่เราควรรู้จักเกี่ยวกับ MongoDB ขณะนี้ MongoDB มี[ไดรฟ์เวอร์ที่เป็นทางการ](http://docs.mongodb.org/ecosystem/drivers/)สำหรับหลากหลายภาษา ซึ่งสามารถคิดได้ว่าไดรฟ์เวอร์เหล่านี้ก็คือไดรฟ์เวอร์ฐานข้อมูลชนิดต่าง ๆ ที่ผู้อ่านคงคุ้นเคยอยู่แล้ว นอกจากไดรฟ์เวอร์เหล่านี้แล้ว ชุมชนนักพัฒนาโปรแกรมยังได้สร้างไลบรารีที่เฉพาะเจาะจงกับภาษาหรือเฟรมเวิร์กอีกด้วย ตัวอย่างเช่น [NoRM](https://github.com/atheken/NoRM) ซึ่งเป็นไลบรารีภาษา C# ที่ทำงานแบบ LINQ และ [MongoMapper](https://github.com/jnunemaker/mongomapper) ไลบรารี Ruby ที่ทำงานได้ดีกับแอคทีฟเรคคอร์ด (ActiveRecord) ผู้อ่านจะเลือกเขียนโปรแกรมโดยตรงผ่านไดรฟ์เวอร์หลักของ MongoDB หรือจะใช้ไลบรารีในชั้นที่สูงกว่าก็ได้ ผู้เขียนต้องการกล่าวถึงประเด็นนี้เนื่องจากผู้ใช้ MongoDB รายใหม่ ๆ หลายคนเกิดความสับสนว่าทำไมถึงมีทั้งไดรฟ์เวอร์ในแบบที่เป็นทางการและไลบรารีจากชุมชนนักพัฒนา - โดยทั่วไปแล้วแบบแรกนั้นจะมุ่งไปที่การเชื่อมต่อหรือการสื่อสารกับ MongoDB เป็นหลัก ขณะที่แบบหลังเป็นการจัดเตรียมการทำงานร่วมกับภาษาหรือเฟรมเวิร์กใดโดยเฉพาะ

ผู้เขียนขอแนะนำให้ทดลองเล่นกับ MongoDB และทำตามตัวอย่างที่นำเสนอไปพร้อม ๆ กันกับการอ่านหนังสือเล่มนี้ รวมถึงทดลองกับโจทย์ที่ผู้อ่านอาจเกิดความสงสัยและคิดขึ้นมาเอง การจัดเตรียมและเริ่มใช้งาน MongoDB นั้นทำได้ง่ายเพียงไม่กี่นาทีเท่านั้น ดังนั้น เรามาเริ่มติดตั้งและเตรียมใช้งานกันได้เลย

1. ไปที่[หน้าดาวน์โหลดอย่างเป็นทางการ](http://www.mongodb.org/downloads) และโหลดโปรแกรมจากแถวบนสุด (เวอร์ชันเสถียรที่แนะนำให้ใช้) สำหรับระบบปฏิบัติการที่ผู้อ่านต้องการนำไปใช้ โดยในขั้นตอนทดลองพัฒนานี้จะเลือกใชุ้ร่น 32 บิต หรือ 64 บิตก็ได้

2. คลายไฟล์บีบอัด (ไว้ที่ใดก็ได้ตามต้องการ) และไปที่โฟลเดอร์ย่อย `bin` อย่าเพิ่งรันโปรแกรมใด ๆ ตอนนี้ แต่โปรดทราบว่า `mongod` คือตัวเซอร์ฟเวอร์ และ `mongo` คือเชลล์สำหรับไคลเอนต์ - เราจะใช้เวลาส่วนใหญ่กับโปรแกรมทั้งสองนี้

3. สร้่างไฟล์ข้อความ (text file) ขึ้นมาใหม่ในโฟลเดอร์ย่อย `bin` และตั้งชื่อว่า `mongodb.config`

4. เพิ่มบรรทัดเข้าไปในไฟล์ mongodb.config: `dbpath=เส้นทางไปยังที่จัดเก็บไฟล์ฐานข้อมูลตามต้องการ` ตัวอย่างเช่นบนวินโดวส์อาจใช้ `dbpath=c:\mongodb\data` ขณะที่บนลินุกซ์อาจกลายเป็น `dbpath=/var/lib/mongodb/data`

5. ตรวจสอบให้แน่ใจว่าเส้นทาง `dbpath` ที่ระบุได้ถูกสร้างไว้แล้ว

6. เรียกใช้ mongod ด้วยพารามิเตอร์ `--config /path/to/your/mongodb.config`

ตัวอย่างสำหรับผู้ใช้วินโดวส์คือหากคลายไฟล์ที่ดาวน์โหลดมาไว้ที่ `c:\mongodb\` และได้สร้างโฟลเดอร์ `c:\mongodb\data\` ไว้ ดังนั้น ในไฟล์ `c:\mongodb\bin\mongodb.config` ก็ต้องระบุว่า `dbpath=c:\mongodb\data\` จากนั้นจึงเรียกใช้ `mongod` จากบรรทัดคำสั่งดังนี้ `c:\mongodb\bin\mongod --config c:\mongodb\bin\mongodb.config`

ผู้อ่านอาจเพิ่มโฟลเดอร์ `bin` เข้าไปยังเส้นทาง (path) ของระบบเพื่อให้ไม่ต้องพิมพ์เส้นทางแบบเต็มเช่นนี้ก็ได้ สำหรับผู้ใช้แมคโอเอสและลินุกซ์ก็สามารถทำตามขั้นตอนนี้ได้เช่นกัน โดยเปลี่ยนเพียงเส้นทางต่าง ๆ เท่านั้น

ถึงตอนนี้ MongoDB น่าจะพร้อมใช้งานแล้ว หากเกิดความผิดพลาดใด ๆ โปรดอ่านข้อความที่ถูกแสดงผลออกมาโดยละเอียด - เซอร์ฟเวอร์นั้นสามารถให้ข้อมูลเกี่ยวกับข้อผิดพลาดที่เกิดขึ้นได้เป็นอย่างดี

ผู้อ่านสามารถเรียกใช้ `mongo` (ที่ไม่มี *d*) ซึ่งจะเชื่อมต่อเชลล์ไปยังเซอร์ฟเวอร์ที่ทำงานอยู่ ลองป้อนคำสั่ง `db.version()` เพื่อให้แน่ใจว่าทุกอย่างทำงานได้อย่างที่ควรจะเป็น สิ่งที่แสดงผลออกมาควรเป็นเลขเวอร์ชันของโปรแกรมที่ถูกติดตั้งไว้

# บทที่ 1 - หลักการพื้นฐาน #
เรามาเริ่มการเดินทางของเราด้วยการทำความรู้จักกลไกพื้นฐานในการทำงานกับ MongoDB กันก่อน แน่นอนว่านี่คือแกนหลักสำคัญในการทำความเข้าใจ MongoDB และยังเป็นสิ่งที่จะช่วยให้เราสามารถตอบคำถามในระดับที่สูงขึ้นเกี่ยวกับความเหมาะสมในการใช้ MongoDB ได้อีกด้วย

มีหลักการพื้นฐานหกประการที่ควรทำความเข้าใจก่อนเริ่มใช้งานดังนี้

1. MongoDB ใช้หลักการของ `ฐานข้อมูล (database)` ที่เราน่าจะคุ้นเคยกันดีอยู่แล้ว (หรือสคีมาสำหรับสายออราเคิล) ในระบบ MongoDB หนึ่ง ๆ สามารถมีฐานข้อมูลได้ตั้งแต่จำนวนศูนย์ฐานข้อมูลหรือมากกว่า แต่ละฐานข้อมูลทำหน้าที่เป็นที่จัดเก็บ (container) องค์ประกอบต่าง ๆ ทั้งหมดที่อยู่ภายใน 

2. ฐานข้อมูลหนึ่งสามารถมี `คอลเลกชัน (collection)` จำนวนศูนย์คอลเลกชันหรือมากกว่า ในคอลเลกชันหนึ่ง ๆ มีคุณสมบัติคล้ายกันกับ `ตาราง (table)` ทั่วไป จนสามารถคิดได้ว่าทั้งสองสิ่งนี้คือสิ่งเดียวกัน

3. คอลเลกชันต่าง ๆ ถูกสร้างขึ้นมาจาก `เอกสาร (document)` จำนวนศูนย์เอกสารหรือมากกว่า และเช่นเดียวกัน เอกสารหนึ่ง ๆ ก็สามารถคิดได้ว่าคือ `แถว (row)` นั่นเอง

4. เอกสารหนึ่ง ๆ ถูกสร้างขึ้นมาจาก `ฟิลด์ (field)` จำนวนหนึ่งฟิลด์หรือมากกว่า ซึ่งผู้อ่านคงเดาได้ว่ามีลักษณะคล้ายกันกับ `คอลัมน์ (column)`

5. `ดัชนี (index)` ใน MongoDB ทำหน้าที่โดยรวมเช่นเดียวกันกับในระบบแบบ RDBMS

6. `เคอร์เซอร์ (cursor)` มีลักษณะที่แตกต่างจากหลักการห้าด้านข้างต้น มีความสำคัญไม่แพ้กันแต่มักถูกมองข้าม ซึ่งผู้เขียนมองว่าควรได้รับการพิจารณาเป็นการเฉพาะ สิ่งสำคัญที่ต้องทำความเข้าใจเกี่ยวกับเคอร์เซอร์คือในขณะร้องขอข้อมูลจาก MongoDB นั้น สิ่งที่ถูกส่งกลับมาคือตัวชี้ที่ถูกเรียกว่าเคอร์เซอร์ซึ่งไปยังชุดของผลลัพธ์ที่เราสามารถดำเนินการต่าง ๆ ได้ เช่นการนับจำนวนหรือข้ามไปข้างหน้า ก่อนที่จะมีการดึงข้อมูลออกมาจริง ๆ 

มาทบทวนกันอีกครั้ง MongoDB ถูกสร้างขึ้นมาจาก `ฐานข้อมูล` ที่ประกอบไปด้วย `คอลเลกชัน` โดยหนึ่ง `คอลเลกชัน` ถูกสร้างขึ้นมาจาก `เอกสาร` และแต่ละ `เอกสาร` ประกอบไปด้วย `ฟิลด์` ต่าง ๆ ในที่นี้ `คอลเลกชัน` สามารถถูกทำ `ดัชนี` ซึ่งช่วยเพิ่มประสิทธิภาพในการสืบค้นและจัดเรียงข้อมูล และท้ายที่สุด ในการนำข้อมูลจาก MongoDB มาใช้นั้น จะกระทำผ่าน `เคอร์เซอร์` ซึ่งการประมวลผลจริง ๆ จะถูกชะลอออกไปจนกว่าจะถึงเวลาที่จำเป็น

ทำไมต้องกำหนดคำศัพท์ขึ้นมาใหม่ (คอลเลกชัน vs. ตาราง เอกสาร vs. แถว และฟิลด์ vs. คอลัมน์)? หรือเพียงแค่ต้องการเพิ่มความซับซ้อนเท่านั้น? ในความเป็นจริง แม้ว่าหลักการพื้นฐานเหล่านี้ดูจะคล้ายคลึงกับองค์ประกอบต่าง ๆ ในฐานข้อมูลเชิงสัมพันธ์ แต่ก็ไม่ได้เหมือนกันทั้งหมด ความแตกต่างหลัก ๆ มาจากข้อเท็จจริงที่ว่าฐานข้อมูลเชิงสัมพันธ์กำหนด `คอลัมพน์` ที่ระดับ `ตาราง` ขณะที่ฐานข้อมูลที่ใช้รูปแบบเอกสารกำหนด `ฟิลด์` ที่ระดับ `เอกสาร` จึงกล่าวได้ว่าแต่ละ `เอกสาร` ใน `คอลเลกชัน` หนึ่ง ๆ สามารถมีชุดของ `ฟิลด์` ที่เฉพาะเจาะจงในเอกสารนั้น ๆ ได้ ดังนั้น `คอลเลกชัน` จึงเป็นที่จัดเก็บข้อมูลที่ดูจะฉลาดน้อยกว่าเมื่อเปรียบเทียบกับ `ตาราง` ขณะที่ `เอกสาร` หนึ่ง ๆ นั้น มีข้อมูลและสารสนเทศได้มากกว่าที่จัดเก็บได้ในหนึ่ง `แถว` มาก

แม้ว่านี่คือสิ่งสำคัญที่ต้องทำความเข้าใจ แต่อย่าเพิ่งเป็นกังวลไปหากยังเห็นภาพไม่ชัดเจนนัก หลังจากลองเพิ่มข้อมูลสักสองถึงสามครั้งก็จะเข้าใจความหมายได้เอง ในที่สุดแล้ว ประเด็นสำคัญก็คือในคอลเลกชันหนึ่ง ๆ นั้นไม่ได้มีกฎเกณฑ์ที่ตายตัวว่าจะใส่อะไรเข้าไปได้บ้าง (นั่นคือไม่มีสคีมา) ฟิลด์ต่าง ๆ ถูกติดตามไว้โดยตรงในแต่ละเอกสาร ซึ่งจุดเด่นและจุดด้อยของลักษณะเช่นนี้จะถูกกล่าวถึงในบทต่อ ๆ ไป

มาเริ่มลงมือกันดีกว่า ถ้าเซอร์ฟเวอร์ยังไม่ได้ทำงานอยู่ ให้เรียกใช้ `mongod` รวมทั้งเชลล์ mongo ได้เลย ซึ่งเชลล์นี้จะรันจาวาสคริปต์ มีหลายคำสั่งที่สามารถเรียกใช้ได้เลยโดยไม่ขึ้นกับฐานข้อมูล เช่น `help` หรือ `exit` ส่วนคำสั่งที่ต้องการใช้กับฐานข้อมูลปัจจุบันจะถูกประมวลผลผ่านออบเจกต์ `db` เช่น `db.help()` หรือ `db.stats()` ขณะที่คำสั่งต่าง ๆ ที่จะประมวลผลกับคอลเลกชันใด ๆ ซึ่งเราจะได้ใช้เป็นหลักในลำดับต่อไปนั้น จะถูกประมวลผลผ่านออบเจกต์ `db.ชื่อคอลเลกชัน` เช่น `db.unicorns.help()` หรือ `db.unicorns.count()`

ลองสั่ง `db.help()` ดู โปรแกรมจะแสดงรายการของคำสั่งที่สามารถใช้ประมวลผลออบเจกต์ `db` ได้

หมายเหตุเล็ก ๆ: เนื่องจากนี่คือเชลล์จาวาสคริปต์ หากคุณสั่งรันเมธอดโดยไม่ใส่วงเล็บ `()` คุณจะพบกับตัวโปรแกรมของเมธอดแทนที่จะเป็นการรันเมธอดนั้น ผู้เขียนขอกล่าวถึงไว้ ณ ที่นี้เพื่อผู้อ่านจะได้ไม่แปลกใจหากป้อนคำสั่งแล้วกลับพบหน้าจอที่ขึ้นต้นว่า `function (...){` ตัวอย่างเช่นหากป้อน `db.help` (โดยไม่มีวงเล็บ) โปรแกรมจะแสดงรายละเอียดของเมธอด `help` ขึ้นมาแทน

อันดับแรก เราจะใช้คำสั่ง `use` เป็นตัวช่วยสลับฐานข้อมูล ลองป้อน `use learn` ได้เลย ไม่ต้องกังวลว่าเรายังไม่มีฐานข้อมูลนี้อยู่จริง เนื่องจากหลังจากเราสร้างคอลเลกชันแรกขึ้นมาแล้ว ฐานข้อมูล `learn` ก็จะถูกสร้างขึ้นเช่นกัน เมื่อเราอยู่ในฐานข้อมูลแล้ว ก็สามารถเริ่มป้อนคำสั่งเกี่ยวกับฐานข้อมูล เช่น `db.getCollectionNames()` ได้ ถ้าลองสั่งดู คุณควรพบกับอาร์เรย์ว่าง (`[ ]`) และเนื่องจากคอลเลกชันนั้นเป็นแบบไม่มีสคีมา เราจึงไม่จำเป็นต้องสร้างขึ้นมา โดยต้องทำเพียงแค่เพิ่มเอกสารเข้าไปยังคอลเลกชันใหม่นี้เท่านั้น ซึ่งสามารถทำได้โดยใช้คำสั่ง `insert` ตามด้วยเอกสารที่ต้องการเพิ่มเข้าไป:

	db.unicorns.insert({name: 'Aurora',
		gender: 'f', weight: 450})

บรรทัดข้างต้น คือการส่งค่าพารามิเตอร์ผ่านคำสั่ง `insert` เข้าไปยังคอลเลกชัน `unicorns` การทำงานภายในของ MongoDB นั้น ใช้รูปแบบ JSON ทีเ่ป็นอนุกรมไบนารีซื่อมีชื่อเรียกว่า BSON ดังนั้นในการทำงานภายนอกนี้ เราจะใช้ JSON เป็นหลัก ดังเช่นพารามิเตอร์ที่ส่งผ่านไปนี้ หากเราสั่ง `db.getCollectionNames()` ในตอนนี้ เราจะพบกับคอลเลกชัน `unicorns`

เราสามารถใช้คำสั่ง `find` กับ `unicorns` เพื่อคืนค่าเป็นรายการเอกสารได้:

	db.unicorns.find()

สังเกตว่านอกเหนือจากข้อมูลที่เราป้อนเข้าไปแล้ว จะมีฟิลด์ `_id` เพิ่มขึ้นมา ในทุกเอกสารจะต้องมีฟิลด์ `_id` ที่มีค่าไม่ซ้ำกัน เราสามารถสร้างขึ้นมาได้เองหรือจะให้ MongoDB กำหนดค่าขึ้นมาให้ก็ได้โดยจะมีชนิดของฟิลด์เป็น `ObjectId` โดยส่วนใหญ่แล้วเราจะให้ MongoDB กำหนดค่าให้เอง ซึ่งฟิลด์ `_id` นี้จะถูกทำดัชนีให้โดยปริยาย ซึ่งเราสามารถตรวจสอบได้ด้วยคำสั่ง  `getIndexes`:

	db.unicorns.getIndexes()

เราจะพบกับชื่อของดัชนี ชื่อฐานข้อมูลและคอลเลกชันที่ดัชนีนี้ถูกนำมาใช้ และรายการของฟิลด์ต่าง ๆ ที่รวมอยู่ในดัชนี

ตอนนี้เราจะกลับมากล่าวถึงการไม่มีสคีมาในคอลเลกชันกันอีกครั้ง ลองเพิ่มเอกสารที่แตกต่างกันโดยสิ้นเชิงเข้าไปใน `unicorns` ดังนี้:

	db.unicorns.insert({name: 'Leto',
		gender: 'm',
		home: 'Arrakeen',
		worm: false})

จากนั้นใช้ `find` อีกครั้งเพื่อแสดงรายการเอกสาร เราจะกลับมาอธิบายถึงพฤติกรรมที่น่าสนใจเช่นนี้ของ MongoDB อีกครั้งหลังจากเราได้เรียนรู้เพิ่มเติมอีกสักนิด แต่ในตอนนี้ ผู้อ่านคงเริ่มเข้าใจว่าทำไมชื่อเรียกต่าง ๆ ที่ใช้ในฐานข้อมูลแบบดั้งเดิมจึงไม่เหมาะกับการนำมาใช้ในที่นี้

## รู้จักกับตัวช่วยเลือก (Selector) ##
นอกจากหลักสำคัญหกประการที่เราได้ศึกษากันไปแล้ว ยังมีประเด็นเกี่ยวกับตัวช่วยเลือกคิวรี (query selector) ที่จำเป็นต้องทำความเข้าใจการนำมาใช้กับ MongoDB ก่อนที่เราจะก้าวไปยังหัวข้อขั้นสูงขึ้นต่อไปได้ ตัวช่วยเลือกคิวรีของ MongoDB ทำหน้าที่คล้ายกับประโยค `where` ในข้อความสั่ง SQL ดังนั้น เราจึงนำมาใช้ในการดำเนินการค้นหา นับจำนวน ปรับปรุงแก้ไข และลบเอกสารต่าง ๆ ที่อยู่ในแต่ละคอลเลกชัน ตัวช่วยเลือกแต่ละตัวเป็นออบเจกต์ JSON ซึ่งในรูปแบบพื้นฐานที่สุดหรือ `{}` นั้น จะจับคู่ได้กับเอกสารทั้งหมด หรือถ้าเราต้องการค้นหายูนิคอร์นเพศเมีย (female unicorn) ทั้งหมด เราสามารถใช้ `{gender:'f'}` เป็นตัวช่วยเลือกได้

ก่อนจะลงรายละเอียดกับตัวช่วยเลือกไปมากกว่านี้ เราต้องเตรียมข้อมูลเพิ่มเติมให้สามารถเห็นภาพได้ชัดเจนขึ้นเสียก่อน อันดับแรก เราจะลบข้อมูลต่าง ๆ ที่ป้อนไว้แล้วในคอลเลกชัน `unicorns` ด้วยคำสั่ง: `db.unicorns.remove({})` จากนั้น ให้ป้อนข้อมูลลงไปดังนี้ (แนะนำให้ผู้อ่านคัดลอกไปรันได้เลย):

	db.unicorns.insert({name: 'Horny',
		dob: new Date(1992,2,13,7,47),
		loves: ['carrot','papaya'],
		weight: 600,
		gender: 'm',
		vampires: 63});
	db.unicorns.insert({name: 'Aurora',
		dob: new Date(1991, 0, 24, 13, 0),
		loves: ['carrot', 'grape'],
		weight: 450,
		gender: 'f',
		vampires: 43});
	db.unicorns.insert({name: 'Unicrom',
		dob: new Date(1973, 1, 9, 22, 10),
		loves: ['energon', 'redbull'],
		weight: 984,
		gender: 'm',
		vampires: 182});
	db.unicorns.insert({name: 'Roooooodles',
		dob: new Date(1979, 7, 18, 18, 44),
		loves: ['apple'],
		weight: 575,
		gender: 'm',
		vampires: 99});
	db.unicorns.insert({name: 'Solnara',
		dob: new Date(1985, 6, 4, 2, 1),
		loves:['apple', 'carrot',
			'chocolate'],
		weight:550,
		gender:'f',
		vampires:80});
	db.unicorns.insert({name:'Ayna',
		dob: new Date(1998, 2, 7, 8, 30),
		loves: ['strawberry', 'lemon'],
		weight: 733,
		gender: 'f',
		vampires: 40});
	db.unicorns.insert({name:'Kenny',
		dob: new Date(1997, 6, 1, 10, 42),
		loves: ['grape', 'lemon'],
		weight: 690,
		gender: 'm',
		vampires: 39});
	db.unicorns.insert({name: 'Raleigh',
		dob: new Date(2005, 4, 3, 0, 57),
		loves: ['apple', 'sugar'],
		weight: 421,
		gender: 'm',
		vampires: 2});
	db.unicorns.insert({name: 'Leia',
		dob: new Date(2001, 9, 8, 14, 53),
		loves: ['apple', 'watermelon'],
		weight: 601,
		gender: 'f',
		vampires: 33});
	db.unicorns.insert({name: 'Pilot',
		dob: new Date(1997, 2, 1, 5, 3),
		loves: ['apple', 'watermelon'],
		weight: 650,
		gender: 'm',
		vampires: 54});
	db.unicorns.insert({name: 'Nimue',
		dob: new Date(1999, 11, 20, 16, 15),
		loves: ['grape', 'carrot'],
		weight: 540,
		gender: 'f'});
	db.unicorns.insert({name: 'Dunx',
		dob: new Date(1976, 6, 18, 18, 18),
		loves: ['grape', 'watermelon'],
		weight: 704,
		gender: 'm',
		vampires: 165});

เมื่อเรามีข้อมูลแล้ว เราก็สามารถใช้ตัวช่วยเลือกได้หลากหลายขึ้น ในที่นี้ `{field: value}` ถูกใช้เพื่อค้นหาเอกสารใด ๆ ที่ `field` มีค่าตรงกับ `value` และ `{field1: value1, field2: value2}` แสดงตัวอย่างการใช้และ (`and`) ในการค้นหา เราสามารถใช้ `$lt` `$lte` `$gt` `$gte` และ `$ne` เป็นตัวดำเนินการเพื่อเปรียบเทียบแบบน้อยกว่า น้อยกว่าหรือเท่ากับ มากกว่า มากกว่าหรือเท่ากับ และไม่เท่ากับ ได้ตามลำดับ ตัวอย่างเช่น หากต้องการค้นหายูนิคอร์นเพศผู้ที่มีน้ำหนักมากกว่า 700 ปอนด์ ก็สามารถทำได้ด้วย:

	db.unicorns.find({gender: 'm',
		weight: {$gt: 700}})
	//หรือ (แม้จะมีความหมายต่างกัน 
	//แต่สามารถแสดงตัวอย่างโดยได้ผลเช่นเดียวกัน)
	db.unicorns.find({gender: {$ne: 'f'},
		weight: {$gte: 701}})


เราสามารถใช้ตัวดำเนินการ `$exists` เพื่อตรวจจับว่ามีฟิลด์นั้น ๆ อยู่หรือไม่ ตัวอย่างเช่น:

	db.unicorns.find({
		vampires: {$exists: false}})

ควรแสดงผลเอกสารเพียงหนึ่งรายการ ขณะที่ตัวดำเนินการ '$in' ถูกใช้เพื่อตรวจจับว่ามีค่าตรงกับหนึ่งในรายการของอาร์เรย์ที่เราป้อนเข้าไปหรือไม่ เช่น:

    db.unicorns.find({
    	loves: {$in:['apple','orange']}})

ซึ่งจะแสดงยูนิคอร์นทุกรายการที่มีข้อมูลว่าชอบ 'apple' หรือ 'orange'

หากเราต้องการนำหลาย ๆ เงื่อนไขในฟิลด์ที่แตกต่างกันมาทำการหรือ (OR) แทนการและ (AND) นั้น ก็สามารถทำได้โดยใช้ตัวดำเนินการ `$or` แล้วกำหนดอาร์เรย์ของตัวช่วยค้นหารายการต่าง ๆ ที่ต้องการนำมา หรือ (OR) เข้าด้วยกัน:

	db.unicorns.find({gender: 'f',
		$or: [{loves: 'apple'},
			  {weight: {$lt: 500}}]})

ตัวอย่างข้างต้นจะแสดงรายการยูนิคอร์นเพศเมียทั้งหมดที่ชอบแอปเปิลหรือมีน้ำหนักน้อยกว่า 500 ปอนด์

มีบางอย่างน่าสนใจเกิดขึ้นในตัวอย่างล่าสุดทั้งสองของเรานี้ ผู้อ่านอาจสังเกตเห็นแล้วว่าฟิลด์ `loves` นั้นเป็นอาร์เรย์ เนื่องจาก MongoDB รองรับอาร์เรย์เป็นออบเจกต์พื้นฐาน ซึ่งนี่เป็นคุณสมบัติที่มีประโยชน์เป็นอย่างยิ่งจนหลังจากเริ่มใช้แล้ว อาจทำให้รู้สึกว่าอยู่มาได้อย่างไรโดยไม่ได้ใช้คุณสมบัตินี้ สิ่งที่น่าสนใจยิ่งขึ้นไปอีกคือความง่ายในการเลือกด้วยการอ้างถึงข้อมูลที่อยู่ในอาร์เรย์ เช่นการเลือกด้วย: `{loves: 'watermelon'}` ก็จะแสดงเอกสารทุกรายการที่มี `watermelon` เป็นค่าหนึ่งที่อยู่ใน `loves`

ยังมีตัวดำเนินการอื่นให้ใช้อีกมาก นอกเหนือจากตัวดำเนินการที่กล่าวถึงไว้ในที่นี้ ซึ่งทั้งหมดนั้นจะถูกกล่าวถึงโดยละเอียดในส่วนของ [ตัวช่วยเลือกคิวรี (Query Selectors)](http://docs.mongodb.org/manual/reference/operator/query/#query-selectors) ในคู่มือ MongoDB อย่างไรก็ตาม ตัวดำเนินการต่าง ๆ ที่ได้ครอบคลุมมาถึงขณะนี้นั้นก็เพียงพอต่อการเริ่มใช้งานแล้ว และโดยส่วนใหญ่เราก็มักใช้เพียงตัวดำเนินการพื้นฐานเหล่านี้เป็นหลัก

เราได้เห็นวิธีการนำตัวช่วยเลือกมาใช้ร่วมกันคำสั่ง `find` กันแล้ว ตัวช่วยเหลือกเหล่านี้ยังสามารถถูกใช้ร่วมกับคำสั่ง `remove` เพื่อลบข้อมูลดังที่ได้เห็นเบื้องต้นมาแล้วได้เช่นกัน และสามารถนำมาใช้กับคำสั่ง `count` ที่ยังไม่ได้ลองใช้กันแต่ผู้อ่านก็น่าจะพอเห็นภาพได้ ตลอดจนคำสั่ง `update` ที่เราจะมาใช้เวลาเพิ่มเติมเพื่อทดลองใช้กันต่อไป

ในส่วนของ `ObjectId` ที่ MongoDB สร้างขึ้นมาให้กับฟิลด์ `_id` ของเราก็สามารถถูกเลือกได้เช่นกัน:

	db.unicorns.find(
		{_id: ObjectId("ค่าของ ObjectId")})

## ในบทนี้ ##
แม้ว่าเรายังไม่ได้ดูรายละเอียดเกี่ยวกับคำสั่ง `update` หรือความสามารถเด่น ๆ ที่เราสามารถทำได้ด้วย `find` อย่างไรก็ตาม เราได้เริ่มใช้งาน MongoDB ได้ลองใช้คำสั่ง `insert` และ `remove` เพื่อเพิ่มและลบข้อมูล (ซึ่งไม่ได้มีอะไรมากไปกว่าที่เราได้ลองใช้ไปแล้วนัก) เราได้เริ่มใช้ `find` เพื่อค้นหาข้อมูล และได้รู้ว่าตัวช่วยเลือก (`selectors`) ของ MongoDB นั้นคืออะไร ในตอนนี้ เราได้วางรากฐานสำหรับสิ่งต่าง ๆ ที่จะเรียนรู้กันต่อไปได้อย่างเข้มแข็ง เชื่อหรือไม่ว่าขณะนี้ผู้อ่านได้เรียนรู้ส่วนใหญ่ของสิ่งที่จำเป็นต่อการเริ่มใช้ MongoDB ไปเรียบร้อยแล้ว - นั่นเป็นเพราะ MongoDB ถูกสร้างให้ง่ายต่อการเรียนรู้และใช้งาน ผู้เขียนขอแนะนำให้ผู้อ่านทดลองเล่นกับฐานข้อมูลที่ได้ติดตั้งไว้อีกเล็กน้อยก่อนที่จะไปยังบทต่อไป ลองเพิ่มอีกหลาย ๆ เอกสาร หรือถ้าเป็นไปได้ให้เพิ่มลงในคอลเลกชันใหม่ และทำความคุ้นเคยกับตัวช่วยเลือกต่าง ๆ รวมถึงลองใช้คำสั่ง `find` `count` และ `remove` หลังจากได้ลองทำสิ่งเหล่านี้สักสองถึงสามครั้งแล้ว สิ่งต่าง ๆ ที่อาจดูแปลกในช่วงแรกก็น่าจะดูเข้าที่เข้าทางมากขึ้น

# บทที่ 2 - การอัพเดต #
เราได้ทำความคุ้นเคยกับองค์ประกอบสามในสี่ด้านของ CRUD - Create (สร้าง) Read (อ่าน) Update (อัพเดต) และ Delete (ลบ) กันในบทที่ 1 มาแล้ว ในบททนี้ เราจะมากล่าวถึงด้านที่เราข้ามไปคือ: การอัพเดต (`update`) แต่เนื่องจากการ `update` มีพฤติกรรมบางอย่างที่อาจดูน่าแปลกใจ เราจึงแยกออกมาเป็นอีกหนึ่งบทโดยเฉพาะ

## อัพเดต: จะแทนที่หรือจะ $set ##
โดยพื้นฐานแล้วการ `update` ต้องการสองพารามิเตอร์: ตัวช่วยเลือก (where) ที่จะใช้ค้นหา กับสิ่งที่ต้องการอัพเดตให้กับฟิลด์ต่าง ๆ ตัวอย่างเช่น หากยูนิคอร์นชื่อ Roooooodles น้ำหนึกขึ้นมาเล็กน้อย ผู้อ่านอาจคาดว่าเราควรสั่งประมวลผลดังนี้:

	db.unicorns.update({name: 'Roooooodles'},
		{weight: 590})

(หากคุณได้ลองเล่นกับคอลเลกชัน `unicorns` จนไม่มีข้อมูลดั้งเดิมเหลืออยู่แล้ว โปรดสั่ง `remove` เพื่อลบเอกสารทั้งหมด แล้วใช้โค้ดในบทที่ 1 เพื่อเพิ่มเอกสารต่าง ๆ กลับเข้าไปอีกครั้ง)

ในตอนนี้ หากเราลองเรียกดูเรคอร์ดที่ถูกอัพเดตแล้ว:

	db.unicorns.find({name: 'Roooooodles'})

ผู้อ่านน่าจะพบเรื่องน่าแปลกใจเรื่องแรกเกี่ยวกับการ `update` แล้ว เนื่องจากคำสั่งนี้จะไม่พบเอกสารตามชื่อที่ระบุ เพราะค่าพารามิเตอร์ที่สองที่เราป้อนไปนั้นไม่ได้ระบุตัวดำเนินการใด ๆ ไว้ ดังนั้นคำสั่งนี้จึงเป็นการ **แทนที่** เอกสารต้นฉบับ หรือกล่าวอีกนัยหนึ่งคือคำสั่ง `update` พบเอกสารตามฟิลด์ `name` ที่กำหนด แล้วจึงแทนที่เอกสารท้งหมดนั้นด้วยเอกสารใหม่ (ค่าที่ระบุในพารามิเตอร์ที่สอง) การทำงานในลักษณะเช่นเดียวกันนี้ไม่มีอยู่ในคำสั่ง `update` ของ SQL ซึ่งรูปแบบเช่นนี้อาจช่วยอำนวยความสะดวกได้เป็นอย่างยิ่งกับการอัพเดตข้อมูลในบางสถานการณ์ อย่างไรก็ตาม หากต้องการเปลี่ยนแปลงข้อมูลในหนึ่งหรือเพียงไม่กี่ฟิลด์แล้วนั้น จะต้องใช้ตัวดำเนินการ `$set` ของ MongoDB ซึ่งเราจะใช้คำสั่งนี้เพื่ออัพเดตข้อมูลในฟิลด์ต่าง ๆ ที่หายไปของเรา:

	db.unicorns.update({weight: 590}, {$set: {
		name: 'Roooooodles',
		dob: new Date(1979, 7, 18, 18, 44),
		loves: ['apple'],
		gender: 'm',
		vampires: 99}})

คำสั่งข้างต้นจะไม่เปลี่ยนแปลงฟิลด์ `weight` เนื่องจากไม่ได้ระบุค่าไว้ ในตอนนี้ หากเราสั่ง:

	db.unicorns.find({name: 'Roooooodles'})

เราจะได้ผลลัพธ์ตามที่คาดหมายไว้ ดังนั้น หากเราต้องการอัพเดตน้ำหนักให้ถูกต้องตามที่ต้องการตั้งแต่แรกนั้นจะต้องใช้คำสั่งดังนี้:

	db.unicorns.update({name: 'Roooooodles'},
		{$set: {weight: 590}})

## ตัวดำเนินการในการอัพเดต ##
นอกเหนือจาก `$set` แล้ว เรายังสามารถใช้ตัวดำเนินการอื่น ๆ สำหรับงานที่แตกต่างกันไป เนื่องจากตัวดำเนินการอัพเดตทั้งหมดทำงานในระดับฟิลด์ - จึงไม่ต้องกังวัลว่าตัวเอกสารจะถูกลบไป ตัวอย่างการใช้งานเช่นในกรณีที่เราบันทึกข้อมูลจำนวนแวมไพร์ที่ถูกสังหารไปโดยยูนิคอร์นที่ชื่อ Pilot ไว้ไม่ถูกต้อง ก็สามารถใช้ตัวดำเนินการ `$inc` ที่ใช้เพื่อนำค่าบวกหรือค่าลบมาบวกเข้ากับฟิลด์ต่าง ๆ มาแก้ไขได้ดังนี้:

	db.unicorns.update({name: 'Pilot'},
		{$inc: {vampires: -2}})

หากอยู่มาวันหนึ่ง Aurora เกิดชอบของหวานขึ้นมา เราก็สามารถเพิ่มค่าดังกล่าวเข้าไปในฟิลด์ `loves` โดยใช้ตัวดำเนินการ `$push` ได้ดังนี้:

	db.unicorns.update({name: 'Aurora'},
		{$push: {loves: 'sugar'}})

ผู้อ่านสามารถดูรายละเอียดเพิ่มเติมเกี่ยวกับตัวดำเนินการในการอัพเดตอื่น ๆ ได้ที่ส่วนของ [ตัวดำเนินการอัพเดต (Update Operators)](http://docs.mongodb.org/manual/reference/operator/update/#update-operators) ในคู่มือของ MongoDB

## อัพเสิร์ต (Upsert) ##
อีกหนึ่งเรื่องน่าแปลกใจที่มีประโยชน์อย่างยิ่งในการใช้ `update` คือการรองรับการอัพเสิร์ต (`upsert`) อย่างเต็มรูปแบบ การ `upsert` จะอัพเดตเอกสารหากพบว่ามีเอกสารนั้นอยู่แล้ว และจะเพิ่มให้ทันทีหากยังไม่มีเอกสารนั้น ๆ  การอัพเสิร์ตเช่นนี้ช่วยอำนวยความสะดวกได้เป็นอย่างยิ่งในหลายสถานการณ์ ซึ่งผู้อ่านจะทราบได้ทันทีเมื่อต้องเผชิญสถานการณ์เช่นนี้ เราสามารถเปิดใช้การอัพเสิร์ตได้โดยส่งผ่านพารามิเตอร์ `{upsert:true}` เป็นค่าที่สามไปพร้อมกับคำสั่งขณะอัพเดต

ตัวนับการเข้าชมเว็บไซต์แสดงการนำลักษณะเช่นนี้ไปใช้งานจริงได้เป็นอย่างดี หากเราต้องการรวบรวมจำนวนนับแบบเรียลไทม์นั้น เราต้องตรวจสอบว่ามีข้อมูลสำหรับหน้านั้น ๆ อยู่แล้วหรือไม่ และใช้ข้อมูลดังกล่าวเพื่อตัดสินใจว่าจะทำการอัพเดตข้อมูลที่มีอยู่แล้วหรือเพิ่มเรคคอร์ดสำหรับหน้านั้นขึ้นมาใหม่ หากไม่ได้กำหนดตัวเลือกอัพเสิร์ต (หรือกำหนดให้เป็นเท็จ) การประมวลผลต่อไปนี้จะไม่มีผลแต่อย่างใด:

	db.hits.update({page: 'unicorns'},
		{$inc: {hits: 1}});
	db.hits.find();

อย่างไรก็ตาม หากเปิดใช้ตัวเลือกอัพเสิร์ตแล้ว ผลที่ได้จะแตกต่างออกไป:

	db.hits.update({page: 'unicorns'},
		{$inc: {hits: 1}}, {upsert:true});
	db.hits.find();

เนื่องจากยังไม่มีเอกสารใดที่ค่าในฟิลด์ `page` เป็น `unicorns` ดังนั้น เอกสารใหม่จึงถูกเพิ่มเข้าไป หากเรารันคำสั่งนี้เป็นครั้งที่สอง เอกสารนี้ก็จะถูกอัพเดตให้ `hits` มีค่าเพิ่มขึ้นเป็น 2

	db.hits.update({page: 'unicorns'},
		{$inc: {hits: 1}}, {upsert:true});
	db.hits.find();

## การอัพเดตหลายรายการ ##
เรื่องน่าแปลกใจประการสุดท้ายของ `update` คือโดยค่าตั้งต้นแล้วจะทำการอัพเดตเอกสารเพียงรายการเดียวเท่านั้น หากพิจารณาเฉพาะจากตัวอย่างที่ผ่านมาทุกอย่างอาจยังดูสมเหตุสมผล อย่างไรก็ตาม หากใช้คำสั่งดังนี้แล้ว:

	db.unicorns.update({},
		{$set: {vaccinated: true }});
	db.unicorns.find({vaccinated: true});

เราอาจคาดว่ายูนิคอร์นทั้งหมดของเราจะถูกกำหนดค่าว่าได้รับการฉีดวัคซีนแล้ว (vaccinated) แต่ถ้าต้องการให้ได้ผลดังที่คาดหวังไว้นั้น ตัวเลือก `multi` ต้องถูกกำหนดให้เป็นจริงด้วย:

	db.unicorns.update({},
		{$set: {vaccinated: true }},
		{multi:true});
	db.unicorns.find({vaccinated: true});

## ในบทนี้ ##
ในบทนี้ เราได้สรุปปิดท้ายการทำความรู้จักกระบวนการ CRUD เบื้องต้นที่ดำเนินการกับคอลเลกชัน เราได้ศึกษารายละเอียดเกี่ยวกับการ `update` พร้อมทั้งได้สังเกตพฤติกรรมสามประการที่น่าแปลกใจ ประการแรกคือหากส่งผ่านเอกสารเข้าไปโดยไม่ระบุตัวดำเนินการในการอัดเดตแล้ว การ `update` ของ MongoDB จะแทนที่เอกสารดังกล่าว ด้วยเหตุผลนี้ โดยปกติแล้วเราจึงต้องใช้ตัวดำเนินการ `$set` (หรือตัวดำเนินการอื่น ๆ ที่ใช้เพื่อแก้ไขเอกสาร) ร่วมด้วยเสมอ ประการที่สอง การ `update` รองรับตัวเลือก `upsert` ซึ่งมีประโยชน์อย่างยิ่งในกรณีที่เราไม่ทราบว่ามีเอกสารเดิมอยู่แล้วหรือไม่ และท้ายที่สุด การ `update` จะดำเนินการกับเอกสารแรกที่ตรงตามเงื่อนไขที่กำหนดเท่านั้น หากต้องการดำเนินการกับเอกสารทั้งหมดที่ตรงตามเงื่อนไข ก็ต้องระบุตัวเลือก `multi` ด้วย

# บทที่ 3 - รู้ลึกเรื่องการค้นหา (Find) #
ในบทที่ 1 เราได้กล่าวถึงภาพรวมของคำสั่ง `find` กันมาบ้างแล้ว แต่คำสั่ง `find` ยังมีความสามารถที่นอกเหนือไปจากการใช้ตัวช่วยเลือก (`selectors`) เราได้กล่าวถึงไว้แล้วว่าการใช้ `find` จะคืนค่าเป็นเคอร์เซอร์ (`cursor`) ซึ่งจะได้อธิบายในรายละเอียดให้ ณ ที่นี้

## การเลือกฟิลด์ ##
ก่อนจะลงลึกไปกับ `cursors` นั้น เราควรทราบก่อนว่า `find` รองรับพารามิเตอร์ตัวที่สองซึ่งอาจมีหรือไม่มีก็ได้ที่เรียกว่า "projection" โดยพารามิเตอร์นี้ คือรายการของฟิลด์ที่เราต้องการเรียกใช้หรืออาจต้องการให้ละเว้นไว้ ตัวอย่างเช่น เราสามารถกำหนดให้แสดงเฉพาะชื่อ (name) ของยูนิคอร์นทั้งหมดโดยไม่ต้องเรียกใช้ฟิลด์อื่น ๆ ด้วยคำสั่งดังนี้:

	db.unicorns.find({}, {name: 1});

โดยปกติแล้ว ฟิลด์ `_id` จะถูกคืนค่ากลับมาเสมอ แต่เราสามารถกำหนดให้ละเว้นไม่นำมาแสดงได้โดยระบุว่า `{name:1, _id: 0}`

นอกเหนือจากฟิลด์ `_id` แล้ว เราไม่สามารถใช้การระบุให้มีหรือให้ละเว้นฟิลด์ต่าง ๆ คละกันได้ ซึ่งถ้าพิจารณาแล้วจะเห็นได้ว่าสมเหตุสมผล เพราะเราคงต้องการเลือกบางฟิลด์ขึ้นมาใช้งาน หรือไม่ก็ต้องการระบุให้ละเว้นบางฟิลด์จากฟิลด์ต่าง ๆ ทั้งหมดนั้น

## การจัดเรียง (Ordering) ##
ผู้เขียนได้กล่าวถึงมาบ้างแล้วว่า `find` จะคืนค่าเป็นเคอร์เซอร์ โดยการประมวลผลจะถูกชะลอไปจนกว่าจะถึงเวลาจำเป็นจริง ๆ อย่างไรก็ตาม ผู้อ่านคงสังเกตเห็นได้จากการใช้เชลล์ว่า `find` แสดงผลให้เห็นได้ในทันที แต่พฤติกรรมดังนี้เกิดขึ้นเฉพาะในเชลล์เท่านั้น เราสามารถสังเกตพฤติกรรมที่แท้จริงของ `cursors` ได้จากเมธอดต่าง ๆ ที่เราสามารถเชื่อมต่อเข้ากับ `find` โดยเมธอดแรกที่จะมาลองดูกันคือการจัดเรียง (`sort`) ซึ่งเราสามารถระบุรายการฟิลด์ต่าง ๆ ที่ต้องการจัดเรียงในรูปแบบเอกสาร JSON ได้โดยใช้ 1 สำหรับการเรียงจากน้อยไปหามาก และ -1 สำหรับการจัดเรียงจากมากไปหาน้อย ดังตัวอย่างต่อไปนี้:

	//ให้แสดงยูนิคอร์นที่มีน้ำหนักมากที่สุดขึ้นมาก่อน
	db.unicorns.find().sort({weight: -1})

	//จัดเรียงตามชื่อยูนิคอร์นแล้วตามด้วยจำนวนแวมไพร์ที่สังหารไปได้:
	db.unicorns.find().sort({name: 1,
		vampires: -1})

MongoDB สามารถใช้ดัชนี (index) สำหรับการจัดเรียงได้เช่นเดียวกับในฐานข้อมูลเชิงสัมพันธ์ เราจะพิจารณารายละเอียดเกี่ยวกับดัชนีกันในภายหลัง อย่างไรก็ตาม โปรดทราบว่า MongoDB จะจำกัดขนาดของผลการจัดเรียงที่ไม่ได้ทำดัชนีไว้ นั่นคือโปรแกรมจะแสดงข้อผิดพลาดหากเราพยายามจัดเรียงชุดของข้อมูลผลลัพธ์ที่มีขนาดใหญ่มาก ๆ ที่ไม่ได้ทำดัชนีไว้ ซึ่งบางคนอาจมองว่านี่คือข้อจำกัดของโปรแกรม แต่ในความเป็นจริงแล้ว ผู้เขียนมองว่าฐานข้อมูลอื่น ๆ ควรสามารถปฏิเสธการรันคิวรีที่ไม่ได้รับการจัดเตรียมให้มีประสิทธิภาพ (optimized) ไว้ได้ในลักษณะเช่นเดียวกันนี้ (ผู้เขียนไม่ได้ต้องการกล่าวถึงข้อด้อยของ MongoDB ให้กลายเป็นข้อดีเสมอไป แต่ในกรณีนี้ ผู้เขียนเคยมีประสบการณ์กับฐานข้อมูลที่ไม่ได้รับการจัดเตรียมให้มีประสิทธิภาพ และหวังเป็นอย่างยิ่งว่าฐานข้อมูลเหล่านั้นมีโหมดที่สามารถจำกัดการทำงานได้เช่นเดียวกันนี้)

## การแบ่งหน้า (Paging) ##
การนำผลลัพธ์ที่ได้มาแสดงเป็นหน้า ๆ สามารถทำได้โดยใช้เมธอดจำกัด (`limit`) และข้าม (`skip`) ของเคอร์เซอร์ผลลัพธ์นั้น ๆ ในกรณีที่ต้องการแสดงยูนิคอร์นที่มีน้ำหนักมากที่สุดเป็นอันดับสองและสาม เราสามารถสั่งการได้ดังนี้:

	db.unicorns.find()
		.sort({weight: -1})
		.limit(2)
		.skip(1)

การใช้ `limit` ร่วมกับการ `sort` นั้นสามารถถูกนำมาใช้เพื่อป้องกันปัญหาในกรณีที่ต้องการจัดเรียงฟิลด์ที่ไม่ได้ทำดัชนี้เอาไว้เช่นกัน

## การนับจำนวน (Count) ##
เราสามารถสั่งให้นับจำนวน (`count`) รายการต่าง ๆ ในคอลเลกชันได้โดยตรงจากเชลล์ ดังตัวอย่างนี้:

	db.unicorns.count({vampires: {$gt: 50}})

อันที่จริง `count` ก็คือหนึ่งในเมธอดของ `cursor` ที่เชลล์จัดเตรียมเป็นทางลัดไว้ให้ ในกรณีที่ใช้ไดรฟ์เวอร์อื่น ๆ ที่ไม่มีทางลัดดังกล่าว จะต้องสั่งการดังนี้ (ซึ่งสามารถสั่งการผ่านเชลล์ได้เช่นเดียวกัน):

	db.unicorns.find({vampires: {$gt: 50}})
		.count()

## ในบทนี้ ##
การค้นหาโดยใช้ `find` และ `cursors` มีรูปแบบที่ตรงไปตรงมา นอกจากคำสั่งที่ได้กล่าวมาแล้ว ยังมีคำสั่งอื่น ๆ ที่อาจกล่าวถึงในบทต่อ ๆ ไปหรืออาจนำมาใช้ในกรณีพิเศษต่าง ๆ เท่านั้น แต่ในตอนนี้ ผู้อ่านน่าจะสร้างความคุ้นเคยในการใช้งานเชลล์ของ mongo รวมถึงเข้าใจหลักการพื้นฐานของ MongoDB ได้เป็นอย่างดีแล้ว

# บทที่ 4 - การออกแบบข้อมูล (Data Modeling) #
เราลองมาเปลี่ยนมุมมองและกล่าวถึงด้านที่เป็นนามธรรมเกี่ยวกับ MongoDB กันบ้าง การอธิบายเกี่ยวกับคำใหม่ ๆ และวากยสัมพันธ์ใหม่ ๆ เป็นเรื่องที่ตรงไปตรงมา แต่การกล่าวถึงการออกแบบที่ใช้กรอบแนวคิด (paradigm) แบบใหม่อาจไม่ง่ายเช่นนั้น อันที่จริงพวกเราส่วนใหญ่ยังอยู่ระหว่างการพยายามค้นหาว่าอะไรบ้างที่ใช้ได้หรือใช้ไม่ได้กับเทคโนโลยีใหม่ ๆ เช่นนี้ นี่คือประเด็นที่เราสามารถเริ่มบทสนทนากันได้ แต่ท้ายที่สุดแล้ว ผู้อ่านจะต้องทดลองและเรียนรู้จากการเขียนโค้ดขึ้นมาจริง ๆ

จากฐานข้อมูลชนิด NoSQL ต่าง ๆ นั้น ฐานข้อมูลที่มีพื้นฐานบนเอกสารดูจะมีความคล้ายคลึงกับฐานข้อมูลเชิงสัมพันธ์มากที่สุดแล้ว - อย่างน้อยเมื่อพิจารณาด้านการออกแบบข้อมูล อย่างไรก็ตาม ด้านที่แตกต่างกันก็มีความสำคัญไม่แพ้กัน

## ไม่มีการเชื่อมตาราง (Join) ##
ความแตกต่างประการแรกและเป็นหลักการพื้นฐานสำคัญที่ผู้อ่านต้องทำความคุ้นเคยคือการที่ MongoDB ไม่มีการเชื่อมตาราง (join) ผู้เขียนเองก็ไม่ทราบว่าเหตุใด MongoDB จึงไม่สนับสนุนการเชื่อมตารางไม่ว่าในรูปแบบใด ๆ แต่ผู้เขียนเข้าใจดีว่าการเชื่อมตารางนั้นถูกมองว่าไม่สามารถปรับเปลี่ยนขนาดได้ (non-scalable) นั่นคือหากเราเริ่มแบ่งข้อมูลออกตามแนวนอนแล้ว ในที่สุดก็ต้องทำการเชื่อมโยงข้อมูลทางฝั่งไคลเอนต์ (แอปพลิเคชันเซอร์ฟเวอร์) อยู่ดี ดังน้้น ไม่ว่าจะเป็นด้วยสาเหตุประการใด แต่ข้อเท็จจริงก็คือตัวข้อมูลนั้น*สัมพันธ์*กัน แต่ MongoDB ไม่รองรับการเชื่อมตารางหรือ join

Without knowing anything else, to live in a join-less world, we have to do joins ourselves within our application's code. Essentially we need to issue a second query to `find` the relevant data in a second collection. Setting our data up isn't any different than declaring a foreign key in a relational database. Let's give a little less focus to our beautiful `unicorns` and a bit more time to our `employees`. The first thing we'll do is create an employee (I'm providing an explicit `_id` so that we can build coherent examples)

	db.employees.insert({_id: ObjectId(
		"4d85c7039ab0fd70a117d730"),
		name: 'Leto'})

Now let's add a couple employees and set their manager as `Leto`:

	db.employees.insert({_id: ObjectId(
		"4d85c7039ab0fd70a117d731"),
		name: 'Duncan',
		manager: ObjectId(
		"4d85c7039ab0fd70a117d730")});
	db.employees.insert({_id: ObjectId(
		"4d85c7039ab0fd70a117d732"),
		name: 'Moneo',
		manager: ObjectId(
		"4d85c7039ab0fd70a117d730")});


(It's worth repeating that the `_id` can be any unique value. Since you'd likely use an `ObjectId` in real life, we'll use them here as well.)

Of course, to find all of Leto's employees, one simply executes:

	db.employees.find({manager: ObjectId(
		"4d85c7039ab0fd70a117d730")})

There's nothing magical here. In the worst cases, most of the time, the lack of join will merely require an extra query (likely indexed).

## Arrays and Embedded Documents ##
Just because MongoDB doesn't have joins doesn't mean it doesn't have a few tricks up its sleeve. Remember when we saw that MongoDB supports arrays as first class objects of a document? It turns out that this is incredibly handy when dealing with many-to-one or many-to-many relationships. As a simple example, if an employee could have two managers, we could simply store these in an array:

	db.employees.insert({_id: ObjectId(
		"4d85c7039ab0fd70a117d733"),
		name: 'Siona',
		manager: [ObjectId(
		"4d85c7039ab0fd70a117d730"),
		ObjectId(
		"4d85c7039ab0fd70a117d732")] })

Of particular interest is that, for some documents, `manager` can be a scalar value, while for others it can be an array. Our original `find` query will work for both:

	db.employees.find({manager: ObjectId(
		"4d85c7039ab0fd70a117d730")})

You'll quickly find that arrays of values are much more convenient to deal with than many-to-many join-tables.

Besides arrays, MongoDB also supports embedded documents. Go ahead and try inserting a document with a nested document, such as:

	db.employees.insert({_id: ObjectId(
		"4d85c7039ab0fd70a117d734"),
		name: 'Ghanima',
		family: {mother: 'Chani',
			father: 'Paul',
			brother: ObjectId(
		"4d85c7039ab0fd70a117d730")}})

In case you are wondering, embedded documents can be queried using a dot-notation:

	db.employees.find({
		'family.mother': 'Chani'})

We'll briefly talk about where embedded documents fit and how you should use them.

Combining the two concepts, we can even embed arrays of documents:

	db.employees.insert({_id: ObjectId(
		"4d85c7039ab0fd70a117d735"),
		name: 'Chani',
		family: [ {relation:'mother',name: 'Chani'},
			{relation:'father',name: 'Paul'},
			{relation:'brother', name: 'Duncan'}]})


## Denormalization ##
Yet another alternative to using joins is to denormalize your data. Historically, denormalization was reserved for performance-sensitive code, or when data should be snapshotted (like in an audit log). However, with the ever-growing popularity of NoSQL, many of which don't have joins, denormalization as part of normal modeling is becoming increasingly common. This doesn't mean you should duplicate every piece of information in every document. However, rather than letting fear of duplicate data drive your design decisions, consider modeling your data based on what information belongs to what document.

For example, say you are writing a forum application. The traditional way to associate a specific `user` with a `post` is via a `userid` column within `posts`. With such a model, you can't display `posts` without retrieving (joining to) `users`. A possible alternative is simply to store the `name` as well as the `userid` with each `post`. You could even do so with an embedded document, like `user: {id: ObjectId('Something'), name: 'Leto'}`. Yes, if you let users change their name, you may have to update each document (which is one multi-update).

Adjusting to this kind of approach won't come easy to some. In a lot of cases it won't even make sense to do this. Don't be afraid to experiment with this approach though. It's not only suitable in some circumstances, but it can also be the best way to do it.

## Which Should You Choose? ##
Arrays of ids can be a useful strategy when dealing with one-to-many or many-to-many scenarios. But more commonly, new developers are left deciding between using embedded documents versus doing "manual" referencing.

First, you should know that an individual document is currently limited to 16 megabytes in size. Knowing that documents have a size limit, though quite generous, gives you some idea of how they are intended to be used. At this point, it seems like most developers lean heavily on manual references for most of their relationships. Embedded documents are frequently leveraged, but mostly for smaller pieces of data which we want to always pull with the parent document. A real world example may be to store an `addresses` documents with each user, something like:

	db.users.insert({name: 'leto',
		email: 'leto@dune.gov',
		addresses: [{street: "229 W. 43rd St",
		            city: "New York", state:"NY",zip:"10036"},
		           {street: "555 University",
		            city: "Palo Alto", state:"CA",zip:"94107"}]})

This doesn't mean you should underestimate the power of embedded documents or write them off as something of minor utility. Having your data model map directly to your objects makes things a lot simpler and often removes the need to join. This is especially true when you consider that MongoDB lets you query and index fields of an embedded documents and arrays.

## Few or Many Collections ##
Given that collections don't enforce any schema, it's entirely possible to build a system using a single collection with a mishmash of documents but it would be a very bad idea.  Most MongoDB systems are laid out somewhat similarly to what you'd find in a relational system, though with fewer collections. In other words, if it would be a table in a relational database, there's a chance it'll be a collection in MongoDB (many-to-many join tables being an important exception as well as tables that exist only to enable one to many relationships with simple entities).

The conversation gets even more interesting when you consider embedded documents. The example that frequently comes up is a blog. Should you have a `posts` collection and a `comments` collection, or should each `post` have an array of `comments` embedded within it? Setting aside the 16MB document size limit for the time being (all of *Hamlet* is less than 200KB, so just how popular is your blog?), most developers should prefer to separate things out. It's simply cleaner, gives you better performance and more explicit.  MongoDB's flexible schema allows you to combine the two approaches by keeping comments in their own collection but embedding a few comments (maybe the first few) in the blog post to be able to display them with the post.  This follows the principle of keeping together data that you want to get back in one query.

There's no hard rule (well, aside from 16MB). Play with different approaches and you'll get a sense of what does and does not feel right.

## In This Chapter ##
Our goal in this chapter was to provide some helpful guidelines for modeling your data in MongoDB, a starting point, if you will. Modeling in a document-oriented system is different, but not too different, than in a relational world. You have more flexibility and one constraint, but for a new system, things tend to fit quite nicely. The only way you can go wrong is by not trying.

# Chapter 5 - When To Use MongoDB #
By now you should have a feel for where and how MongoDB might fit into your existing system. There are enough new and competing storage technologies that it's easy to get overwhelmed by all of the choices.

For me, the most important lesson, which has nothing to do with MongoDB, is that you no longer have to rely on a single solution for dealing with your data. No doubt, a single solution has obvious advantages, and for a lot projects - possibly even most - a single solution is the sensible approach. The idea isn't that you *must* use different technologies, but rather that you *can*. Only you know whether the benefits of introducing a new solution outweigh the costs.

With that said, I'm hopeful that what you've seen so far has made you see MongoDB as a general solution. It's been mentioned a couple times that document-oriented databases share a lot in common with relational databases. Therefore, rather than tiptoeing around it, let's simply state that MongoDB should be seen as a direct alternative to relational databases. Where one might see Lucene as enhancing a relational database with full text indexing, or Redis as a persistent key-value store, MongoDB is a central repository for your data.

Notice that I didn't call MongoDB a *replacement* for relational databases, but rather an *alternative*. It's a tool that can do what a lot of other tools can do. Some of it MongoDB does better, some of it MongoDB does worse. Let's dissect things a little further.

## Flexible Schema ##
An oft-touted benefit of document-oriented database is that they don't enforce a fixed schema. This makes them much more flexible than traditional database tables. I agree that flexible schema is a nice feature, but not for the main reason most people mention.

People talk about schema-less as though you'll suddenly start storing a crazy mishmash of data. There are domains and data sets which can really be a pain to model using relational databases, but I see those as edge cases. Schema-less is cool, but most of your data is going to be highly structured. It's true that having an occasional mismatch can be handy, especially when you introduce new features, but in reality it's nothing a nullable column probably wouldn't solve just as well.

For me, the real benefit of dynamic schema is the lack of setup and the reduced friction with OOP. This is particularly true when you're working with a static language. I've worked with MongoDB in both C# and Ruby, and the difference is striking. Ruby's dynamism and its popular ActiveRecord implementations already reduce much of the object-relational impedance mismatch. That isn't to say MongoDB isn't a good match for Ruby, it really is. Rather, I think most Ruby developers would see MongoDB as an incremental improvement, whereas C# or Java developers would see a fundamental shift in how they interact with their data.

Think about it from the perspective of a driver developer. You want to save an object? Serialize it to JSON (technically BSON, but close enough) and send it to MongoDB. There is no property mapping or type mapping. This straightforwardness definitely flows to you, the end developer.

## Writes ##
One area where MongoDB can fit a specialized role is in logging. There are two aspects of MongoDB which make writes quite fast. First, you have an option to send a write command and have it return immediately without waiting for the write to be acknowledged. Secondly, you can control the write behavior with respect to data durability. These settings, in addition to specifying how many servers should get your data before being considered successful, are configurable per-write, giving you a great level of control over write performance and data durability.

In addition to these performance factors, log data is one of those data sets which can often take advantage of schema-less collections. Finally, MongoDB has something called a [capped collection](http://docs.mongodb.org/manual/core/capped-collections/). So far, all of the implicitly created collections we've created are just normal collections. We can create a capped collection by using the `db.createCollection` command and flagging it as capped:

	//limit our capped collection to 1 megabyte
	db.createCollection('logs', {capped: true,
		size: 1048576})

When our capped collection reaches its 1MB limit, old documents are automatically purged. A limit on the number of documents, rather than the size, can be set using `max`. Capped collections have some interesting properties. For example, you can update a document but it can't change in size. The insertion order is preserved, so you don't need to add an extra index to get proper time-based sorting.  You can "tail" a capped collection the way you tail a file in Unix via `tail -f <filename>` which allows you to get new data as it arrives, without having to re-query it.

If you want to "expire" your data based on time rather than overall collection size, you can use [TTL Indexes](http://docs.mongodb.org/manual/tutorial/expire-data/) where TTL stands for "time-to-live".

## Durability ##
Prior to version 1.8, MongoDB did not have single-server durability. That is, a server crash would likely result in lost or corrupt data. The solution had always been to run MongoDB in a multi-server setup (MongoDB supports replication). Journaling was one of the major features added in 1.8. Since version 2.0 MongoDB enables journaling by default, which allows fast recovery of the server in case of a crash or abrupt power loss.

Durability is only mentioned here because a lot has been made around MongoDB's past lack of single-server durability. This'll likely show up in Google searches for some time to come. Information you find about journaling being a missing feature is simply out of date.

## Full Text Search ##
True full text search capability is a recent addition to MongoDB.  It supports fifteen languages with stemming and stop words. With MongoDB's support for arrays and full text search you will only need to look to other solutions if you need a more powerful and full-featured full text search engine.  

## Transactions ##
MongoDB doesn't have transactions. It has two alternatives, one which is great but with limited use, and the other that is cumbersome but flexible.

The first is its many atomic update operations. These are great, so long as they actually address your problem. We already saw some of the simpler ones, like `$inc` and `$set`. There are also commands like `findAndModify` which can update or delete a document and return it atomically.

The second, when atomic operations aren't enough, is to fall back to a two-phase commit. A two-phase commit is to transactions what manual dereferencing is to joins. It's a storage-agnostic solution that you do in code. Two-phase commits are actually quite popular in the relational world as a way to implement transactions across multiple databases. The MongoDB website [has an example](http://docs.mongodb.org/manual/tutorial/perform-two-phase-commits/) illustrating the most typical example (a transfer of funds). The general idea is that you store the state of the transaction within the actual document being updated atomically and go through the init-pending-commit/rollback steps manually.

MongoDB's support for nested documents and flexible schema design makes two-phase commits slightly less painful, but it still isn't a great process, especially when you are just getting started with it.

## Data Processing ##
Before version 2.2 MongoDB relied on MapReduce for most data processing jobs. As of 2.2 it has added a powerful feature called  [aggregation framework or pipeline](http://docs.mongodb.org/manual/core/aggregation-pipeline/), so you'll only need to use MapReduce in rare cases where you need complex functions for aggregations that are not yet supported in the pipeline. In the next chapter we'll look at Aggregation Pipeline and MapReduce in detail. For now you can think of them as feature-rich and different ways to `group by` (which is an understatement).  For parallel processing of very large data, you may need to rely on something else, such as Hadoop. Thankfully, since the two systems really do complement each other, there's a [MongoDB connector for Hadoop](http://docs.mongodb.org/ecosystem/tools/hadoop/).

Of course, parallelizing data processing isn't something relational databases excel at either. There are plans for future versions of MongoDB to be better at handling very large sets of data.

## Geospatial ##
A particularly powerful feature of MongoDB is its support for [geospatial indexes](http://docs.mongodb.org/manual/applications/geospatial-indexes/). This allows you to store either geoJSON or x and y coordinates within documents and then find documents that are `$near` a set of coordinates or `$within` a box or circle. This is a feature best explained via some visual aids, so I invite you to try the [5 minute geospatial interactive tutorial](http://mongly.openmymind.net/geo/index), if you want to learn more.

## Tools and Maturity ##
You probably already know the answer to this, but MongoDB is obviously younger than most relational database systems. This is absolutely something you should consider, though how much it matters depends on what you are doing and how you are doing it. Nevertheless, an honest assessment simply can't ignore the fact that MongoDB is younger and the available tooling around isn't great (although the tooling around a lot of very mature relational databases is pretty horrible too!). As an example, the lack of support for base-10 floating point numbers will obviously be a concern (though not necessarily a show-stopper) for systems dealing with money.

On the positive side, drivers exist for a great many languages, the protocol is modern and simple, and development is happening at blinding speeds. MongoDB is in production at enough companies that concerns about maturity, while valid, are quickly becoming a thing of the past.

## In This Chapter ##
The message from this chapter is that MongoDB, in most cases, can replace a relational database. It's much simpler and straightforward; it's faster and generally imposes fewer restrictions on application developers. The lack of transactions can be a legitimate and serious concern. However, when people ask *where does MongoDB sit with respect to the new data storage landscape?* the answer is simple: **right in the middle**.

# Chapter 6 - Aggregating Data #

## Aggregation Pipeline ##
Aggregation pipeline gives you a way to transform and combine documents in your collection.  You do it by passing the documents through a pipeline that's somewhat analogous to the Unix "pipe" where you send output from one command to another to a third, etc.

The simplest aggregation you are probably already familiar with is the SQL `group by` expression.  We already saw the simple `count()`  method, but what if we want to see how many unicorns are male and how many are female?  

	db.unicorns.aggregate([{$group:{_id:'$gender',
		total: {$sum:1}}}])

In the shell we have the `aggregate` helper which takes an array of pipeline operators.  For a simple count grouped by something, we only need one such operator and it's called `$group`.   This is the exact analog of `GROUP BY` in SQL where we create a new document with `_id` field indicating what field we are grouping by (here it's `gender`) and other fields usually getting assigned results of some aggregation, in this case we `$sum` 1 for each document that matches a particular gender.  You probably noticed that the `_id` field was assigned `'$gender'` and not `'gender'` - the `'$'` before a field name indicates that the value of this field from incoming document will be substituted.

What are some of the other pipeline operators that we can use?  The most common one to use before (and frequently after) `$group` would be `$match` - this is exactly like the `find` method and it allows us to aggregate only a matching subset of our documents, or to exclude some documents from our result.

	db.unicorns.aggregate([{$match: {weight:{$lt:600}}},
		{$group: {_id:'$gender',  total:{$sum:1},
		  avgVamp:{$avg:'$vampires'}}},
		{$sort:{avgVamp:-1}} ])

Here we introduced another pipeline operator `$sort` which does exactly what you would expect, along with it we also get `$skip` and `$limit`.  We also used a `$group` operator `$avg`.

MongoDB arrays are powerful and they don't stop us from being able to aggregate on values that are stored inside of them.  We do need to be able to "flatten" them to properly count everything:

	db.unicorns.aggregate([{$unwind:'$loves'},
     	{$group: {_id:'$loves',  total:{$sum:1},
	 	unicorns:{$addToSet:'$name'}}},
	  	{$sort:{total:-1}},
	  	{$limit:1} ])

Here we will find out which food item is loved by the most unicorns and we will also get the list of names of all the unicorns that love it.  `$sort` and `$limit` in combination allow you to get answers to "top N" types of questions.

There is another powerful pipeline operator called [`$project`](http://docs.mongodb.org/manual/reference/operator/aggregation/project/#pipe._S_project) (analogous to the projection we can specify to `find`) which allows you not just to include certain fields, but to create or calculate new fields based on values in existing fields.  For example, you can use math operators to add together values of several fields before finding out the average, or you can use string operators to create a new field that's a concatenation of some existing fields.

This just barely scratches the surface of what you can do with aggregations.  In 2.6 aggregation got more powerful as the aggregate command returns either a cursor to the result set (which you already know how to work with from Chapter 1) or it can write your results into a new collection using the `$out` pipeline operator.  You can see a lot more examples as well as all of the supported pipeline and expression operators in the [MongoDB manual](http://docs.mongodb.org/manual/core/aggregation-pipeline/).

## MapReduce ##
MapReduce is a two-step approach to data processing. First you map, and then you reduce. The mapping step transforms the inputted documents and emits a key=>value pair (the key and/or value can be complex). Then, key/value pairs are grouped by key, such that values for the same key end up in an array. The reduce gets a key and the array of values emitted for that key, and produces the final result.  The map and reduce functions are written in JavaScript.

With MongoDB we use the `mapReduce` command on a collection. `mapReduce` takes a map function, a reduce function and an output directive. In our shell we can create and pass a JavaScript function. From most libraries you supply a string of your functions (which is a bit ugly). The third parameter sets additional options, for example we could filter, sort and limit the documents that we want analyzed. We can also supply a `finalize` method to be applied to the results after the `reduce` step.

You probably won't need to use MapReduce for most of your aggregations, but if you do, you can read more about it [on my blog](http://openmymind.net/2011/1/20/Understanding-Map-Reduce/) and in [MongoDB manual](http://docs.mongodb.org/manual/core/map-reduce/).

## In This Chapter ##
In this chapter we covered MongoDB's [aggregation capabilities](http://docs.mongodb.org/manual/aggregation/).  Aggregation Pipeline is relatively simple to write once you understand how it's structured and it's a powerful way to group data. MapReduce is more complicated to understand, but its capabilities can be as boundless as any code you can write in JavaScript.

# Chapter 7 - Performance and Tools #
In this last chapter, we look at a few performance topics as well as some of the tools available to MongoDB developers. We won't dive deeply into either topic, but we will examine the most important aspects of each.

## Indexes ##
At the very beginning we saw the `getIndexes` command which shows information on all the indexes in a collection. Indexes in MongoDB work a lot like indexes in a relational database: they help improve query and sorting performance. Indexes are created via `ensureIndex`:

	// where "name" is the field name
	db.unicorns.ensureIndex({name: 1});

And dropped via `dropIndex`:

	db.unicorns.dropIndex({name: 1});

A unique index can be created by supplying a second parameter and setting `unique` to `true`:

	db.unicorns.ensureIndex({name: 1},
		{unique: true});

Indexes can be created on embedded fields (again, using the dot-notation) and on array fields. We can also create compound indexes:

	db.unicorns.ensureIndex({name: 1,
		vampires: -1});

The direction of your index (1 for ascending, -1 for descending) doesn't matter for a single key index, but it can make a difference for compound indexes when you are sorting on more than one indexed field.

The [indexes page](http://docs.mongodb.org/manual/indexes/) has additional information on indexes.

## Explain ##
To see whether or not your queries are using an index, you can use the `explain` method on a cursor:

	db.unicorns.find().explain()

The output tells us that a `BasicCursor` was used (which means non-indexed), that 12 objects were scanned, how long it took, what index, if any, was used as well as a few other pieces of useful information.

If we change our query to use an index, we'll see that a `BtreeCursor` was used, as well as the index used to fulfill the request:

	db.unicorns.find({name: 'Pilot'}).explain()

## Replication ##
MongoDB replication works in some ways similarly to how relational database replication works. All production deployments should be replica sets, which consist of ideally three or more servers that hold the same data.  Writes are sent to a single server, the primary, from where it's asynchronously replicated to every secondary. You can control whether you allow reads to happen on secondaries or not, which can help direct some special queries away from the primary, at the risk of reading slightly stale data. If the primary goes down, one of the secondaries will be automatically elected to be the new primary. Again, MongoDB replication is outside the scope of this book.

## Sharding ##
MongoDB supports auto-sharding. Sharding is an approach to scalability which partitions your data across multiple servers or clusters. A naive implementation might put all of the data for users with a name that starts with A-M on server 1 and the rest on server 2. Thankfully, MongoDB's sharding capabilities far exceed such a simple algorithm. Sharding is a topic well beyond the scope of this book, but you should know that it exists and that you should consider it, should your needs grow beyond a single replica set.

While replication can help performance somewhat (by isolating long running queries to secondaries, and reducing latency for some other types of queries), its main purpose is to provide high availability. Sharding is the primary method for scaling MongoDB clusters. Combining replication with sharding is the perscribed approach to achieve scaling and high availability.

## Stats ##
You can obtain statistics on a database by typing `db.stats()`. Most of the information deals with the size of your database. You can also get statistics on a collection, say `unicorns`, by typing `db.unicorns.stats()`. Most of this information relates to the size of your collection and its indexes.

## Profiler ##
You enable the MongoDB profiler by executing:

	db.setProfilingLevel(2);

With it enabled, we can run a command:

	db.unicorns.find({weight: {$gt: 600}});

And then examine the profiler:

	db.system.profile.find()

The output tells us what was run and when, how many documents were scanned, and how much data was returned.

You disable the profiler by calling `setProfilingLevel` again but changing the parameter to `0`. Specifying `1` as the first parameter will profile queries that take more than 100 milliseconds. 100 milliseconds is the default threshold, you can specify a different minimum time, in milliseconds, with a second parameter:

	//profile anything that takes
	//more than 1 second
	db.setProfilingLevel(1, 1000);

## Backups and Restore ##
Within the MongoDB `bin` folder is a `mongodump` executable. Simply executing `mongodump` will connect to localhost and backup all of your databases to a `dump` subfolder. You can type `mongodump --help` to see additional options. Common options are `--db DBNAME` to back up a specific database and `--collection COLLECTIONNAME` to back up a specific collection. You can then use the `mongorestore` executable, located in the same `bin` folder, to restore a previously made backup. Again, the `--db` and `--collection` can be specified to restore a specific database and/or collection.  `mongodump` and `mongorestore` operate on BSON, which is MongoDB's native format.

For example, to back up our `learn` database to a `backup` folder, we'd execute (this is its own executable which you run in a command/terminal window, not within the mongo shell itself):

	mongodump --db learn --out backup

To restore only the `unicorns` collection, we could then do:

	mongorestore --db learn --collection unicorns \
		backup/learn/unicorns.bson

It's worth pointing out that `mongoexport` and `mongoimport` are two other executables which can be used to export and import data from JSON or CSV. For example, we can get a JSON output by doing:

	mongoexport --db learn --collection unicorns

And a CSV output by doing:

	mongoexport --db learn \
		--collection unicorns \
		--csv --fields name,weight,vampires

Note that `mongoexport` and `mongoimport` cannot always represent your data. Only `mongodump` and `mongorestore` should ever be used for actual backups.  You can read more about [your backup options](http://docs.mongodb.org/manual/core/backups/) in the MongoDB Manual.

## In This Chapter ##
In this chapter we looked at various commands, tools and performance details of using MongoDB. We haven't touched on everything, but we've looked at some of the common ones. Indexing in MongoDB is similar to indexing with relational databases, as are many of the tools. However, with MongoDB, many of these are to the point and simple to use.

# Conclusion #
You should have enough information to start using MongoDB in a real project. There's more to MongoDB than what we've covered, but your next priority should be putting together what we've learned, and getting familiar with the driver you'll be using. The [MongoDB website](http://www.mongodb.org/) has a lot of useful information. The official [MongoDB user group](http://groups.google.com/group/mongodb-user) is a great place to ask questions.

NoSQL was born not only out of necessity, but also out of an interest in trying new approaches. It is an acknowledgment that our field is ever-advancing and that if we don't try, and sometimes fail, we can never succeed. This, I think, is a good way to lead our professional lives.
