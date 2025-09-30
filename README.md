# 📘 Modul 9
🚀 Tasbih App (Digital Counter)
Pada modul ini, kita akan belajar membuat aplikasi **Tasbih Digital** sederhana menggunakan Flutter.  
Aplikasi ini berfungsi sebagai penghitung dzikir (tasbih), dengan fitur utama menambah hitungan, mereset hitungan, dan menyimpan data secara lokal.


## 📌 Tentang Proyek
- **Nama Proyek**: tasbih_app  
- **Deskripsi**: Aplikasi penghitung tasbih digital berbasis Flutter.  
- **Fitur Utama**:
  - Menambah hitungan tasbih
  - Reset hitungan ke nol
  - Menyimpan hitungan terakhir agar tidak hilang saat aplikasi ditutup
  - (Opsional) Menetapkan target jumlah tasbih

🎯 **Tujuan**:
- Memahami penggunaan **state management sederhana** di Flutter  
- Mempelajari cara **update state secara real-time** pada widget  
- Menyimpan data lokal menggunakan **SharedPreferences**  


## 🔲 Konsep Utama

### 1. State Management (setState)
Menggunakan `setState()` untuk memperbarui nilai counter secara langsung pada UI.

```dart
int counter = 0;

void _incrementCounter() {
  setState(() {
    counter++;
  });
}

void _resetCounter() {
  setState(() {
    counter = 0;
  });
}
```

### 2. Menampilkan Counter di UI
Gunakan Text widget untuk menampilkan jumlah tasbih, serta tombol untuk menambah dan mereset.

```dart
Scaffold(
  appBar: AppBar(title: Text('Tasbih App')),
  body: Center(
    child: Column(
      mainAxisAlignment: MainAxisAlignment.center,
      children: [
        Text(
          '$counter',
          style: TextStyle(fontSize: 48, fontWeight: FontWeight.bold),
        ),
        Row(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            ElevatedButton(
              onPressed: _incrementCounter,
              child: Text('Tambah'),
            ),
            SizedBox(width: 16),
            ElevatedButton(
              onPressed: _resetCounter,
              child: Text('Reset'),
            ),
          ],
        ),
      ],
    ),
  ),
);
```
