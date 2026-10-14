# Tool Descriptions for AegisCrow MCP Integration

Dokumen ini menjelaskan definisi tools yang diekspos oleh Langflow ke IBM Bob melalui Model Context Protocol (MCP).

## 1. Tool: `generate_aegiscrow_contract`
**Deskripsi untuk Bob:** 
"Membuat draf kontrak freelance escrow AegisCrow secara otomatis, menghitung pembagian milestone dan stake 10%, menyimpannya ke Google Docs, mencatatnya ke Database, dan menyiapkan draf email. Gunakan tool ini ketika user meminta untuk membuat kontrak, menghitung escrow, atau membuat perjanjian freelance."

**Input yang diharapkan (dari Bob ke Langflow):**
- `message` (String): Instruksi natural language dari user (berisi detail proyek, nama, harga, milestone, dll).

**Output yang dihasilkan (dari Langflow ke Bob):**
- Teks ringkasan perhitungan Escrow (Total, Stake 10%, Rilis per Milestone).
- Link Google Docs berisi kontrak lengkap.
- ID Kontrak dari Database Supabase.
- Konfirmasi pembuatan draf email.

---

## 2. Tool: `send_aegiscrow_email` *(Opsional, jika Anda memisahkannya)*
**Deskripsi untuk Bob:** 
"Mengirimkan draf email kontrak AegisCrow yang telah disetujui oleh user ke alamat email klien. Gunakan tool ini HANYA ketika user secara eksplisit mengetik 'YA' atau 'kirim email'."

**Input yang diharapkan:**
- `confirmation` (String): Konfirmasi user (misal: "YA").

**Output yang dihasilkan:**
- Status pengiriman email (Berhasil/Gagal).