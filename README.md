# Chapter 11: Context API

## GitHube Pages
Link: [Mini Context](https://fatahpratam.github.io/tutorial-mini-context/)

## Youtube Tutorial
- Link: [Full Stack React Developer Course with Appwrite](https://www.youtube.com/watch?v=Bvwq_S0n2pk)
- Creator: [HiteshCodeLab](https://www.youtube.com/@HiteshCodeLab)

## Context API
- Ketika suatu child component yang nested di dalam parent component membutuhkan data, maka child component memerlukan props yang diberikan oleh parent component.
- Data flow ini pada umumnya tidak bermasalah, akan tetapi jika child component tersebut nested sedalam 3 level dan membutuhkan data dari component level 1, maka hal ini menciptakan aliran data yang berlebihan.
- Solusi dari masalah ini adalah state management dengan menciptakan sebuah store yang dapat menyimpan data dan dapat diakses oleh semua component.
- Menggunakan method Context API.

## Alur kerja sederhana Context API
- Memulai projek
- Membuat aplikasi React sederhana dari template (CRA atau Vite)
- Membuat sebuah `Context` (Nama lain dari store)
- Menginformasikan semua component bahwa terdapat sebuah `Context` melalui Context Provider.
- Menggunakan `Context` di dalam child component

## Cara mengatur Context
### Membuat Context
- Buat folder context
- Buat file UserContext.js untuk membuat `Context` untuk variabel user.
- Di dalam file, panggil method `createContext()`, simpan hasil panggilan ke dalam variabel, dan export variabel tersebut.
- Buat file UserContextProvider.jsx untuk membuat Context Provider untuk variabel user.
- Di dalam file, buat sebuah fungsi `UserContextProvider` dengan parameter `{ children }`.
- Di dalam fungsi tersebut, Buat state untuk variabel user dengan setUser sebagai fungsi pengubah state.
- Import `UserContext` dari file UserContext.js sebelumnya.
- Kembalikan JSX `UserContext.Provider` dengan argument untuk kunci 'value' dengan object `{user, setUser}` dari state sebelumya.
- Panggil variabel children di dalam JSX `UserContext.Provider`.
- Terakhir, export fungsi `UserContextProvider`.

### Menggunakan Context
- Import `UserContextProvider` dan apit component yang akan menggunakan `Context` dengan JSX `UserContextProvider`.
- Untuk mengakses atau mengubah variabel user, import `UserContext` dan panggil method `useContext` dengan `UserContext` sebagai argument-nya.

## Fungsi Context
- `createContext()`: Memungkinkan Anda membuat Konteks yang dapat disediakan atau dibaca oleh komponen
- `useContext()`: Menerima objek konteks (nilai yang dikembalikan dari `React.createContext`) dan mengembalikan nilai konteks saat ini, seperti yang diberikan oleh penyedia konteks terdekat untuk konteks yang diberikan.