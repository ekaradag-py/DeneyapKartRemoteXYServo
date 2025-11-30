<div align="center">

  <img src="https://raw.githubusercontent.com/RemoteXY/RemoteXY-Arduino-Library/master/extras/logo.png" alt="Logo" width="100" />
  
  <h1>🤖 Deneyap Kart: 4 Eksenli Robot Kol Kontrolü</h1>
  
  <p>
    RemoteXY ve Deneyap Kart kullanarak WiFi üzerinden kablosuz robotik kontrol sistemi.
    <br />
    <strong>İnternet Yok, Gecikme Yok, Tam Kontrol!</strong>
  </p>

  <p>
    <img src="https://img.shields.io/badge/Donanım-Deneyap_Kart-red?style=for-the-badge" alt="Deneyap Kart" />
    <img src="https://img.shields.io/badge/Yazılım-Arduino_IDE-00979D?style=for-the-badge&logo=arduino&logoColor=white" alt="Arduino IDE" />
    <img src="https://img.shields.io/badge/App-RemoteXY-blue?style=for-the-badge" alt="RemoteXY" />
    <img src="https://img.shields.io/badge/Lisans-MIT-green?style=for-the-badge" alt="License" />
  </p>
  
  <p align="center">
    <a href="#-özellikler">Özellikler</a> •
    <a href="#-devre-şeması">Devre Şeması</a> •
    <a href="#-kurulum">Kurulum</a> •
    <a href="#-uyarılar">Uyarılar</a>
  </p>
</div>

---

## 🌟 Özellikler

Bu proje, Deneyap Kart'ın **Access Point (AP)** özelliğini kullanarak harici bir modeme ihtiyaç duymadan kendi yerel ağını oluşturur.

* 📡 **Kablosuz Kontrol:** Kendi WiFi ağını yayar, her yerde çalışır.
* 🦾 **4 Eksen Yönetimi:** Robot kollar veya 4 tekerlekli araçlar için tam uyumludur.
* 📱 **Mobil Arayüz:** iOS ve Android uyumlu **RemoteXY** ile görsel joystick deneyimi.
* ⚡ **Stabilite:** `RemoteXY_delay` fonksiyonu ile bağlantı kopmalarına karşı korumalı.

## 🛠️ Gereksinimler

| Bileşen | Miktar | Açıklama |
| :--- | :---: | :--- |
| **Deneyap Kart** | 1 | veya Deneyap Kart 1A, Deneyap Mini |
| **Servo Motor** | 4 | SG90, MG90S veya MG995 |
| **Güç Kaynağı** | 1 | **Harici 5V** (Pil veya Adaptör) |
| **Jumper Kablo** | 20+ | Erkek-Erkek / Dişi-Erkek |

## 🔌 Devre Şeması

Motorların sinyal uçlarını Deneyap Kart'a aşağıdaki tabloya göre bağlayın.

| Servo No | İşlev (Örnek) | Deneyap Pin | PWM Kanalı |
| :---: | :--- | :---: | :---: |
| **1** | Taban (X Ekseni) | `D8` | 0 |
| **2** | İleri-Geri (Y Ekseni) | `D4` | 1 |
| **3** | Yukarı-Aşağı | `D5` | 2 |
| **4** | Kıskaç | `D6` | 3 |

> [!WARNING]
> **⚠️ KRİTİK GÜÇ UYARISI**
>
> Servo motorları **ASLA** doğrudan Deneyap Kart'ın 3.3V veya 5V pininden beslemeyiniz!
> * 4 motor aynı anda çalıştığında yüksek akım çeker ve kartın regülatörünü yakabilir.
> * **Mutlaka harici bir güç kaynağı kullanın.**
> * Güç kaynağının **GND (-) ucu** ile Deneyap Kart'ın **GND ucunu** birleştirmeyi (ortak şase) unutmayın.

## 📱 Kurulum ve Kullanım

### 1. Yazılımı Yükleyin
`deneyapKartRemoteXYServo.ino` dosyasını Arduino IDE ile açın. Gerekli kütüphanelerin (Deneyap ve RemoteXY) yüklü olduğundan emin olup kodu karta yükleyin.

### 2. Uygulamayı Hazırlayın
Telefonunuza **RemoteXY** uygulamasını indirin:
* [App Store (iOS)](https://apps.apple.com/us/app/remotexy/id1168130280)
* [Google Play (Android)](https://play.google.com/store/apps/details?id=com.shevauto.remotexy.free&pcampaignid=web_share)

### 3. Bağlantıyı Kurun
Telefonunuzun WiFi ayarlarına gidin ve aşağıdaki ağa bağlanın:

```text
SSID:   RemoteXY
Şifre:  12345678
