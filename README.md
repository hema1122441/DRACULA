# **🧛 DRACULA (Direct Response & Automated Customer Utility Language Architecture)**

**Principal Architect:** Ibrahim El Feqi (hema1122441)  
**Licensing Agreement:** MIT License (Open-Source Academic & Commercial Grant)  
**Technical Stack:** Python (Version 3.10 or higher) | FastAPI Framework | Ollama (Local Small Language Model Inference) | Meta Graph API Integration

---

## **🌍 Language Specification / تحديد اللغة**

## 🌍 Language / اللغة
* [English Version](#english)
* [النسخة العربية](#arabic)

---
<a name="english"></a>
## **🇺🇸 Technical Specifications & Documentation (English)**

DRACULA is an enterprise-grade, fully localized digital sales automation engine engineered for execution within restricted local hardware environments. Utilizing the official Meta Webhook Architecture, the system establishes direct, real-time integration with Facebook Messenger, Instagram Direct Message (DM), and the WhatsApp Business Cloud API, thereby facilitating microsecond response latencies while preserving absolute digital data sovereignty.

### **🎯 Engineering & Operational Philosophy**

* **Mitigating Latency-Induced Revenue Attrition:** Empirical data within the electronic commerce sector indicates that consumer conversion rates decay by approximately sixty percent (![][image1]) should response latency exceed a five-minute threshold. The architecture described herein mitigates this systemic vulnerability through instantaneous automated query resolution.  
* **Structural Memory Integrity and Account Security:** The software design completely eschews browser-based extensions and Document Object Model (DOM) scraping mechanisms, thereby preventing memory saturation, associated hardware failure, and platform-level account suspensions.  
* **Hardware Optimization for Constrained Environments:** The system is optimized to perform high-throughput local inference on standard developer hardware—specifically evaluated on a Core i5 processor and an 8GB RAM memory configuration—by reserving system memory strictly for Small Language Models (SLMs).

### **🛠 System Architecture & Data Flow**

```text
\[ Client Interface: Facebook / Instagram / WhatsApp \]  
                       │  
                       ▼  (Meta Official Webhook \- HTTP POST JSON)  
             \[ Secure Reverse Proxy / Ngrok \]  
                       │  
                       ▼  
         \[ DRACULA Engine (FastAPI Async) \]  
                       │  
                       ├─► 1\. Payload sanitization & strict Thread-ID session isolation.  
                       ├─► 2\. Memory truncation via sliding window (Retaining last 4 messages).  
                       └─► 3\. Context payload dispatch to local Ollama inference server.  
                       │  
                       ▼  
       \[ Local Ollama Instance \] ◄──► \[ SLM Model: qwen2.5-coder:1.5b \]
```
### **🧠 Core Architectural Features**

* **Unified Omnichannel Deserialization Routing:** A singular asynchronous endpoint engineered to ingest, deserialize, and process structured payloads originating from disparate Meta communication APIs within a unified processing pipeline.  
* **Deterministic Inference Constraints:** To prevent algorithmic hallucination and ensure strict alignment with predefined local product inventories and pricing schedules, the model's hyperparameter boundaries are constrained to a rigid temperature setting of 0.3.  
* **Localized Linguistic Synthesis:** The language generation layer is structurally aligned to synthesize highly formal yet accessible Egyptian Arabic, systematically guiding the user toward the submission of essential contact metadata to secure commercial conversion.

### **🚀 Deployment Protocol**

1. **Model Acquisition:**  
   Ensure the local model is pulled via the command-line interface:  
    ```bash
    ollama pull qwen2.5-coder:1.5b

2. **Dependency Installation:**  
   Initialize the isolated virtual environment and install the required asynchronous libraries:  
    ```bash
   pip install fastapi uvicorn httpx

4. **Tunnel Configuration:**  
   Expose the local server port via a secure tunneling protocol to satisfy the HTTPS requirement imposed by Meta:  
   ```bash
   ngrok http 8000

6. **Application Execution:**  
   Execute the primary server process utilizing the Uvicorn ASGI server:  
  ```bash
   python main.py
```
<a name="arabic"></a>
## **🇪🇬 وثيقة المواصفات الفنية والتشغيلية (العربية)**

يمثل مشروع DRACULA محركاً برمجياً متقدماً لأتمتة العمليات البيعية الرقمية بمستوى المؤسسات، وقد صُمّم خصيصاً للتنفيذ المحلي الشامل (100% Local Deployment) دون الاعتماد على البنى التحتية السحابية الخارجية لضمان السيادة المطلقة على البيانات. يعتمد النظام على معمارية الويب هوك الرسمية (Official Webhook Architecture) للربط المباشر مع منصات Meta (Facebook Messenger, Instagram DMs, WhatsApp Cloud API)، مما يضمن استجابة فورية فائقة السرعة مع حماية البيانات الحساسة للشركات.

### **🎯 الفلسفة الهندسية والتشغيلية**

* **معالجة الفقد المالي الناجم عن فترات الانتظار:** تشير التحليلات الإحصائية في قطاع التجارة الإلكترونية إلى تراجع معدلات التحويل بنسبة تقارب الستين بالمائة (![][image1]) في حال تجاوز زمن الاستجابة عتبة الخمس دقائق. ويعمل هذا النظام على سد هذه الثغرة التشغيلية عبر الاستجابة الفورية واللحظية للطلبات المستلمة.  
* **ضمان استقرار سلامة الذاكرة وأمن الحسابات:** يتجنب التصميم البرمجي بالكامل استخدام إضافات المتصفح وهندسة كشط بيانات واجهة المستخدم (DOM Scraping) الهشة، مما يمنع تسريب الذاكرة العشوائية ويحد من مخاطر حظر الحسابات التجارية من قبل المنصات المزودة.  
* **أمثلة استهلاك الموارد في البيئات العتادية المحدودة:** تم تصميم النظام ليعمل بكفاءة عالية على أجهزة التطوير القياسية والخوادم المحلية ذات الموارد المحدودة (حيث تم اختباره بنجاح على معالج Core i5 وذاكرة عشوائية بسعة 8 جيجابايت) عن طريق عزل ذاكرة الاستنتاج وتخصيصها بالكامل للنماذج اللغوية الصغيرة (SLMs).

### **🛠 المعمارية التقنية وتدفق البيانات**

```text

\[ واجهة العميل: فيسبوك / إنستجرام / واتساب \]  
                       │  
                       ▼  (Meta Official Webhook \- HTTP POST JSON)  
             \[ نفق اتصالات آمن / Ngrok \]  
                       │  
                       ▼  
       \[ محرك DRACULA (FastAPI Async) \]  
                       │  
                       ├─► 1\. تنظيف البيانات المستلمة وعزل الجلسات بناءً على معرّف Thread-ID الفريد.  
                       ├─► 2\. تقليص ذاكرة المحادثة عبر نافذة منزلقة تحتفظ بآخر 4 رسائل فقط لمنع التشتت.  
                       └─► 3\. تمرير السياق المنظم إلى واجهة استنتاج Ollama المحلية.  
                       │  
                       ▼  
         \[ خادم Ollama المحلي \] ◄──► \[ النموذج اللغوي: qwen2.5-coder:1.5b \]
```
### **🧠 المميزات الهندسية للنظام**

* **موجّه البيانات الموحد (Omnichannel Router):** نقطة نهاية برمجية غير متزامنة موحدة قادرة على فك ترميز وتوجيه حزم البيانات القادمة من مختلف تطبيقات منصة Meta بكفاءة عالية.  
* **الحد من الهلوسة البرمجية (Deterministic Constraints):** تم ضبط معايير الاستنتاج للنموذج بدقة عند درجة حرارة استنتاج Temperature \= 0.3 لضمان الالتزام الصارم ببيانات المخزون والأسعار المحددة مسبقاً من قبل المؤسسة دون حياد أو تأليف.  
* **صياغة النبرة اللغوية التوجيهية:** تم ضبط النظام لغوياً لإنتاج نصوص بالعامية المصرية الرصينة والمهنية، بهدف توجيه المستخدم بدقة وبشكل موضوعي لتسجيل بيانات الاتصال اللازمة لإتمام وتأكيد المعاملة التجارية بنجاح.

### **🚀 دليل التشغيل والتهيئة التقنية**

1. **جلب النموذج اللغوي محلياً:**  
   يرجى التأكد من سحب وتثبيت النموذج اللغوي عبر الواجهة الطرفية:
   ```bash 
   ollama pull qwen2.5-coder:1.5b

3. **تثبيت الحزم والاعتمادات البرمجية:**  
   يتم إنشاء بيئة برمجية معزولة وتثبيت المكتبات المطلوبة للتشغيل غير المتزامن:
   ```bash 
   pip install fastapi uvicorn httpx

5. **تهيئة منفذ الاتصال الخارجي:**  
   يتم استخدام بروتوكول نفق الاتصال الآمن لتوفير رابط مشفر يدعم بروتوكول HTTPS لمتطلبات Meta الفنية:
   ```bash 
   ngrok http 8000

7. **تشغيل الخادم:**  
   يتم تشغيل المحرك البرمجي الرئيسي باستخدام خادم ASGI المتمثل في Uvicorn:
   ```bash 
   python main.py

## **📊 System Overview & Metrics / نظرة عامة على النظام**

\[مخطط تدفق البيانات ومعمارية نظام DRACULA\]

## **👥 Contributing & Support / المساهمة والدعم**

This project is open-source under the **MIT License**. Feel free to open issues or submit pull requests for architecture optimizations, memory leak code-reviews, or local QR decoding layers.  
هذا المشروع متاح للعموم كبرمجية مفتوحة المصدر بموجب رخصة **MIT**. نرحب بكافة المساهمات البرمجية، وطلبات مراجعة الأكواد (Code Reviews)، والمقترحات الخاصة بتحسين إدارة الذاكرة، أو تطوير طبقات فك تشفير الرموز السريعة (QR Codes) محلياً.


