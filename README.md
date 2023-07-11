<div align="center">
<h1>
  FLO Müşteri Segmentasyonu
</h1>

<h4>
    <img alt="FLO" src="https://github.com/bekowashere/rfm-flo/blob/main/src/flo1.png?raw=true">
</h4>

</div>


## Kullanılan Teknojiler

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white) ![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)

## İş Problemi

Online ayakkabı mağazası olan FLO müşterilerini segmentlere ayırıp bu segmentlere göre pazarlama stratejileri belirlemek istiyor. Buna yönelik olarak müşterilerin davranışları tanımlanacak ve bu davranışlardaki öbeklenmelere göre gruplar oluşturulacak.

## Veri Seti Hikayesi

Veri seti FLO'dan son alışverişlerini 2020-2021 yıllarında OmniChannel (hem online hem offline alışveriş yapan) olarak yapan müşterilerin geçmiş alışveriş davranışlarından elde edilen bilgilerden oluşmaktadır.

| Değişken  | Tanım   |
|---|---|
|   **master_id**  | Eşsiz müşteri numarası |
|   **order_channel**  | Alışveriş yapılan platforma ait hangi kanalın kullanıldığı (Android, IOS, Desktop, Mobile) |
|   **last_order_channel**  | En son alışverişin yapıldığı kanal |
|   **first_order_date**  | Müşterinin yaptığı ilk alışveriş tarihi |
|   **last_order_date**  | Müşterinin yaptığı son alışveriş tarihi |
|   **last_order_date_online**  | Müşterinin online platformda yaptığı son alışveriş tarihi |
|   **last_order_date_offline**  | Müşterinin offline platformda yaptığı son alışveriş tarihi |
|   **order_num_total_ever_online**  | Müşterinin online platformda yaptığı toplam alışveriş sayısı |
|   **order_num_total_ever_offline**  | Müşterinin offline'da yaptığı toplam alışveriş sayısı |
|   **customer_value_total_ever_offline**  | Müşterinin offline alışverişlerinde ödediği toplam ücret  |
|   **customer_value_total_ever_online**  | Müşterinin online alışverişlerinde ödediği toplam ücret |
|   **interested_in_categories_12**  | Müşterinin son 12 ayda alışveriş yaptığı kategorilerin listesi |

## Proje Görevleri

### GÖREV 1: Veriyi Anlama ve Hazırlama

- **Adım 1:** flo_data_20K.csv verisini okuyunuz. Dataframe'in kopyasını oluşturunuz.
- **Adım 2:** Veri setinde aşağıdaki incelemeleri yapınız:
    - **a.** İlk 10 gözlem
    - **b.** Değişken isimleri
    - **c.** Betimsel istatistik
    - **d.** Boş değer
    - **e.** Değişken tipleri
- **Adım 3:** Omnichannel müşterilerin hem online'dan hemde offline platformlardan alışveriş yaptığını ifade etmektedir. Her bir müşterinin toplam alışveriş sayısı ve harcaması için yeni değişkenler oluşturunuz.
- **Adım 4:** Değişken tiplerini inceleyiniz. Tarih ifade eden değişkenlerin tipini date'e çeviriniz.
- **Adım 5:** Alışveriş kanallarındaki müşteri sayısının, toplam alınan ürün sayısının ve toplam harcamaların dağılımına bakınız.
- **Adım 6:** En fazla kazancı getiren ilk 10 müşteriyi sıralayınız.
- **Adım 7:** En fazla siparişi veren ilk 10 müşteriyi sıralayınız.
- **Adım 8:** Veri ön hazırlık sürecini fonksiyonlaştırınız.

### GÖREV 2: RFM Metriklerinin Hesaplanması

- **Adım 1:** **Recency, Frequency** ve **Monetary** tanımlarını yapınız.
- **Adım 2:** Müşteri özelinde Recency, Frequency ve Monetary metriklerini hesaplayınız.
- **Adım 3:** Hesapladığınız metrikleri rfm isimli bir değişkene atayınız.
- **Adım 4:** oluşturduğunuz metriklerin isimlerini recency, frequency ve monetary olarak değiştiriniz.

**Dikkat!** recency değerini hesaplamak için analiz tarihini maksimum tarihten 2 gün sonrası seçebilirsiniz.