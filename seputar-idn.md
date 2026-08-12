# Panduan Request GraphQL IDN Live (Postman / API Client)

Panduan langkah demi langkah untuk mengambil semua livestream dari IDN App melalui API GraphQL.

---

### 1. Atur Method & URL
* **Method**: Ubah dropdown method dari `GET` menjadi `POST`.
* **URL**:
  ```text
  https://api.idn.app/graphql
  ```

---

### 2. Atur Headers
Buka tab **Headers** (di bawah kolom URL) dan tambahkan konfigurasi header berikut:

| Key | Value |
| :--- | :--- |
| `Content-Type` | `application/json` |
| `User-Agent` | `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/120.0.0.0 Safari/537.36` |

---

### 3. Masukkan Payload Body
1. Buka tab **Body**.
2. Pilih opsi **raw**.
3. Pada dropdown format di sebelah kanan (yang bertuliskan *Text*), ubah menjadi **JSON**.
4. Salin dan tempel JSON berikut ke dalam kolom teks:

```json
{
  {
  "query": "query GetLivestreams { getLivestreams { title slug playback_url live_at view_count image_url creator { name username avatar } } }"
  }
}
```

### 4. Kirim Request
1. Klik tombol **Send** (tombol berwarna biru).
2. Periksa kotak respons di bagian bawah:
   - **Status**: `200 OK`
   - **Hasil**: Data JSON lengkap berisi informasi stream termasuk `playback_url` (`.m3u8`).
