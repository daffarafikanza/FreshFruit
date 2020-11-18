# Fresh Fruit

Aplikasi sederhana ini adalah untuk Menambahkan Buah ke dalam Keranjang.

## Scope & Functionalities

- User dapat memilih atau menambahkan buah ke keranjang.
- Maksimal buah yang bisa ditambahkan hanya bisa 4 buah saja.
- User akan mendapatkan notif jika udah mencapai batas maksimal.

## How Does it Works?

- `Bucket.cs`, `BucketEventListener.cs`, `Fruit.cs`, `Seller.cs` Berada pada folder Konsep Model.

```csharp
namespace TheNextCar.Controller
{
    class DoorController
    {
        private Door door;
        private OnDoorChanged callbackOnDoorChanged;

        public DoorController(OnDoorChanged callbackOnDoorChanged)
        {
            this.callbackOnDoorChanged = callbackOnDoorChanged;
            this.door = new Door();
        }
```

## 2. model Door.cs
`model Door.cs` Berfungsi untuk fungsi door closed dan locked.

```csharp
namespace TheNextCar.Model
{
    class Door
    {
        private bool locked;
        private bool closed;

        public void close()
        {
            this.closed = true;
        }

        public void open()
        {
            this.closed = false;
        }

        public void activateLock()
        {
            this.locked = true;
        }

        public void unlock()
        {
            this.locked = false;
        }

        public bool isLocked()
        {
            return this.locked;
        }

        public bool isClosed()
        {
            return this.closed;
        }
    }
}
```

## 3. OnDoorChanged
`OnDoorChanged` berfungsi untuk mengganti fungsi Door dan DoorController.

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
