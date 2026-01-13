نظام إدارة المواعيد الذكي

Appointment Smart System

 نبذة عن المشروع:

نظام إدارة المواعيد الذكي هو تطبيق خلفي (Backend) مبني باستخدام Spring Boot، يهدف إلى تنظيم وحجز المواعيد بشكل آمن ومرن، مع دعم أدوار متعددة للمستخدمين ومنع تعارض المواعيد، إضافةً إلى نظام أمان متكامل يعتمد على JWT و HTTPS.

المشروع مطوّر على ثلاث مراحل (Core Backend – Security – Advanced Features) ويحقق جميع المتطلبات الأكاديمية المطلوبة.

مراحل تنفيذ المشروع:

المرحلة الأولى: Core Backend

إنشاء مشروع Spring Boot

تصميم قاعدة البيانات (Users – Services – Appointments)

تنفيذ RESTful APIs  كامل للمستخدمين والخدمات والمواعيد CRUD
 

تطبيق منطق الأعمال:

منع حجز مواعيد متداخلة

التحقق من صحة التواريخ والأوقات

إدارة حالات الموعد

اختبار جميع الواجهات باستخدام Postman

المرحلة الثانية: الأمان (Security)

تسجيل الدخول والمصادقة باستخدام JWT

التحكم بالصلاحيات حسب الدور (Role-Based Authorization)

تشفير كلمات المرور باستخدام BCrypt

تفعيل Spring Security

تفعيل الاتصال الآمن باستخدام HTTPS (SSL)

المرحلة الثالثة: الميزات المتقدمة

إرسال الإشعارات عند إنشاء أو تعديل حالة الموعد

ربط الإشعارات بمنطق الأعمال

اختبار الأداء والضغط (Stress Testing)

التأكد من استقرار النظام تحت ضغط عالٍ

أدوار المستخدمين
الدور	الصلاحيات
ADMIN	إدارة النظام، المستخدمين، والخدمات
STAFF	الاطلاع على المواعيد المخصصة له
CUSTOMER	إنشاء حساب، حجز، تعديل، وإلغاء المواعيد
الأمان (Security):

JWT Authentication

Role-Based Authorization

BCrypt Password Encoding

JWT Filter

HTTPS (SSL Enabled)

جميع الواجهات محمية باستثناء واجهات المصادقة

التقنيات المستخدمة:

Java 17

Spring Boot 3

Spring Security

Spring Data JPA

Hibernate

H2 Database

JWT (io.jsonwebtoken)

Maven

كيفية تشغيل المشروع:
المتطلبات

Java 17

Maven

Postman لاختبار الـ APIs

الإعدادات:

المنفذ الافتراضي: 8443

قاعدة البيانات: H2

SSL مفعّل

تشغيل التطبيق:
mvn spring-boot:run


سيعمل المشروع على:

https://localhost:8443

آلية المصادقة:

إنشاء مستخدم (Register أو Admin)

تسجيل الدخول

الحصول على JWT Token

تمرير التوكن في الهيدر:

Authorization: Bearer <JWT_TOKEN>

واجهات الـ API (أمثلة):
المصادقة:

Register

POST https://localhost:8443/api/auth/register

{
  "fullName": "Rama User",
  "email": "rama@gmail.com",
  "password": "123456"
}


Login

POST https://localhost:8443/api/auth/login

الخدمات:

إضافة خدمة:

POST https://localhost:8443/api/services

{
  "name": "Medical Consultation",
  "durationMinutes": 30,
  "price": 100
}

المواعيد:

إضافة موعد:

POST https://localhost:8443/api/appointments

{
  "clientName": "Amal",
  "serviceId": 1,
  "date": "2026-02-02",
  "startTime": "05:30",
  "endTime": "06:30"
}


تغيير حالة موعد:

PUT https://localhost:8443/api/appointments/{id}/status

{
  "status": "CONFIRMED"
}

المستخدمين:

إضافة مستخدم:

POST https://localhost:8443/api/users

{
  "email": "masa@gmail.com",
  "fullName": "Masa",
  "password": "12345678",
  "role": "STAFF"
}
تقسيم العمل بين أعضاء الفريق:

تم تنفيذ هذا المشروع بشكل جماعي.



ملاحظات ختامية:

المشروع يحقق جميع المتطلبات الأكاديمية

منطق منع التعارض يعمل بدقة

النظام مستقر تحت الضغط

زمن الاستجابة ممتاز حتى مع عدد كبير من الطلبات

التصميم نظيف وقابل للتوسع

جميع كلمات المرور مشفرة

الاتصال يتم عبر HTTPS فقط
