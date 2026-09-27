# <h1 align="center">Laporan Praktikum Modul 1 - Codeblocks IDE & Pengenalan Bahas C++ (Bagian Pertama)</h1>

<p align="center">Muhammad Farrel Argiyanto - 109082500018</p>

## Dasar Teori

Code::Blocks merupakan _Integrated Development Environment_ (IDE) yang digunakan untuk membuat program menggunakan bahasa C/C++. Code::Blocks bersifat _free_, _open-source_, dan _cross-platform_ serta menyediakan fasilitas untuk menulis, melakukan _build_, menjalankan program, dan menampilkan _error message_ ketika terdapat kesalahan sintaks [1]. Bahasa C++ merupakan bahasa pemrograman yang dikembangkan oleh Bjarne Stroustrup berdasarkan bahasa C dan memiliki berbagai fitur seperti _class_, fungsi, dan _operator overloading_ [1]. Dalam C++, program memiliki struktur dasar yang terdiri dari library, deklarasi variabel atau konstanta, fungsi, dan fungsi utama `main()`. Tipe data digunakan untuk menentukan jenis data yang disimpan dalam variabel, seperti `char`, `int`, `float`, dan `double`, sedangkan variabel digunakan untuk menyimpan nilai yang dapat berubah selama program berjalan [1]. Proses input dan output dapat dilakukan menggunakan `cin` dan `cout`, sedangkan operator digunakan untuk melakukan operasi terhadap data, seperti operator aritmatika, _assignment_, perbandingan, dan logika [1]. C++ juga menyediakan struktur kondisional seperti `if`, `if-else`, dan `switch` untuk pengambilan keputusan serta perulangan `for`, `while`, dan `do-while` untuk menjalankan perintah secara berulang [1]. Selain itu, `struct` dapat digunakan untuk mengelompokkan beberapa variabel dengan tipe data berbeda menjadi satu kesatuan, sedangkan fungsi digunakan untuk membagi program menjadi bagian-bagian tertentu agar lebih terstruktur [1].

## Unguided

### 1. Buatlah program yang menerima input-an dua buah bilangan bertipe float, kemudian memberikan output-an hasil penjumlahan, pengurangan, perkalian, dan pembagian dari dua bilangan tersebut.

```C++
#include <iostream>
using namespace std;

int main(){
    float x, y;

    cin >> x >> y;

    cout << "hasil penjumlahan = " << x + y << endl;
    cout << "hasil pengurangan = " << x - y << endl;
    cout << "hasil perkalian = " << x * y << endl;
    cout << "hasil pembagian = " << x / y << endl;

    return 0;
}
```

### Output Unguided 1 :

##### Output 1

![Screenshot Output Unguided 1_2](https://raw.githubusercontent.com/Farrel-13/Laporan_praktikum/main/laprak01_output01.png)

Program tersebut menerima dua buah bilangan bertipe `float`, kemudian melakukan empat operasi aritmatika yaitu penjumlahan, pengurangan, perkalian, dan pembagian. Hasil dari setiap operasi kemudian ditampilkan menggunakan `cout`.

### 2. Buatlah sebuah program yang menerima masukan angka dan mengeluarkan output nilai angka tersebut dalam bentuk tulisan. Angka yang akan di-input-kan user adalah bilangan bulat positif mulai dari 0 s.d. 100.

Contoh:

```text
79 : tujuh puluh sembilan
```

```C++
#include <iostream>
using namespace std;

int main() {
    int angka;

    cout << "Masukkan angka (0-100): ";
    cin >> angka;

    if (angka == 0)
        cout << "Nol";
    else if (angka == 100)
        cout << "Seratus";
    else if (angka < 10) {
        string satuan[] = {"", "Satu", "Dua", "Tiga", "Empat",
                           "Lima", "Enam", "Tujuh", "Delapan", "Sembilan"};
        cout << satuan[angka];
    }
    else if (angka < 20) {
        string belasan[] = {"", "", "Dua Belas", "Tiga Belas", "Empat Belas",
                            "Lima Belas", "Enam Belas", "Tujuh Belas",
                            "Delapan Belas", "Sembilan Belas"};
        if (angka == 10)
            cout << "Sepuluh";
        else if (angka == 11)
            cout << "Sebelas";
        else
            cout << belasan[angka];
    }
    else if (angka < 100) {
        string satuan[] = {"", "Satu", "Dua", "Tiga", "Empat",
                           "Lima", "Enam", "Tujuh", "Delapan", "Sembilan"};

        string puluhan[] = {"", "", "Dua Puluh", "Tiga Puluh", "Empat Puluh",
                            "Lima Puluh", "Enam Puluh", "Tujuh Puluh",
                            "Delapan Puluh", "Sembilan Puluh"};

        cout << puluhan[angka / 10];

        if (angka % 10 != 0)
            cout << " " << satuan[angka % 10];
    }

    return 0;
}

```

### Output Unguided 2 :

##### Output 1

![Screenshot Output Unguided 1_2](https://raw.githubusercontent.com/Farrel-13/Laporan_praktikum/main/laprak01_output02.png)

Program tersebut menerima input berupa bilangan bulat positif dari 0 sampai 100, kemudian menampilkan angka tersebut dalam bentuk tulisan bahasa Indonesia.

### 3. Buatlah program yang dapat memberikan input dan output seperti berikut.

Contoh input:

```text
3
```

Contoh output:

```text
3 2 1 * 1 2 3
  2 1 * 1 2
    1 * 1
      *
```

```C++
#include <iostream>
using namespace std;

int main()
{
    int n;

    cout << "Input: ";
    cin >> n;

    cout << "Output:" << endl;

    for (int i = n; i >= 1; i--)
    {
        for (int j = n; j > i; j--)
            cout << "  ";

        for (int j = i; j >= 1; j--)
            cout << j << " ";

        cout << "*";

        for (int j = 1; j <= i; j++)
            cout << " " << j;

        cout << endl;
    }

    for (int i = 0; i < n; i++)
        cout << "  ";
    cout << "*";

    return 0;
}
```

### Output Unguided 3 :

##### Output 1

![Screenshot Output Unguided 1_2](https://raw.githubusercontent.com/Farrel-13/Laporan_praktikum/main/laprak01_output03.png)

Program tersebut menerima sebuah angka sebagai input, kemudian menghasilkan pola berbentuk cermin (_mirror_). Setiap baris menampilkan angka secara menurun dari angka input sampai `1`, kemudian tanda `*`, dan angka kembali secara menaik.

## Kesimpulan

Berdasarkan praktikum Modul 1, dapat disimpulkan bahwa Code::Blocks dapat digunakan sebagai IDE untuk menulis, melakukan _build_, dan menjalankan program C++. Pada praktikum ini dipelajari dasar-dasar bahasa C++ seperti struktur program, tipe data, variabel, input dan output menggunakan `cin` dan `cout`, serta penggunaan operator aritmatika. Selain itu, praktikum juga memberikan pemahaman mengenai penggunaan kondisi dan perulangan dalam membuat program sederhana. Melalui latihan yang diberikan, konsep-konsep tersebut dapat diterapkan untuk mengolah input dan menghasilkan output sesuai dengan kebutuhan program.

## Referensi

[1] Modul Praktikum Struktur Data 1. (n.d.). "Modul 1: Code Blocks IDE & Pengenalan Bahasa C++ (Bagian Pertama)."