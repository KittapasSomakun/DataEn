# **SDLC**

- Software Development Lifecycle (วงจรการพัฒนาซอฟต์แวร์หรือ SDLC) คือกระบวนการที่คุ้มค่าและประหยัดเวลาในการออกแบบและสร้างซอฟต์แวร์คุณภาพสูงสำหรับทีมพัฒนา 
เป้าหมายของ SDLC คือการลดความเสี่ยงของโปรเจกต์ด้วยการวางแผนล่วงหน้า เพื่อให้ซอฟต์แวร์ตอบสนองตามความคาดหวังของลูกค้าในระหว่างการใช้งานจริงและหลังจากนั้น 
ระเบียบวิธีการนี้จะแสดงชุดขั้นตอนที่แบ่งกระบวนการพัฒนาซอฟต์แวร์ออกเป็นงานที่คุณสามารถมอบหมาย ดำเนินการ และวัดผลได้

## Agile
- การทำซ้ำและรับ feedback

## Waterfall
- ทำตามลำดับขั้นตอน
--- 
# **Data warehouse**

- Data Warehouse หรือคลังข้อมูล เป็นระบบที่ออกแบบมาเพื่อเก็บรวบรวมข้อมูลจากหลายแหล่งต่าง ๆ ในองค์กร แล้วจัดเก็บข้อมูลนี้ในรูปแบบที่เข้าใจง่ายและเหมาะสมสำหรับการวิเคราะห์และรายงาน คลังข้อมูลนี้ทำให้ข้อมูลสา มารถเข้าถึงได้อย่างสะดวกและมีความครบถ้วน โดยสร้างฐานข้อมูลใหญ่ที่เรียกว่า Data Warehouse ซึ่งเป็นสถานที่ที่ข้อมูลทั้งหมดถูกรวบรวมเข้าด้วยกัน แล้วองค์กรสามารถนำข้อมูลที่ถูกเก็บรวบรวมจาก Data Warehouse มาใช้ได้อย่างครบถ้วนและรวดเร็ว

- ETL คือ etract , transform , load

![Data_warehouse_1](https://d3i71xaburhd42.cloudfront.net/4f12317e591342f4cd7f7a4858bebf2dc257c854/4-Table1-1.png)

![Data_warehouse_2](https://panoply.io/uploads/versions/diagram8-1---x----750-376x---.jpg)

--- 
# **SQL**

## CRUD คืออะไร
- C(Create) สร้างหรือเพิ่มรายการใหม่
- R(Read) อ่านดึงค้นหาหรือดูรายการที่มีอยู่
- U(Update) อัปเดตหรือแก้ไขรายการที่มีอยู่
- D(Delete) ลบปิดใช้งานหรือลบรายการที่มีอยู่

## SQL ( Structured Query Language )
- C (Create) = CREATE, INSERT
- R (Read) = SELECT
- U (Update) = UPDATE
- D (Delete) = DELETE

## INSERT

```sql
INSERT INTO table_name
VALUES (value1, value2, value3, ...);
```


## SELECT
```sql
SELECT * FROM table WHERE condition;
```

## UPDATE
```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

## DELETE
```sql
DELETE FROM table_name WHERE condition;
```


## Subquery [ต้องการ query หลายรอบ]
```sql
SELECT ...
FROM ( SELECT ...
       FROM ...)
```

## JOIN [เชื่อม table กลับไปเป็น NF หรือ ความสัมพันธ์ใน table]
```sql
SELECT tbl1.col1, tbl2.col2...
FROM tbl1
LEFT JOIN tbl2
ON tbl1.field_name = tbl2.field_name;
```

## GROUP BY [รวบข้อมูลเข้าด้วยกัน]
```sql
SELECT column1, column2
FROM table_name
WHERE [ conditions ]
GROUP BY column1, column2
ORDER BY column1, column2;
```

## Complier test mysql online
https://onecompiler.com/mysql

## CheatSheet
![SQL CheatSheet](https://preview.redd.it/hf2y9e6r36s71.jpg?width=1080&crop=smart&auto=webp&s=d2961feaab08f247d1fef9b06b174589ae79ce21)

--- 

# Normalization
- การทำ Normalization จะต้องทำเป็นขั้นตอน โดยเริ่มจาก Unnormalized Form หรือ ข้อมูลดั้งเดิม > 1NF > 2NF > 3NF > BCNF > 4NF > 5NF 
จนได้รูปแบบของ Higher normal forms โดยที่ห้ามข้ามขั้นตอน ถ้าไม่อยู่ในรูปแบบก่อนหน้า เช่น ถ้าไม่อยู่ในรูปของ 1NF จะข้ามไปทำ 3NF เลยไม่ได้

- 1NF เป็นขั้นตอนการปรับปรุง ค่าที่ซ้ำกันให้แยกกัน [กระจายข้อมูลซ้ำกันออกมา]
- 2NF เป็นขั้นตอนที่ใช้กำจัด Partial Dependency [แยกให้เป็นตาราง relational]
- 3NF เป็นขั้นตอนที่ใช้กำจัด Transitive Dependency [แยกตารางของ 2NF ให้แยกออกมาอีก]
- BCNF เป็นขั้นตอนที่ใช้กำจัด Candidate Key
- 4NF เป็นขั้นตอนที่ใช้กำจัด Mutivalued Dependency
- 5NF จะเป็นการ Join Dependency แล้ว ได้ตารางที่เหมือนเดิม
  
Ref : https://miwtoo.medium.com/%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B8%97%E0%B8%B3-normalization-%E0%B9%80%E0%B8%9E%E0%B8%B7%E0%B9%88%E0%B8%AD%E0%B8%9B%E0%B8%A3%E0%B8%B1%E0%B8%9A%E0%B8%9B%E0%B8%A3%E0%B8%B8%E0%B8%87-schema-d0324b6c9556


--- 

# ER diagram

- Entity
entity แทนที่ สิ่ง ซึ่งอาจจะเป็นทั้งคน วัตถุ สิ่งของ หรือสิ่งซึ่งเป็นนามธรรมจับต้องไม่ได้ ใช้แทนที่สิ่งในโลกความเป็นจริงแต่ละ entity แทนที่ด้วยชื่อของ entity ในรูปสี่เหลี่ยมผืนผ้า

- Attribute
attributes ใช้แสดงถึงคุณสมบัติของ entity เช่น ชื่อ นามสกุล  เลขประจำตัว  ที่อยู่ ฯลฯ แทนที่ด้วยชื่อของ attribute ในรูปวงรี

![ER_diagram_1](https://msit5.files.wordpress.com/2013/09/e-r1.jpg)

- Key attribute
คือ attribute ที่ถูกกำหนดให้เป็น key ของ entity โดยแทนที่ด้วย attribute ที่ถูกขีดเส้นใต้ จากในภาพ account Id ถูกขีดเส้นใต้เพื่อแสดงว่า attribute นี้ถูกใช้เป็น key ของ entity Customer

- Multi-valued attribute
คือ attribute ที่มีค่าบรรจุอยู่มากกว่าหนึ่งค่า โดยแทนที่ด้วยวงกลมรูปไข่ซ้อนกันสองวง จากในภาพ attribute ที่ชื่อ otherUsers เป็น multi-valued attribute หมายถึง Customer สามารถมีผู้ใช้คนอื่น ๆ ที่ใช้บัญชีของ Customer ได้ (ผู้ใช้คนอื่นอาจจะเป็นญาติกับ Customer เช่น ลูก, ภรรยา, น้อง)

- Derived attribute
คือ attribute ที่ค่าของมันได้มาจากการคำนวณของ attribute อื่น โดยแทนที่ด้วยวงกลมรูปไข่ที่เป็นเส้นประ  จากในภาพ attribute ที่ชื่อ numberRentals หรือจำนวนที่เช่าซึ่งได้มาจากการรวมจำนวนสินค้าที่เช่าทั้งหมดเข้าด้วยกัน

- Composite attribute
คือ attribute ที่สามารถแยกออกเป็น attribute ย่อย ๆ ได้หลาย attribute แทนที่โดยชื่อ attribute ใน วงกลมรูปไข่ที่มีเส้นตรงลากไปเชื่อมโยงกับ attribute หลัก จากในภาพ attribute ที่ชื่อ address สามารถแยกออกเป็น attribute ย่อยที่ชื่อ street, city, state, zipcode  ได้อีก

- Relationship Types
ใช้แสดงความสัมพันธ์ระหว่าง entity โดยแทนที่ด้วยรูปสี่เหลี่ยมข้าวหลามตัด ดังในภาพข้างล่าง Store  Owns (เป็นเจ้าของ)  Video (ในกรณีที่อ่านจากซ้ายไปขวา) หรือ Video IsOwnedBy (ถูกเป็นเจ้าของโดย) Store (ในกรณีที่อ่านจากขวาไปซ้าย)  พึงสังเกตุว่าชื่อของ relationship types จะต้องเป็นคำกริยาเสมอ  และความสัมพันธ์สามารถมี attribute ของตัวเองได้ เช่นในภาพ ความสัมพันธ์ Owns มี attribute คือ purchase Date และ cost

![ER_diagram_2](https://msit5.files.wordpress.com/2013/09/e-r2.jpg)

## Cardinality ratio
ใช้แสดงถึงอัตราส่วนของความสัมพันธ์ แทนที่ด้วยตัวเลข 1, M และ N
- 1 :  1        แทนความสัมพันธ์แบบหนึ่งต่อหนึ่ง
- 1 :  N        แทนความสัมพันธ์แบบหนึ่งต่อหลาย
- M : N        แทนความสัมพันธ์แบบหลายต่อหลาย

## Participation
- ใช้แสดงการมีส่วนร่วมในความสัมพันธ์ของสมาชิกใน entity แทนที่ด้วยเส้นตรงหรือเส้นคู่
total  (เส้นคู่)           ทุก ๆ สมาชิกที่อยู่ใน entity จะต้องอยู่ในความสัมพันธ์ทั้งหมด
partial  (เส้นเดี่ยว)      บางส่วนของสมาชิกที่อยู่ใน entity เท่านั้นที่อยู่ในความสัมพันธ์






