# <h1 align="center">Laporan Praktikum Modul 4 </h1>
<p align="center">Hajratun Nisa - IF 11-03 - 2311102203 </p>

## Tugas 

### 1. 

Source Code:
```Golang
func factorial(n int) int {
    if n == 0 {
        return 1
    }
    return n * factorial(n-1)
}
```

Operasi diatas merupakan operasi menghitung faktorial dari sebuah bilangan bulat dengan cara fungsi memanggil dirinya sendiri untuk menghitung faktorial secara berulang

Source Code:
```Golang
func printPermutation(n, r int) {
    result := factorial(n) / factorial(n-r)
    fmt.Printf("Permutation(%d, %d) = %d\n", n, r, result)
}
```
Operasi diatas merupakan operasi permutasi dengan rumus n! / (n-r)!. Untuk menghitung faktorial dipangillah fungsi factorial sebelumnya
 dirinya sendiri untuk menghitung faktorial secara berulang

 Source Code:
```Golang
func printCombination(n, r int) {
    result := factorial(n) / (factorial(r) * factorial(n-r))
    fmt.Printf("Combination(%d, %d) = %d\n", n, r, result)
}
```
Operasi diatas merupakan operasi kombinasi dengan rumus n! / (r! * (n-r)!). untuk menghitung faktorial dipangillah fungsi factorial sebelumnya

### 2.	

Source Code:
```Golang
type Peserta struct {
    nama       string
    soalSelesai int
    totalWaktu  int
}
```
Operasi diatas merupakan operasi mendefinisikan sebuah struktur data (struct) yang diberi nama Peserta.

Source Code:
```Golang
func hitungSkor(nama string, waktu []int) Peserta {
    const maxWaktu = 301
    soalSelesai := 0
    totalWaktu := 0

    for _, w := range waktu {
        if w < maxWaktu {
            soalSelesai++
            totalWaktu += w
        }
    }

    return Peserta{nama, soalSelesai, totalWaktu}
}
```
Operasi diatas merupakan operasi menghitung skor seorang peserta dalam suatu kompetisi atau ujian berdasarkan waktu yang mereka gunakan untuk menyelesaikan setiap soal.

Source Code:
```Golang
var n int
    fmt.Print("Masukkan jumlah peserta: ")
    fmt.Scan(&n)

    pesertaList := make([]Peserta, n)

    for i := 0; i < n; i++ {
        var nama string
        var waktu [8]int

        fmt.Print("Masukkan nama peserta: ")
        fmt.Scan(&nama)

        fmt.Print("Masukkan waktu penyelesaian untuk 8 soal (dalam menit): ")
        for j := 0; j < 8; j++ {
            fmt.Scan(&waktu[j])
        }

        pesertaList[i] = hitungSkor(nama, waktu[:])
    }
```
Operasi diatas merupakan operasi mengumpulkan data dari pengguna, yaitu jumlah peserta, nama peserta, dan waktu penyelesaian setiap soal.

Source Code:
```Golang
pemenang := pesertaList[0]
    for _, peserta := range pesertaList {
        if peserta.soalSelesai > pemenang.soalSelesai || 
           (peserta.soalSelesai == pemenang.soalSelesai && peserta.totalWaktu < pemenang.totalWaktu) {
            pemenang = peserta
        }
    }
```
Operasi diatas merupakan operasi mencari dan menentukan siapa peserta dengan skor tertinggi (pemenang) dari seluruh peserta yang datanya telah dikumpulkan sebelumnya.

### 3.

Source Code:
```Golang
func cetakDeret(n int) {
        for n != 1 {
                fmt.Print(n, " ")
                if n%2 == 0 {
                        n /= 2
                } else {
                        n = 3*n + 1
                }
        }
        fmt.Println(1)
}
```
Operasi diatas merupakan operasi untuk menghitung nilai barisan deret suku berikutnya jika nilai n genap maka suku berikutnya n * 1/2 dan jika nilai n ganjil maka suku berikutnya 3*n + 1



