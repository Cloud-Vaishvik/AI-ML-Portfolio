# 🧞 TheBookGinni — Universal Book AI Assistant

A multilingual AI-powered chat assistant for books. Upload any PDF and ask questions in 15+ languages — powered by Google Gemini.

## 🌐 Live Demo

**[the-book-ginni.vercel.app](https://the-book-ginni.vercel.app/)**

## ✨ Features

- 📚 Upload any PDF book in any language
- 🌍 Supports 15+ languages: Hindi, French, Spanish, Arabic, Chinese, Japanese, German, and more
- 🤖 Powered by **Google Gemini 2.5 Flash / Pro / Flash-Lite**
- 🔒 Strictly grounded in uploaded content — no hallucination beyond the book
- 💬 Chat history with multi-session support
- 📖 Large context window — handles full books (1M tokens)
- 🆓 Free to use with a Gemini API key (500 req/day free)

## 🚀 Getting Started

### 1. Get a Free Gemini API Key
Visit [aistudio.google.com/apikey](https://aistudio.google.com/apikey) — no credit card required.

### 2. Use the Live App
Go to [the-book-ginni.vercel.app](https://the-book-ginni.vercel.app/), paste your API key, upload a PDF, and start asking.

### 3. Run Locally
```bash
cd the-book-ginni

# Option A: Open directly
open index.html

# Option B: Serve with a local server (recommended to avoid CORS)
npx serve .
# or
python -m http.server 3000
```

## 📁 File Structure

```
the-book-ginni/
│
├── index.html          # Main app (single-file frontend)
├── README.md
└── (assets if any)
```

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | HTML, CSS, JavaScript |
| AI Backend | Google Gemini API (gemini-2.5-flash) |
| PDF Parsing | Browser-native PDF handling |
| Deployment | Vercel |

## 🌐 Supported Languages

| Language | Code |
|----------|------|
| English | en |
| Hindi | hi |
| French | fr |
| Spanish | es |
| German | de |
| Arabic | ar |
| Chinese | zh |
| Japanese | ja |
| Portuguese | pt |
| Russian | ru |
| Italian | it |
| Bengali | bn |
| Urdu | ur |
| Tamil | ta |
| Telugu | te |

## ⚙️ Models Available

- **Gemini 2.5 Flash** ⭐ (Recommended — balanced speed & quality)
- **Gemini 2.5 Pro** (Smartest — best for complex reasoning)
- **Gemini 2.5 Flash-Lite** (Fastest — good for quick queries)

## 🔐 Privacy

Your Gemini API key is stored only in your browser session and never sent to any server other than Google's API. Uploaded PDFs are processed locally in the browser.

## 📄 License

MIT License
