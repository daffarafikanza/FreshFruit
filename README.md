# Fresh Fruit

Aplikasi sederhana ini adalah untuk Menambahkan Buah ke dalam Keranjang.

## Scope & Functionalities

- User dapat memilih atau menambahkan buah ke keranjang.
- Maksimal buah yang bisa ditambahkan hanya bisa 4 buah saja.
- User akan mendapatkan notif jika udah mencapai batas maksimal.

## How Does it Works?

- Di dalam folder Model, terdapat 4 class yaitu `Bucket.cs`, `BucketEventListener.cs`, `Fruit.cs`, `Seller.cs`.

- `MainWindow.xaml` Berfungsi untuk menampilkan program ini.

- Di dalam folder Controller, terdapat class `BucketController.cs`.

Diawali dengan Method `MainWindow` pada class `MainWindow.xaml.cs` dideklarasikan menjadi.....
```csharp
public MainWindow()
        {
            InitializeComponent();

            Bucket keranjangBuah = new Bucket(4);
            BucketController bucketController = new BucketController(keranjangBuah, this);

            toni = new Seller("Toni", bucketController);

            listBoxBucket.ItemsSource = keranjangBuah.findAll();
        }
```
