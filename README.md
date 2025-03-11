# Fine-Tuning Model

## Deskripsi Proyek
Proyek ini bertujuan untuk melakukan fine-tuning model dengan menggunakan dataset teks biografi. Dataset ini digunakan untuk melatih model dalam menghasilkan pertanyaan berbobot terhadap teks biografi.

## Struktur Notebook

### 1. Pengunduhan Dataset
Notebook mengunduh dataset dari Google Drive dalam format CSV yang terdiri dari:
- `train_data.csv`

Dataset diunduh menggunakan `gdown`, dengan fungsi berikut:
```python
import gdown

def download_folder_from_drive(url, output_path):
    folder_id = url.split("/")[-1]
    gdown.download_folder(f"https://drive.google.com/drive/folders/{folder_id}", output=output_path, quiet=False)
```

### 2. Pemrosesan Dataset
Dataset CSV dikonversi ke format JSONL yang diperlukan untuk fine-tuning model. Contoh format JSONL:
```json
{
    "text": "Teks Biografi:\n[isi teks]",
    "question": "[pertanyaan yang dihasilkan]"
}
```
Proses konversi dilakukan dengan `pandas` dan `json`.

### 3. Fine-Tuning Model
Langkah-langkah fine-tuning melibatkan:
- Menggunakan model dasar (Llama-3.2-3B-Instruct).
- Melatih model dengan dataset JSONL.
- Menyesuaikan hyperparameter (batch size, learning rate, dll.).
