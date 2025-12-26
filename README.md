# Mini-RAG-Banjir-Sumatera

# Mini RAG System untuk Informasi Banjir di Sumatera

Repository ini berisi implementasi **Mini Retrieval-Augmented Generation (RAG)** untuk sistem tanya jawab
berbasis dokumen berita banjir di Sumatera, Indonesia. Proyek ini dikembangkan sebagai bagian dari
Natural Language Processing (NLP) untuk membandingkan performa pendekatan **RAG** dan **Non-RAG**
dalam menghasilkan jawaban faktual.

## 📄 Dataset
Dataset yang digunakan terdiri dari 50 dokumen teks berita dalam format .txt yang berisi informasi terkait peristiwa banjir di wilayah Sumatera. Setiap dokumen dimuat dan diproses menjadi teks bersih dengan penghapusan karakter yang tidak relevan.
Dokumen mencakup informasi mengenai:
- Penyebab banjir
- Wilayah terdampak
- Waktu kejadian
- Infrastruktur yang rusak
- Penanganan dan bantuan

## ⚙️ Metodologi
Pipeline RAG yang digunakan meliputi:
1. Pra-pemrosesan dokumen dan chunking teks
2. Pembentukan embedding menggunakan model multilingual
3. Penyimpanan dan pencarian vektor menggunakan FAISS
4. Reranking konteks menggunakan Maximal Marginal Relevance (MMR)
5. Generasi jawaban menggunakan model bahasa berbasis sequence-to-sequence

Dua model embedding yang dibandingkan:
- **BAAI/bge-m3**
- **paraphrase-multilingual-MiniLM-L12-v2**

Jumlah chunk hasil retrieval divariasikan dengan **k = 1, 3, dan 5**.

## 🤖 Model dan Tools
- Model Embedding: BGE-M3, MiniLM (multilingual)
- Vector Database: FAISS
- Reranking: Maximal Marginal Relevance (MMR)
- Model Bahasa: Flan-T5 Base
- Antarmuka (opsional): Gradio
- Bahasa Pemrograman: Python

## 📊 Evaluasi
Evaluasi dilakukan secara **manual (human evaluation)** berdasarkan tiga aspek:
- Accuracy
- Completeness
- Hallucination (analisis kualitatif)

Hasil eksperimen menunjukkan bahwa pendekatan **RAG** secara signifikan meningkatkan kualitas jawaban
dibandingkan **Non-RAG**, dengan embedding **BGE-M3** menghasilkan jawaban yang lebih ringkas dan stabil.
