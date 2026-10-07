
🎙️ XTTS V2 Arabic Voice Studio

Arabic voice cloning and text-to-speech web application powered by Coqui XTTS-v2, designed for voice-only cloning, audio processing, playback, and generation.

✨ نبذة عن المشروع

XTTS V2 Arabic Voice Studio هو استوديو ويب لمعالجة واستنساخ الأصوات باستخدام نموذج Coqui XTTS-v2.

المشروع مصمم للعمل على أجهزة CPU بدون الحاجة إلى بطاقة NVIDIA، مع واجهة ويب مخصصة للصوت فقط.

المميزات

* 🎙️ استنساخ الصوت باستخدام XTTS-v2.
* 🇸🇦 دعم اللغة العربية.
* 📤 رفع ملفات صوتية.
* 🔊 معاينة الصوت.
* 📝 تحويل النص إلى كلام باستخدام الصوت المرجعي.
* 🎧 إخراج صوتي قابل للتشغيل والتنزيل.
* 🎬 لا يحتاج إلى رفع فيديو.
* 🖥️ يعمل على CPU.
* ⚡ استخدام عدة أنوية CPU.
* 🌐 واجهة Web UI.
* 🔄 تجهيز الصوت وتحويل الصيغ باستخدام FFmpeg.
* 🧩 بنية قابلة للتطوير لإضافة نماذج مثل SILMA وF5-TTS مستقبلًا.

⸻

📦 المتطلبات

النظام

* Linux / Ubuntu
* Python 3.12
* RAM: يفضل 16GB
* CPU: يفضل 4 أنوية أو أكثر
* مساحة تخزين كافية لتحميل نماذج XTTS
* FFmpeg

يمكن تشغيل المشروع على CPU، لكن توليد الصوت سيكون أبطأ بكثير من GPU.

⸻

🚀 التثبيت

استنسخ المشروع:

git clone https://github.com/YOUR_USERNAME/xtts-silma-f5-arabic-cpu.git

ادخل إلى المجلد:

cd xtts-silma-f5-arabic-cpu

إنشاء بيئة Python اختيارية

python3.12 -m venv .venv

تفعيل البيئة:

source .venv/bin/activate

تحديث pip

python -m pip install --upgrade pip

⸻

🔧 تثبيت FFmpeg

Ubuntu / Debian:

sudo apt-get update && sudo apt-get install -y ffmpeg

التأكد:

ffmpeg -version

⸻

🔥 تثبيت PyTorch CPU

لأن هذا الإصدار مخصص للعمل بدون NVIDIA CUDA:

python -m pip install --no-cache-dir torch==2.8.0+cpu torchaudio==2.8.0+cpu torchvision==0.23.0+cpu --index-url https://download.pytorch.org/whl/cpu

⸻

📚 تثبيت مكتبات المشروع

إذا كان لديك ملف:

requirements-cpu.txt

شغّل:

python -m pip install -r requirements-cpu.txt

ثم ثبّت الإصدارات المتوافقة عند الحاجة:

python -m pip install --no-cache-dir numpy==1.26.4 scikit-learn==1.5.2 transformers==4.57.1

⸻

🧪 اختبار XTTS

بعد انتهاء التثبيت:

python -c "import torch; print('Torch:', torch.__version__); print('CUDA:', torch.cuda.is_available())"

في نسخة CPU يجب أن تكون النتيجة شبيهة بـ:

Torch: 2.8.0+cpu
CUDA: False

اختبار XTTS:

python -c "from TTS.api import TTS; print('XTTS IMPORT OK')"

إذا ظهر:

XTTS IMPORT OK

فإن مكتبة XTTS تعمل بنجاح.

⸻

▶️ تشغيل المشروع

بعد تثبيت كل المتطلبات:

./run_cpu.sh

أو:

bash run_cpu.sh

المشروع يستخدم افتراضيًا:

Port: 8000
Device: CPU
CPU threads: 4

ثم افتح:

http://127.0.0.1:8000

إذا كان السيرفر على Cloud/Lightning أو VPS، استخدم عنوان السيرفر والمنفذ 8000 بالطريقة التي يوفرها مزود الاستضافة.

⸻

🛑 إيقاف السيرفر

داخل الطرفية:

Ctrl+C

⸻

⚙️ ملفات المشروع

xtts-silma-f5-arabic-cpu/
│
├── app/
│   ├── ...
│   └── ...
│
├── requirements.txt
├── requirements-cpu.txt
├── requirements-lightning-minimal.txt
│
├── run_cpu.sh
├── run_lightning.sh
│
├── setup_cpu.sh
├── setup_f5.sh
├── setup_lightning.sh
│
├── start_dubbing.sh
│
├── README.md
└── LIGHTNING.md

⸻

⚠️ ترخيص XTTS

مهم جدًا عند نشر المشروع على GitHub:

لا تكتب أن نموذج XTTS-v2 نفسه مرخص تجاريًا بشكل مفتوح بدون التحقق من شروطه.

عند تشغيل XTTS، قد تظهر رسالة Coqui التي تطلب منك تأكيد أحد الخيارين:

I have purchased a commercial license from Coqui

أو الموافقة على شروط CPML للاستخدام غير التجاري.

لذلك ضع في README قسمًا مثل:

⚖️ Licensing

This repository contains application code and configuration for running XTTS-v2.

XTTS-v2 model licensing is separate from this project’s source code.

Users are responsible for reviewing and complying with the applicable Coqui XTTS licensing terms before using the model, especially for commercial applications.

⸻

📝 وصف قصير لـ GitHub

إذا GitHub طلب منك Description قصير، استخدم:

Arabic AI Voice Studio powered by Coqui XTTS-v2 — voice cloning, text-to-speech, audio processing, and CPU inference.

وإذا تريد وصف عربي:

استوديو صوت عربي بالذكاء الاصطناعي باستخدام XTTS-v2 لاستنساخ الصوت وتحويل النص إلى كلام ومعالجة الملفات الصوتية على CPU.

🏷️ Topics

ضع هذه الكلمات في GitHub:

xtts
xtts-v2
voice-cloning
arabic-tts
arabic-ai
text-to-speech
voice-synthesis
speech-synthesis
coqui-tts
pytorch
python
cpu-inference
audio-processing
ffmpeg

ملاحظة: قبل النشر، الأفضل أن نجهز README.md الخاص بمشروعك الحالي فعليًا بدل هذا القالب العام، بحيث يحتوي على أسماء الملفات والأوامر الحقيقية الموجودة عندك ولا توجد فيه أي تعليمات غير مطابقة للمشروع.
