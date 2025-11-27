# Server AI RAG - Sistem Jaringan Komputer

Proyek Server AI dan RAG untuk mata kuliah Sistem dan Jaringan Komputer

## 📋 Deskripsi Project

Repository ini berisi workflow N8N untuk bot Telegram yang terintegrasi dengan Gemini AI 2.0 Flash untuk menjawab pesan pengguna secara otomatis menggunakan teknologi AI generatif.

## 🤖 Workflow N8N - Telegram Bot with Gemini AI

### Komponen Workflow

#### 1. **Telegram Trigger**
- Mendeteksi pesan masuk dari pengguna Telegram
- Trigger otomatis setiap ada pesan baru

#### 2. **HTTP Request (Gemini AI)**
- Mengirim pesan user ke API Gemini AI 2.0 Flash
- Method: POST
- Endpoint: `generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash`
- Memproses input text dan menghasilkan respons AI

#### 3. **Send Text Message (Telegram)**
- Mengirim balasan AI kembali ke chat user
- Menggunakan Chat ID dari trigger untuk reply

### 🔄 Alur Kerja

```
User mengirim pesan → Telegram Trigger → HTTP Request ke Gemini AI → Telegram Reply
```

## 🚀 Cara Setup

### Prerequisites
- N8N instance (local/cloud)
- Gemini API Key ([Google AI Studio](https://aistudio.google.com/app/apikey))
- Telegram Bot Token ([BotFather](https://t.me/botfather))

### Langkah Instalasi

1. **Import Workflow**
   ```bash
   # Import file workflow-gemini.json ke N8N instance Anda
   ```

2. **Setup Telegram Credentials**
   - Buka BotFather di Telegram
   - Buat bot baru atau gunakan bot existing
   - Copy bot token
   - Add credentials di N8N untuk Telegram Trigger dan Send Message nodes

3. **Setup Gemini API**
   - Buka workflow di N8N
   - Edit node "HTTP Request"
   - Ganti `YOUR_API_KEY_HERE` dengan API key Gemini Anda
   ```
   https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent?key=YOUR_GEMINI_API_KEY
   ```

4. **Aktifkan Workflow**
   - Toggle workflow menjadi "Active"
   - Test dengan mengirim pesan ke bot Telegram Anda

## 📁 Struktur File

```
.
├── workflow-gemini.json    # N8N workflow configuration
├── README.md              # Dokumentasi project
├── .gitignore            # Git ignore rules
├── docker-compose.yml    # Docker configuration (jika ada)
└── docs/                 # Dokumentasi tambahan
```

## 🔒 Keamanan

- ⚠️ **JANGAN** commit API key atau credentials ke repository
- Gunakan environment variables atau N8N credentials manager
- File `.gitignore` sudah dikonfigurasi untuk mengabaikan file sensitif

## 📝 Catatan

- Model yang digunakan: **Gemini 2.0 Flash** (model terbaru dari Google)
- Workflow sudah dioptimasi untuk response time yang cepat
- Support untuk berbagai jenis pertanyaan dan percakapan

## 👨‍💻 Pengembang

Muhammad Akbar Pratama - Sistem dan Jaringan Komputer

## 📄 Lisensi

Project ini dibuat untuk keperluan akademik mata kuliah Sistem dan Jaringan Komputer.

---

**⭐ Jangan lupa star repository ini jika bermanfaat!**
