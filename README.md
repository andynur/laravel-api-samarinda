# LARAVEL SAMARINDA API (Application Programming Inteface)

[![Total Downloads](https://poser.pugx.org/novay/laravel-api-samarinda/d/total.svg)](https://packagist.org/packages/novay/laravel-api-samarinda)
[![Build Status](https://travis-ci.org/novay/laravel-api-samarinda.svg?branch=master)](http://travis-ci.org/novay/laravel-api-samarinda)
[![Latest Stable Version](https://poser.pugx.org/novay/laravel-api-samarinda/v/stable.svg)](https://packagist.org/packages/novay/laravel-api-samarinda)
[![Latest Unstable Version](https://poser.pugx.org/novay/laravel-api-samarinda/v/unstable.svg)](https://packagist.org/packages/novay/laravel-api-samarinda)
[![License](https://poser.pugx.org/novay/laravel-api-samarinda/license.svg)](https://raw.githubusercontent.com/novay/laravel-auth/LICENSE)

Package Laravel untuk memudahkan developer lokal khususnya para programmer di Samarinda dalam pemanfaatan API yang disediakan oleh Pemerintah Kota Samarinda.

- [Tentang](#tentang)
- [Requirements](#requirements)
- [Instalasi](#instalasi)
    - [Laravel 5.5 Ke Atas](#laravel-5.5-ke-atas)
    - [Laravel 5.4 Ke Bawah](#laravel-5.4-ke-bawah)
	- [Konfigurasi](#konfigurasi)
- [Panduan Penggunaan](#panduan-penggunaan)
- [Credit](#credit)
- [License](#license)

### Tentang
Untuk menjawab seluruh kebutuhan para developer lokal akan data, Pemerintah Kota Samarinda membuat sebuah Package Laravel untuk memudahkan developer lokal khususnya para programmer di Samarinda dalam pemanfaatan API yang disediakan oleh Pemerintah Kota Samarinda.

### Requirements
* [Composer](https://getcomposer.org/download)
* [Laravel 5.3, 5.4 or 5.5+](https://laravel.com/docs/installation)

### Instalasi

##### Laravel 5.5 Ke Atas
1. Jalankan perintah berikut melalui terminal (Linux & Mac) atau Command Prompt (Windows):

```bash
    composer require novay/laravel-api-samarinda
```

* SELESAI. Package ini menggunakan fitur 'auto discovery'.

##### Laravel 5.4 Ke Bawah
2. Tambahkan baris berikut pada file `config/app.php` pada masing-masing lokasi `providers` dan `aliases`:

```php
    'providers' => [
        'Novay\ApiSamarinda\ApiSamarindaServiceProvider::class', 
    ];

    'aliases' => [
        'ApiSamarinda' => 'Novay\ApiSamarinda\Facade::class'
    ];
```

##### Konfigurasi
3. Tambahkan beberapa settingan berikut kedalam file `.env` Anda:

```
    # These Samarinda API Settings, SMR_TOKEN are required.
	SMR_API='http://api.samarindakota.go.id/api'
	SMR_API_VERSION='v1'
	SMR_TOKEN='API_KEY_ANDA'
```

4. Buat akun dan dapatkan `TOKEN` Anda di [http://api.samarindakota.go.id](http://api.samarindakota.go.id). 

### Panduan Penggunaan

Sementara to the point begini dulu ya.

```php
    # DEVELOPER RESMI
	return ApiSamarinda::penduduk();
	return ApiSamarinda::pendudukByNik(6403050611910002);

	# DEVELOPER
	return ApiSamarinda::url('GET', 'http://api.samarindakota.go.id/api/v1/sekolah?with=both&jenjang=smk');

	return ApiSamarinda::provinsi();
	return ApiSamarinda::provinsi($paginate = 15);
	return ApiSamarinda::provinsiById($id_provinsi);
	return ApiSamarinda::provinsiByNama('kalimantan timur');

	return ApiSamarinda::kota();
	return ApiSamarinda::kota($paginate = 15);
	return ApiSamarinda::kotaById(1103);
	return ApiSamarinda::kotaByNama('samarinda');
	return ApiSamarinda::kotaByIdProvinsi(64);
	
	return ApiSamarinda::kecamatan();
	return ApiSamarinda::kecamatan($paginate = 15);
	return ApiSamarinda::kecamatanById(1101030);
	return ApiSamarinda::kecamatanByNama('redeb');
	return ApiSamarinda::kecamatanByIdKota(6472);
	
	return ApiSamarinda::kelurahan();
	return ApiSamarinda::kelurahan($paginate = 15);
	return ApiSamarinda::kelurahanById(1101010007);
	return ApiSamarinda::kelurahanByNama('redeb');
	return ApiSamarinda::kelurahanByIdKecamatan(6405060);
	
	return ApiSamarinda::sekolah();
	return ApiSamarinda::sekolah('kecamatan');
	return ApiSamarinda::sekolah('kelurahan');
	return ApiSamarinda::sekolah('both');
	
	return ApiSamarinda::sekolahByJenjang('sd');
	return ApiSamarinda::sekolahByJenjang('smp');
	return ApiSamarinda::sekolahByJenjang('sma');
	return ApiSamarinda::sekolahByJenjang('smk');
	
	return ApiSamarinda::sekolahByStatus('swasta');
	return ApiSamarinda::sekolahByStatus('negeri');
	
	return ApiSamarinda::sekolahByKelurahan(6472030002);
	
	return ApiSamarinda::sekolahByKecamatan(6472022);

```

### Credit
* Pemerintah [Kota Samarinda](https://samarindakota.go.id).

## License
API (Application Programming Interface) Samarinda is licensed under the MIT license for both personal and commercial products. Enjoy!