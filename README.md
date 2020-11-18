# Fresh Fruit

Aplikasi sederhana ini adalah untuk Menambahkan Buah ke dalam Keranjang.

## Scope & Functionalities

- User dapat memilih atau menambahkan buah ke keranjang.
- Maksimal buah yang bisa ditambahkan hanya bisa 4 buah saja.
- User akan mendapatkan notif jika udah mencapai batas maksimal.

## How Does it Works?

- Di dalam folder Model, terdapat 4 class yaitu `Bucket.cs`, `BucketEventListener.cs`, `Fruit.cs`, `Seller.cs`.

- `model Door.cs` Berfungsi untuk fungsi door closed dan locked.

- `OnDoorChanged` berfungsi untuk mengganti fungsi Door dan DoorController.

```csharp
public DoorController(OnDoorChanged callbackOnDoorChanged)
        {
            this.callbackOnDoorChanged = callbackOnDoorChanged;
            this.door = new Door();
        }

        public void close()
        {
            this.door.close();
            this.callbackOnDoorChanged.onDoorOpenStateChanged("CLOSED", "door closed");
        }
```
