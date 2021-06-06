# Praktikum 10 - PHP OOP - Pemrograman Web
```
Veno Setyoaji Wiratama
311910363
TI.19.A.2
Universitas Pelita Bangsa
```

## LANGKAH 1
### Buka XAMPP lalu jalakan Apache dan MySQL
![LANGKAH 1](https://user-images.githubusercontent.com/22215113/120921755-5aee9280-c6ef-11eb-9764-06d46fef4208.png)

## LANGKAH 2
### Buat file `lab10_php_OOP` pada root directory web server `(d:\xampp\htdocs)`
![LANGKAH 2](https://user-images.githubusercontent.com/22215113/120921774-76f23400-c6ef-11eb-9e73-84d0b2807b2c.png)

## LANGKAH 3
### Buat file baru dengan nama `mobil.php` pada folder `(d:\xampp\htdocs\lab9_php_modular)`.
* Ini adalah contoh PHP OOP sederhana, membuat Class dan memanggil Class

* Coding
```
<?php
/**
* Program sederhana pendefinisian class dan pemanggilan class.
**/

class Mobil
{
    private $warna;
    private $merk;
    private $harga;

    public function __construct()
    {
    $this->warna = "Biru";
    $this->merk = "BMW";
    $this->harga = "10000000";
    }

    public function gantiWarna ($warnaBaru)
    {
    $this->warna = $warnaBaru;
    }

    public function tampilWarna ()
    {
    echo "Warna mobilnya : " . $this->warna;
    }
}
// membuat objek mobil
$a = new Mobil();
$b = new Mobil();

// memanggil objek
echo "<b>Mobil pertama</b><br>";
$a->tampilWarna();
echo "<br>Mobil pertama ganti warna<br>";
$a->gantiWarna("Merah");
$a->tampilWarna();

// memanggil objek
echo "<br><b>Mobil kedua</b><br>";
$b->gantiWarna("Hijau");
$b->tampilWarna();

?>
```
![LANGKAH 3 coding 1](https://user-images.githubusercontent.com/22215113/120921825-d05a6300-c6ef-11eb-9a49-b9b66bd8c2cf.png)
![LANGKAH 3 coding 2](https://user-images.githubusercontent.com/22215113/120921827-d2242680-c6ef-11eb-8540-6f4ca4527891.png)
* Hasil
![LANGKAH 3 hasil](https://user-images.githubusercontent.com/22215113/120921832-dd775200-c6ef-11eb-9536-34383c409980.png)

## LANGKAH 4
### Buat file baru dengan nama `form.php` pada folder `(d:\xampp\htdocs\lab9_php_modular)`.
* form.php ini untuk Class

* Coding
```
<?php
/**
* Nama Class: Form
* Deskripsi: CLass untuk membuat form inputan text sederhana
**/

class Form
{
    private $fields = array();
    private $action;
    private $submit = "Submit Form";
    private $jumField = 0;

    public function __construct($action, $submit)
    {
    $this->action = $action;
    $this->submit = $submit;
    }
    
    public function displayForm()
    {
    echo "<form action='".$this->action."' method='POST'>";
    echo '<table width="100%" border="0">';
    for ($j=0; $j<count($this->fields); $j++) {
        echo "<tr><td align='right'>".$this->fields[$j]['label']."</td>";
        echo "<td><input type='text' name='".$this->fields[$j]['name']."'></td></tr>";
        }
        echo "<tr><td colspan='2'>";
        echo "<input type='submit' value='".$this->submit."'></td></tr>";
        echo "</table>";
    }

    public function addField($name, $label)
    {
        $this->fields [$this->jumField]['name'] = $name;
        $this->fields [$this->jumField]['label'] = $label;
        $this->jumField ++;
    }
}

?>
```
![LANGKAH 4 coding 1](https://user-images.githubusercontent.com/22215113/120922754-1d8d0380-c6f5-11eb-820d-cef6cfb6f1ad.png)
![LANGKAH 4 coding](https://user-images.githubusercontent.com/22215113/120921883-4068e900-c6f0-11eb-8d46-b6196491d6f8.png)

## LANGKAH 5
### Buat file baru dengan nama `form_input.php` pada folder `(d:\xampp\htdocs\lab9_php_modular)`.
* form_input.php ini untuk memanggil Class yg sudah dibuat tadi.

* Coding
```
<?php
/**
* Program memanfaatkan Program 10.2 untuk membuat form inputan sederhana.
**/

include "form.php";

echo "<html><head><title>Mahasiswa</title></head><body>";
$form = new Form("","Input Form");
$form->addField("txtnim", "Nim");
$form->addField("txtnama", "Nama");
$form->addField("txtalamat", "Alamat");
echo "<h3>Silahkan isi form berikut ini :</h3>";
$form->displayForm();
echo "</body></html>";

?>
```
![LANGKAH 5 coding](https://user-images.githubusercontent.com/22215113/120921986-d997ff80-c6f0-11eb-9c23-a576d4a69580.png)
* Hasil
![LANGKAH 5 hasil](https://user-images.githubusercontent.com/22215113/120921989-dc92f000-c6f0-11eb-8bcc-822a799b08b1.png)
