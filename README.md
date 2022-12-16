## RetailStoreAPI projesine ait detaylar aşağıda verilmiştir.

**GetAmount** metodu ile kullanıcı ve ürün listesi bilgileri alınır ve toplam tutar, toplam ödenecek tutar, toplam indirim tutarı, yüzde indirim tutarı, indirim tutarı ve yüzde indirime giren ürün listesi bilgileri verilir.

<br/>

Burada indirimler hesaplanırken aşağıdaki kurallar geçerli olacaktır:

- Kullanıcı mağaza çalışanı ise % 30 indirim alır.
- Kullanıcı, mağazanın bir üyesi ise % 10 indirim alır.
- Kullanıcı 2 yılı aşkın süredir müşteriyse % 5 indirim alır.
- Faturadaki her 100 Dolar için 5 Dolarlık bir indirim alır(örneğin, 990 Dolar için, indirim olarak 45 Dolar alınır).
- Yüzde bazlı indirimler bakkaliye ürünlerinde uygulanılmaz.
- Bir kullanıcı, bir faturada yüzdeye dayalı indirimlerden yalnızca birini alabilir.
			
**GetAmount** metoduna giderken kullanılacak model **RequestModelDTO** modelidir.
<br/>
RequestModelDTO modeline ait property'ler ve açıklamaları aşağıda verilmiştir.

| Property Name | Description | Nullable |
| :---          | :---        | :---: |
| UserDTO | İşlem yapılacak kullanıcı bilgilerini tutar. | - |
| ListProductDTO | İşlem yapılacak ürün listesini tutar. | - |

<br/>

UserDTO modeline ait property'ler ve açıklamaları aşağıda verilmiştir.

| Property Name | Description | Nullable |
| :---          | :---        | :---: |
| UserName | Müşterinin kullanıcı adını tutar. | + |
| Name | Müşterinin adını tutar. | + |
| Surname | Müşterinin soyadını tutar. | + |
| EMail | Müşterinin e-mail adresini tutar. | + |
| MembershipDate | Müşterinin ilk işleminin tarihini tutar. | - |
| IsEmployee | Müşterinin mağaza çalışanı olup olmadığı bilgisini tutar. | - |
| IsMember | Müşterinin mağazanın üyesi olup olmadığı bigisini tutar. | - |

<br/>

ProductDTO modeline ait property'ler ve açıklamaları aşağıda verilmiştir.

| Property Name | Description | Nullable |
| :---          | :---        | :---: |
| Code | Ürün kodunu tutar. | + |
| Barcode | Ürün barkodunu tutar. | + |
| Name | Ürün adını tutar. | + |
| Detail | Ürün detay bilgisini tutar. | + |
| Quantity | Ürün miktarını tutar. | - |
| Price | Ürün fiyatını tutar. | - |
| IsGrocery | Ürünün bakkaliye ürünü olup olmadığı bilgisini tutar. | - |

<br/>

**GetAmount** metodunun çıktısı olarak kullanılan model **ResultModelDTO** modelidir.
<br/>
ResultModelDTO modeline ait property'ler ve açıklamaları aşağıda verilmiştir.

| Property Name | Description | Nullable |
| :---          | :---        | :---: |
| ListResultProductModel | Yüzde indirim uygulanan ürün listesini tutar. | - |
| TotalAmount | Toplam tutar bilgisini tutar. | - |
| TotalCost | Toplam ödenecek tutar bilgisini tutar.| - |
| TotalDiscount | Toplam indirim tutarı bilgisini tutar. | - |
| PercentDiscount | Yüzde indirim tutarı bilgisini tutar.| - |
| Discount | Dip tutar indirimi tutarı bilgisini tutar.| - |
| DiscountDetail | Yapılan indirimin açıklamasını tutar. | - 

ResultProductModelDTO modeline ait property'ler ve açıklamaları aşağıda verilmiştir.

| Property Name | Description | Nullable |
| :---          | :---        | :---: |
| ProductName | Ürün adı tutar. | + |
| IsGrocery | Ürünün bakkaliye ürünü olup olmadığı bilgisini tutar. | - |
| ProductQuantity | Ürün miktarını tutar. | - |
| ProductPrice | Ürün fiyatını tutar. | - |

<br/>

**GetAmount** metodunun çalıştırılması için örnek json örneği ***Request.json*** dosyasında paylaşılmıştır. Burada swagger üzerinden yapılan deneme için ekran görüntüsü ***Request.png*** görselinde görülebilir.

<br/>

**GetAmount** metodunun çalıştırılması sonucu oluşan çıktı ***Response.json*** dosyasında paylaşılmıştır. Burada swagger üzerinden yapılan deneme için ekran görüntüsü ***Response.png*** görselinde görülebilir.
