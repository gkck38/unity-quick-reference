# 🕹️ Player Movement (2D & 3D)

Oyuncu hareketi Unity'de en temel şeylerden biridir. Ama her döndüğümde unuttuğum için bu dosya burada.  
Hem 2D hem 3D sistemleri, Rigidbody kullanım farkları ve hatırlatma notları içerir.

---

## 🚶‍♂️ Basic 3D Movement (Input.GetAxis)

```csharp
public class PlayerMovement : MonoBehaviour
{
    public float speed = 5f;

    void Update()
    {
        float h = Input.GetAxis("Horizontal");
        float v = Input.GetAxis("Vertical");

        Vector3 move = new Vector3(h, 0f, v);
        transform.Translate(move * speed * Time.deltaTime);
    }
}

📌 Notlar:

* Input.GetAxis() yumuşak geçiş sağlar (-1 → 0 → 1)

* Translate() pozisyonu doğrudan değiştirir, fizik motoru işlemez.

* Zıplama, gravity, rigidbody yok → sadece hareket.


🎮 2D Movement (Rigidbody2D ile)

public class PlayerMovement2D : MonoBehaviour
{
    public float moveSpeed = 5f;
    private Rigidbody2D rb;
    private Vector2 moveInput;

    void Start()
    {
        rb = GetComponent<Rigidbody2D>();
    }

    void Update()
    {
        moveInput.x = Input.GetAxisRaw("Horizontal");
        moveInput.y = Input.GetAxisRaw("Vertical");
    }

    void FixedUpdate()
    {
        rb.MovePosition(rb.position + moveInput * moveSpeed * Time.fixedDeltaTime);
    }
}


📌 Notlar:

* Input.GetAxisRaw → instant geçiş sağlar (ani tepki)

* FixedUpdate() → fizik hesaplamaları için doğru yer

* MovePosition() → Rigidbody ile yumuşak hareket


⚠️ Yaygın Hatalar
❌ Rigidbody varken transform.position kullanmak
    Bu, physics engine ile çakışır ve jitter yapar.

❌ Script’te class adı ≠ dosya adı
    Unity derlemez ve script gözükmez

❌ Collider eklememek
    Hareket eder ama hiçbir şeye çarpmaz, içinden geçer

❌ Rigidbody varken Update() içinde pozisyonu değiştirmek
    Fizik sistemine aykırı olur



📚 Ekstra Bilgi
* Zıplama eklemek için: rb.AddForce(Vector2.up * jumpPower, ForceMode2D.Impulse);

* Gravity kapatmak için: rb.gravityScale = 0;

* Dönüş engellemek için: rb.freezeRotation = true;

* Mobile için: Input.GetTouch, Input.acceleration kullanılır


🧾 Bu dosya temel hareketleri hızlı hatırlamak için oluşturuldu.
Zamanla joystick, dokunmatik kontroller, yeni input system örnekleri de eklenecek.