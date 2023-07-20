<div align="center">
<h1>
  FLO Müşteri Segmentasyonu
</h1>

<h4>
    <img alt="FLO" src="https://github.com/bekowashere/rfm-flo/blob/main/src/flo1.png?raw=true">
</h4>
</div>

<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#kullanılan-teknojiler">Kullanılan Teknolojiler</a>
    </li>
    <li>
      <a href="#i̇ş-problemi">İş Problemi</a>
    </li>
    <li><a href="#veri-seti-hikayesi">Veri Seti Hikayesi</a></li>
    <li>
      <a href="#proje-görevleri">Proje Görevleri</a>
      <ul>
        <li><a href="#görev-1-veriyi-anlama-ve-hazırlama">GÖREV 1</a></li>
        <li><a href="#görev-2-rfm-metriklerinin-hesaplanması">GÖREV 2</a></li>
        <li><a href="#görev-3-rf-skorunun-hesaplanması">GÖREV 3</a></li>
        <li><a href="#görev-4-rf-skorunun-segment-olarak-tanımlanması">GÖREV 4</a></li>
        <li><a href="#görev-5-aksiyon-zamanı">GÖREV 5</a></li>
      </ul>
    </li>
  </ol>
</details>

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

- **Adım 1:** **Recency**, **Frequency** ve **Monetary** tanımlarını yapınız.
- **Adım 2:** Müşteri özelinde Recency, Frequency ve Monetary metriklerini hesaplayınız.
- **Adım 3:** Hesapladığınız metrikleri rfm isimli bir değişkene atayınız.
- **Adım 4:** Oluşturduğunuz metriklerin isimlerini recency, frequency ve monetary olarak değiştiriniz.

**Dikkat!** recency değerini hesaplamak için analiz tarihini maksimum tarihten 2 gün sonrası seçebilirsiniz.

### GÖREV 3: RF Skorunun Hesaplanması

- **Adım 1:** Recency, Frequency ve Monetary metriklerini **qcut** yardımı ile 1-5 arasında skorlara çeviriniz.
- **Adım 2:** Bu skorları **recency_score**, **frequency_score** ve **monetary_score** olarak kaydediniz.
- **Adım 3:** recency_score ve frequency_score'u tek bir değişken olarak ifade ediniz ve **RF_SCORE** olarak kaydediniz.

### GÖREV 4: RF Skorunun Segment Olarak Tanımlanması

- **Adım 1:** Oluşturulan RF skorları için segment tanımlamaları yapınız.
- **Adım 2:** Aşağıdaki **seg_map** yardımı ile skorları segmentlere çeviriniz.

```python
# RFM isimlendirmesi
seg_map = {
    r'[1-2][1-2]': 'hibernating',
    r'[1-2][3-4]': 'at_Risk',
    r'[1-2]5': 'cant_loose',
    r'3[1-2]': 'about_to_sleep',
    r'33': 'need_attention',
    r'[3-4][4-5]': 'loyal_customers',
    r'41': 'promising',
    r'51': 'new_customers',
    r'[4-5][2-3]': 'potential_loyalists',
    r'5[4-5]': 'champions',
}
```

### GÖREV 5: Aksiyon Zamanı!

- **Adım 1:** Segmentlerin recency, frequency ve monetary ortalamalarını inceleyiniz.
- **Adım 2:** RFM analizi yardımıyla aşağıda verilen 2 case için ilgili profildeki müşterileri bulun ve müşteri id'lerini csv olarak kaydediniz.
    - **a.** FLO, bünyesine yeni bir kadın ayakkabı markası dahil ediyor. Dahil ettiği markanın ürün fiyatları genel müşteri tercihlerinin üstünde. Bu nedenle markanın tanıtımı ve ürün satışları için ilgilenecek profildeki müşterilerle özel olarak iletişime geçmek isteniliyor. Sadık müşterilerinden (champions, loyal_customers) ve kadın kategorisinden alışveriş yapan kişiler özel olarak iletişim kurulacak müşteriler. Bu müşterilerin id numaralarını csv dosyasına kaydediniz.
    - **b.** Erkek ve Çocuk ürünlerinde %40'a yakın indirim planlanmaktadır. Bu indirimle ilgili kategorilerle ilgilenen geçmişte iyi müşteri olan ama uzun süredir alışveriş yapmayan kaybedilmemesi gereken müşteriler, uykuda olanlar ve yeni gelen müşteriler özel olarak hedef alınmak isteniyor. Uygun profildeki müşterilerin id'lerini csv dosyasına kaydediniz.