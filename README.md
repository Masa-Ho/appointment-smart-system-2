نظام إدارة المواعيد الذكي

Appointment Smart System

نبذة عن المشروع

نظام إدارة المواعيد الذكي هو تطبيق خلفي (Backend) مبني باستخدام Spring Boot يهدف إلى تنظيم وحجز المواعيد بشكل آمن ومرن مع دعم أدوار مختلفة للمستخدمين.
يدعم النظام:

إدارة المستخدمين بأدوار متعددة

تسجيل الدخول باستخدام JWT

التحكم بالصلاحيات حسب الدور

إدارة الخدمات والمواعيد

الاتصال الآمن باستخدام HTTPS (SSL)


أدوار المستخدمين

ADMINإدارة النظام، المستخدمين، والخدمات
STAFFالاطلاع على المواعيد المخصصة له
CUSTOMERتسجيل الحساب، حجز وتعديل وإلغاء المواعيد

الأمان (Security)

المصادقة باستخدام JWT

التحكم بالصلاحيات حسب الدور (Role-Based Authorization)

تشفير كلمات المرور باستخدام BCrypt

فلتر JWT 

الاتصال الآمن عبر HTTPS (SSL)

التقنيات المستخدمة

Java 17

Spring Boot 3

Spring Security

Spring Data JPA

Hibernate

H2 Database

JWT (io.jsonwebtoken)

Maven

كيفية تشغيل المشروع

١. المتطلبات

Java 17 

Maven

Postman لاختبار الـ APIs


٢. الإعدادات

المنفذ الافتراضي: 8443

قاعدة البيانات: H2

SSL مفعل


٣.  تشغيل التطبيق

mvn spring-boot:run 
سيعمل المشروع على:
https://localhost:8443 

آلية المصادقة

إنشاء مستخدم (Register أو Admin)

تسجيل الدخول

الحصول على JWT Token

تمرير التوكن في الهيدر:

Authorization: Bearer <JWT_TOKEN> 


واجهات الـ API

المصادقة (Authentication)

تسجيل دخول جديد

https://localhost:8443/api/auth/register

مثال:
{
  "fullName": "rama User",
  "email": "rama@gmail.com",
  "password": "123456"
}

تسجيل الدخول

https://localhost:8443/api/auth/login

مثال:
{
  "email": "admin@gmail.com",
  "password": "admin123"
}

إضافة موعد
https://localhost:8443/api/appointments
مثال:
{
  "clientName": "Amal",
  "serviceId": 1,
  "date": "2026-02-02",
  "startTime": "05:30",
  "endTime": "06:30"
}

إضافة خدمة
https://localhost:8443/api/services
مثال:
{
  "name": "Medical Consultation",
  "durationMinutes": 30,
  "price": "100",
}

تغيير حالة موعد
https://localhost:8443/api/appointments/رقم الموعد/status


{
  "status": "CONFIRMED"
}

إضافة مستخدمhttps://localhost:8443/api/users
{
  "email": "Masa@gm.com",
  "fullName": "Masa",
  "password": "12345678",
  "role": "STAFF"
}


ملاحظات

المشروع يحقق جميع المتطلبات الأكاديمية:

منطق أعمال صحيح

أمان كامل

إشعارات

اختبار أداء ناجح

تصميم نظيف وقابل للتوسع

اختبار الأداء أثبت أن النظام قادر على التعامل مع ضغط حقيقي مشابه للبيئة الإنتاجية، وأن منطق منع التعارض يعمل بشكل صحيح، وأن البنية العامة للنظام مستقرة وسريعة

قادر على معالجة عدد كبير من الطلبات بدون انهيار

يحافظ على زمن استجابة ممتاز حتى تحت الضغط

لا يعاني من مشاكل في منطق الأعمال أو قاعدة البيانات

جميع الواجهات محمية باستثناء واجهات المصادقة

كلمات المرور مشفرة بالكامل

الاتصال يتم عبر HTTPS فقط
