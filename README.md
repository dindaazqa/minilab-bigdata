# Minilab Big Data – Data Ingestion (Tahap 1)

## Overview
Proyek ini bertujuan untuk melakukan proses ingestion data dari dua sumber utama, yaitu database relasional (PostgreSQL) dan file tabular (CSV/XLSX), ke dalam MinIO sebagai object storage (data lake).


## 1. Setup Environment
Pastikan environment telah memenuhi kebutuhan berikut:
* Docker
* Python 3.x

Install dependency yang diperlukan:
pip install pandas sqlalchemy psycopg2-binary openpyxl minio jupyter

## 2. Deployment Services
Jalankan container PostgreSQL dan MinIO menggunakan Docker:
docker compose up -d

Verifikasi container berjalan:
docker ps

Akses MinIO melalui browser: http://localhost:9001

## 3. Data Sources
Data yang digunakan terdiri dari:
* Data dari PostgreSQL (tabel relasional)
* File dalam format CSV dan/atau XLSX

## 4. Proses Data Ingestion
Langkah-langkah ingestion:
* Mengambil data dari PostgreSQL menggunakan query SQL
* Membaca file CSV menggunakan pandas
* Membaca file XLSX menggunakan openpyxl
* Memuat data ke dalam DataFrame
* Mengunggah data ke MinIO

## 5. Struktur Penyimpanan di MinIO
Data hasil ingestion disimpan dengan struktur:
raw/
  rdbms/
  csv/
  xlsx/

## 6. Validasi
Validasi dilakukan dengan memastikan:
* Container PostgreSQL dan MinIO dalam kondisi berjalan
* MinIO dapat diakses melalui browser
* Data berhasil diunggah ke bucket
* File tersimpan sesuai struktur yang ditentukan

## 7. Kendala Umum
Beberapa kendala yang mungkin terjadi:
* Python tidak terdeteksi → pastikan sudah terinstall dan terdaftar di PATH
* Jupyter Notebook tidak terbuka otomatis → akses manual melalui URL di terminal
* Bucket MinIO belum tersedia → buat bucket terlebih dahulu di MinIO
