# AegisCrow - AI-Powered Freelance Escrow Contract Generator

## Deskripsi Project
AegisCrow adalah platform berbasis AI yang mengotomatisasi pembuatan kontrak escrow untuk freelancer dan UMKM di Indonesia. Sistem ini mengintegrasikan IBM Langflow dan IBM Bob untuk menghasilkan kontrak hukum terstruktur, perhitungan escrow dinamis, dan dokumentasi otomatis.

## Tema Hackathon
Financial / Productivity & Smart Business

## Cara Menjalankan Project

### 1. Setup Langflow
- Import file `langflow/aegiscrow-flow.json` ke Langflow
- Konfigurasi API Key: Gemini API, Composio API
- Setup SQL Database dengan Supabase (gunakan schema di `sample-data/supabase-schema.sql`)
- Aktifkan MCP Server dan copy konfigurasi JSON

### 2. Setup IBM Bob
- Download dan install IBM Bob dari https://bob.ibm.com/download
- Buka Settings > MCP > Add Server
- Paste konfigurasi JSON dari Langflow
- Tambahkan `"--with", "mcp<2.0.0"` di bagian args

### 3. Testing
- Buka IBM Bob dan ketik: "Buatkan kontrak AegisCrow untuk jasa desain seharga Rp 10.000.000, 3 milestone"
- Bob akan memanggil Langflow dan menghasilkan:
  - Ringkasan perhitungan Escrow (Stake 10%, Milestone dinamis)
  - Link Google Docs dengan kontrak lengkap
  - ID Kontrak dari Database Supabase
  - Draf email profesional

## Fitur Utama
1. **AI Contract Generation** - Ekstraksi data otomatis dari chat menjadi kontrak hukum
2. **Dynamic Escrow Calculator** - Perhitungan Stake 10% dan persentase milestone dinamis
3. **Auto-Document & Database** - Google Docs + Supabase PostgreSQL
4. **Smart Email Drafting** - Draf email profesional otomatis

## Arsitektur Sistem
User → IBM Bob (MCP Client) → MCP Protocol → Langflow (Multi-Agent) → External Tools (Google Docs, Supabase, Gmail)

## Struktur Folder
- `bob/` - Konfigurasi dan screenshot IBM Bob
- `langflow/` - Export flow dan screenshot canvas Langflow
- `prompts/` - System prompt dan deskripsi tool
- `sample-inputs/` - Contoh input user untuk testing
- `sample-data/` - Data pendukung dan schema database
- `expected-outputs/` - Output yang diharapkan dari sistem

## Tim
- Nama: [Nama Anda]
- Email: [Email Anda]
- Sertifikat IBM SkillsBuild: [Link atau attachment]

## Responsible AI
- Human-in-the-loop: User harus konfirmasi "YA" sebelum email dikirim
- Data minimization: Tidak menyimpan password/wallet di prompt
- Transparency: Disclaimer hukum di setiap output AI
- Fairness: Skema escrow adil untuk kedua belah pihak (Two-Way Commitment)