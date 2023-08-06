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
การสร้างและเพิ่มขเ้อมูลรายละเอียดใน details.html
<<<<<<< HEAD
```shell      
> {% for student in students  %}
=======
 {% for student in students  %}
>>>>>>> b0f636cbba6f14d62283ec809b0bda1090efb664
      <tr>
        <th scope="row">1</th>
        <td>{{ student.std_id }}</td>
        <td>{{ student.prefix }}</td>
        <td>{{ student.name }}</td>
        <td>{{ student.lastname }}</td>
        <td>{{ student.phone }}</td>
        <td>{{ student.address }}</td>
        <td>{{ student.major }}</td>       
      </tr>
      {% endfor %}
<<<<<<< HEAD
```
      
การเพิ่ม class Major(models.Model) ใน models.py
```shell 
> class Major(models.Model):
=======
การเพิ่ม class Major(models.Model) models.py
class Major(models.Model):
>>>>>>> b0f636cbba6f14d62283ec809b0bda1090efb664

    name = models.CharField(max_length=255)

    class Meta:
        verbose_name = "Major"
        verbose_name_plural = "Majors"

    def __str__(self):
        return self.name
<<<<<<< HEAD
```
การเพิ่ม  studentDetails ใน views.py
```shell 
> def studentDetails(request, id) :
=======
การเพิ่ม  studentDetails ใน views.py
def studentDetails(request, id) :
>>>>>>> b0f636cbba6f14d62283ec809b0bda1090efb664
    context = {}
    students = models.Student.objects.filter(id=id)
    for student in students:
        student.prefix_str = getModelChoice(
            student.prefix, models.prefix_choices)
        
        context['student'] = student
        
    return render(request,"details.html",context)

def getModelChoice(num, choices) :
    for choice in choices:
            if choice[0] == num:
                return choice[1]
<<<<<<< HEAD
```            
การเพิ่มรายการใน admin.py
```shell 
> from django.contrib import admin
=======
การเพิ่มรายการใน admin.py
from django.contrib import admin
>>>>>>> b0f636cbba6f14d62283ec809b0bda1090efb664

# Register your models here.

from .models import Student, Major

@admin.register(Student)
class Admin(admin.ModelAdmin):
    list_display = ("std_id","name","prefix","lastname","phone","major")
    search_fields = ("std_id","name","prefix","lastname","phone","major")
    
@admin.register(Major)
class MajorAdmin(admin.ModelAdmin):
    list_display = ('name', )
<<<<<<< HEAD
```
=======
>>>>>>> b0f636cbba6f14d62283ec809b0bda1090efb664
