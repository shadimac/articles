# :construction: ورشة عمل (3) توزيع الكود على Classes وتطبيق OOP

#  خطة الورشات

### [ خطة ورشات العمل](https://macdiscussions.udacity.com/t/topic/177463?u=shadikahwaji)

# :computer_mouse: شرح برنامج الورشة: 

كما تعلم أن مطور الويب الشامل يكون مسؤول عن كافة أجزاء البرنامج، في هذه الورشة سنقوم بالعمل على الجزء الوسطي Backend Coding الذي يختص بقوانين البرنامج وكيف يعمل، لاحقاً في ورشات أخرى سنتطرق إلى آلية العرض Front-End Coding وآلية تخزين المعلومات .Database 

# تلخيص للورشات السابقة:
قمنا بالورشات السابقة التالية لحد الأن:
•	[ورشة عمل (1) : بناء نظام بسيط لحجز الفنادق](https://macdiscussions.udacity.com/t/1-lists-and-loops/177446?u=shadikahwaji)
•	[ورشة عمل (2) :إضافة إمكانية تأكيد الحجز عن طريق الرسائل](https://macdiscussions.udacity.com/t/2-twilio/187598?u=shadikahwaji)

# :page_with_curl: ملف البرنامج:
إلى الأن لدينا ملف واحد للبرنامج ألا وهو reservation.py، وفي هذه الورشة سنقوم بتوزيع عملنا على أكثر من ملف

# :wrench:البدء بالعمل على البرنامج:

في هذه الورشة سنقوم فقط بترتيب برنامجنا على شكل classes بحيث يصبح أسهل للمتابعة والتعديل في المستقبل.

### ما هو ال class؟
[لنتعرف أولا على ال class من خلال هذا المقال.](https://macdiscussions.udacity.com/t/classes/173884?u=shadikahwaji)

### ما هي الوحدات Entities؟
بعد أن تعرفنا علي ال class لنعود مرة ثانية لمشروعنا ألا وهو حجز الفنادق، كيف يمكن توزيع الكود على ال classes؟ طبعا لا توجد طريقة واحدة وصحيحة إنما يمكننا أن نتبع أفضل الممارسات لفعل ذلك.

يجب أن نبحث عن الكيان **Entity**، وهو أي شيء مستقل بحد ذاته له صفات attributes وتجري عليه عمليات  operations. ومن خلال قراءتنا للورشات السابقة نجد أن التعابير التالية قد تشكل كيان مستقلا:

•	فندق
•	عميل
•	حجز

ولكن ما رأيك بإرسال الرسائل النصية؟ حقيقة ذلك بحد ذاته قد لا يشكّل كيان منفصل ولكن لو فكرنا به على أنه تابع للتنبيهات notifications يمكننا أن نضمه لوحدة تدعى تنبيهات لأننا نعتقد أننا في المستقبل قد نضيف تنبه بالبريد الإلكتروني أو أي طريقة أخرى، فكلها تنضم في class واحد يدعى تنبهات.

ولكن هناك شيء لا ينطبق عليه مبدأ الكيان ومع ذلك يمكننا أن نخصص له class لوحده وهو أيضا غير مذكور في جمل الورشات السابقة وهو دوال فحص الكود tester.

### توزع الكود على أكثر من ملف:
حسنا بعد أن عرفنا من يمكنه أن يتحول إلى class يمكننا الأن أن نستخدم أكثر من ملف لهذه ال classes بحيث يأخذ كل class ملف منفصل يحمل فقط كل ما يتعلق بذلك ال class.
### ملف hotel.py:

هنا سنبدأ بتعريف class Hotel وكافة المتغيرات والعمليات المتعلقة به من إضافة وحذف وبحث. 

### ملف customer.py:

هنا سنبدأ بتعريف class Customer وكافة المتغيرات والعمليات المتعلقة به من إضافة وحذف وبحث. 

### ملف reservation.py:

هنا سنبدأ بتعريف class Reservation وكافة المتغيرات والعمليات المتعلقة به من إضافة وحذف وبحث.

### ملف notification.py:

هنا سنبدأ بتعريف class Notification وكافة الدوال الخاصة بالتنبيهات. 

### ملف tester.py:

هنا سنبدأ بتعريف class Tester وكافة الدوال الخاصة بفحص الكود. 

لاحظ أننا استعملنا الحرف الكبير في بداية ال class والاسم المفرد لتلك ال classes فلم نقل Hotels ولكن قلنا Hotel وذلك من ضمن أفضل الممارسات.
 
### ملف main.py:

ماذا عن ملف المشروع الرئيسي، يمكننا أن نسميه main.py أو أي اسم أخر، ومن خلاله يمكننا أن نشمل بقية الملفات عن طريق أمر import.

    “””
        main.py
        This is the main application file for the Hotel Reservation system 
    “””    
    import hotel # when you import you will use the file name not the class name
    import customer
    import reservation
    import tester
    import notification

كل الملفات يجب أن تكون موجودة على نفس الفولدر لتتعرف على بعضها البعض.

# تطبيق الورشة

حسنا تعرفنا الأن على ما يمكن أن يكون كيانات منفصلة entities قد تفيدنا في توزيع الكود على classes وتعرفنا على ماهية هذه ال classes والملفات التي تحتويها، علينا الأن فقط أن نقوم بتوزيع الكود الذي تمت كتابته في الورش السابقة على هذه الملفات وال classes بحيث لا يتأثر تنفيذ البرنامج.

لنأخذ مثال الفندق وسأترك البقية لكم:

    “””
    hotel.py
    This is the Hotel class file 
    “””    

    class Hotel():
        hotels = []
        def __init__(self, number,hotel_name, city,total_rooms,empty_rooms):
            self.number = number
            self.hotel_name = hotel_name
            self.city = city
            self.total_rooms = total_rooms
            self.empty_rooms = empty_rooms

            Hotel.hotels.append([self.number , self.hotel_name, self.city, self.total_rooms 
            self.empty_rooms])

        def list_hotels_in_city(self, city):
            # search inside Hotel.hotels for hotels in a ‘city’

ملف البرنامج الرئيسي:

    “””
        main.py
        This is the main application file for the Hotel Reservation system 
    “””    
    import hotel

    def start_app():
        rotana_hotel = Hotel(20,”Rotana”,”Abu Dhabi”,200,40)
        sheraton_hotel = Hotel(21,”Sheraton”,”Abu Dhabi”,300,100)

        print Hotel.hotels
        
    start_app()

هناك ملاحظة أريدك أن تنتبه لها وهي الفرق بين class variable و instance variable:

### ال class variable: 
هو متغيّر يتبع ال class على مستوى كافة ال objects التي ستنشأ من هذا ال class، لذلك قمت بتعريف القائمة hotels على مستوى ال class لكي أحتفظ بمعلومات كل الفنادق، هذا لا ينصح به ولكننا لم نتعرف على قواعد البيانات بعد لذلك سنقوم بهذه الحركة مؤقتا.

### ال instance or object variable: 
وهي المتغيرات التي تخص كل نسخة من هذا ال class أي تخص كل فندق لوحده وتم تعريفها داخل الدالة الإبتدائية `__init__`. 

### نصيحة: 
أعرف أنا الموضوع قد يبدو جديدا وبه بعض الإشكالات ولكنني هنا للمساعدة وإذا لم تطبق تلك المعرفة على أرض الواقع فلن تتعلم بالطريقة الصحيحة. إسأل كل الأسئلة التي تخطر ببالك وسأكون معك خطوة خطوة حتى تنفذ هذه الورشة والمشروع بأكمله إن شاء الله :smile: 

# الوقت المقترح الورشة
خلال ٢٤ ساعة من استلام الورشة

### أتمنى التوفيق للجميع من كل :heart: :blush:

****
### لم نتعرف على GitHub بعد لذلك يرجى مشاركة الكود من خلال رابط لسهولة متابعته والتعليق عليه من خلال رفع ملف بايثون على Google Drive أو OneDrive. فيما يلي 

#### [شرح طريقة رفع الكود على كل من Google Drive و OneDrive.](https://youtu.be/ntWFCGlXNlE)
****