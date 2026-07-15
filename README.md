# كتاب تدبر القرآن الكريم

كتاب علمي في التدبر القرآني، مكتوب بـ LaTeX ومُهيَّأ للنشر الاحترافي.

## البنية

```
TadaburQuranBook/
├── .github/
│   └── workflows/
│       └── build.yml          # CI: XeLaTeX → PDF
├── Tex/
│   ├── preamble.tex           # الإعدادات العامة (عربي RTL)
│   ├── main.tex               # نقطة الدخول الرئيسية
│   └── chapters/
│       ├── chapter01.tex      # مدخل إلى التدبر
│       ├── chapter02.tex      # أصول التفسير
│       ├── chapter03.tex      # قواعد الاستنباط
│       ├── chapter04.tex      # تدبر سورة الفاتحة
│       └── chapter05.tex      # تدبر سورة البقرة
└── README.md
```

## التحويل المحلي

```bash
latexmk -xelatex -halt-on-error -interaction=nonstopmode \
        -output-directory=Tex/Output Tex/main.tex
```

> **متطلبات:** XeLaTeX + خط Amiri (حزمة `fonts-arabeyes` أو TeX Live)

## CI/CD

عند كل `push` أو `pull_request` يُطلَق GitHub Actions تلقائيًا،
يُجمَّع الكتاب بـ XeLaTeX وتُرفَع ملف PDF كـ artifact باسم `tadabur-quran-pdf`.
