# Clozify Backend

Backend API untuk proyek capstone Clozify, dikembangkan oleh tim C242-PS413. Backend menggunakan FastAPI dan terhubung dengan layanan Google Cloud/Firebase serta endpoint layanan machine learning sesuai konfigurasi lingkungan.

## Struktur

Kode aplikasi berada di folder `app/`, sedangkan dependensi Python dicatat di `requirements.txt`.

## Persiapan

Pastikan Python versi yang kompatibel dengan dependensi proyek sudah terpasang. Dari root repository portofolio ini, jalankan:

```bash
cd backend
python -m venv .venv
```

Aktifkan virtual environment:

**Windows PowerShell**
```powershell
.\.venv\Scripts\Activate.ps1
```

**Windows Command Prompt**
```bat
.venv\Scripts\activate.bat
```

**Linux / macOS**
```bash
source .venv/bin/activate
```

Kemudian instal dependensi:

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

## Konfigurasi lingkungan

Buat file bernama `.env` di dalam folder `backend/` berdasarkan konfigurasi yang dibutuhkan aplikasi. Variabel yang digunakan oleh proyek mencakup:

```dotenv
GOOGLE_APPLICATION_CREDENTIALS_FIRESTORE=
DATABASE_PROJECTID=
DATABASE_INSTANCE=
API_KEY=
BASE_URL=
BUCKET_NAME=
GOOGLE_APPLICATION_CREDENTIALS=
ML_MOOD_ENDPOINT=
ML_OUTFIT_ENDPOINT=
```

Isi nilai sesuai konfigurasi milikmu dan dokumentasi layanan terkait. Jangan masukkan API key, kredensial Google Cloud/Firebase, token, atau rahasia lainnya ke Git. File kredensial dan `.env` harus tetap lokal dan dikecualikan melalui `.gitignore`.

Nama variabel di atas merupakan daftar konfigurasi yang digunakan pada dokumentasi proyek; pastikan nilainya cocok dengan implementasi dan environment yang hendak dijalankan.

## Menjalankan API

Jalankan perintah berikut dari folder `backend/` setelah dependensi dan konfigurasi disiapkan:

```bash
uvicorn app.main:app --reload
```

Secara default, dokumentasi interaktif FastAPI tersedia di `http://127.0.0.1:8000/docs` ketika server berjalan lokal. Endpoint tertentu mungkin belum berfungsi sebelum layanan cloud, akses database/storage, dan endpoint machine learning dikonfigurasi.

## Catatan

- Repository ini merupakan salinan portofolio dari proyek tim, bukan klaim kepemilikan tunggal atas keseluruhan Clozify.
- Untuk referensi sumber backend tim, kunjungi [C242-PS413/clozify-backend](https://github.com/C242-PS413/clozify-backend).
