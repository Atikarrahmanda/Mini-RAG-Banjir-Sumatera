# Mini-RAG-Banjir-Sumatera

# Mini RAG System untuk Informasi Banjir di Sumatera

Repository ini berisi implementasi **Mini Retrieval-Augmented Generation (RAG)** untuk sistem tanya jawab
berbasis dokumen berita banjir di Sumatera, Indonesia. Proyek ini dikembangkan sebagai bagian dari
Natural Language Processing (NLP) untuk membandingkan performa pendekatan **RAG** dan **Non-RAG**
dalam menghasilkan jawaban faktual.

## 📄 Dataset
Dataset pada penelitian ini diperoleh melalui proses scraping terhadap 50 artikel berita berbahasa Indonesia yang membahas kejadian banjir di Sumatera. Artikel-artikel tersebut dikumpulkan dari beberapa portal berita daring dan digunakan sebagai korpus dokumen dalam sistem Retrieval-Augmented Generation (RAG). Dataset yang digunakan dalam format .txt. Setiap dokumen dimuat dan diproses menjadi teks bersih dengan penghapusan karakter yang tidak relevan.
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

## 🖥️ User Interface (Gradio)
<img width="2239" height="734" alt="image" src="https://github.com/user-attachments/assets/81f66ee6-1e20-4bf4-8ced-8316d6abec41" />
Sebagai pelengkap sistem, proyek ini menyediakan **UI berbasis Gradio**
yang memungkinkan pengguna untuk:
- Memasukkan pertanyaan secara langsung
- Memilih mode jawaban (RAG atau Non-RAG)
- Memilih model embedding
- Menentukan jumlah chunk hasil retrieval (*k*)
- Melihat jawaban yang dihasilkan beserta konteks pendukung

AUI ini bertujuan untuk meningkatkan transparansi sistem dan memudahkan eksplorasi
perilaku model dalam berbagai skenario.


Hasil eksperimen menunjukkan bahwa pendekatan **RAG** secara signifikan meningkatkan kualitas jawaban
dibandingkan **Non-RAG**, dengan embedding **BGE-M3** menghasilkan jawaban yang lebih ringkas dan stabil.
