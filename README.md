# การนำโปรเจค My Web Application ขึ้นไปบนrepmote repo บน github



ความรู้ที่ได้รับ

การโคลนโปรเจ็คเริ่มต้นมาใส่ใน Repository โดยการเซ็ต Remote ใหม่โดยใช้คำสั่งโค๊ดว่า **git clone** 
```shell
> git clone <url>
```
การใช้คำสั่งเปลี่ยนชื่อไฟล์
```shell
> rename-item Project2565 Project2566
```
การเซ็ต remote repository ภายใต้คำสั่ง **git remote set-url origin**
```shell
> git remote set-url origin <url>
```
การเช็คสถานะว่า remote ไปที่ repository ไหนภายใต้คำสั่งโค๊ด **git remote -v**
```shell
> git remote -v
```
การสร้างตาราง และ การใช้ prefix chouces
```shell
        > prefix_choices =(
            (1,"นาย"),
            (2,"นางสาว"),
            (3,"นาง"),
        )
        
        class Student(models.Model):
            std_id =    models.IntegerField()
            prefix = models.IntegerField(choices=prefix_choices,    default=1)
            name=       models.CharField(max_length=255)
            lastname=   models.CharField(max_length=255)
            phone =     models.CharField(max_length=255)
            address=    models.TextField()
            
        
            class Meta:
                verbose_name = 'student'
                verbose_name_plural = 'student'
        
            def __str__(self):
                return self.name + " " + self.lastname
        
```
