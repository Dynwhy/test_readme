###### Dio Firmansyah
###### Kelas :XII RPL 1/22
# Modul 1
## 1. Lakukan proses instalasi framework laravel kedalam folder dengan nama masing-masing.

```
composer create-project laravel/laravel penjualan
```
# Modul 2
## Buatlah migration tabel kategori dengan menggunakan teknik yang telah di pelajari dalam modul ini,ikuti langkah langkah berikut :
## * **saran membuka fitur terminal pada VSCODE**
 # Langkah 1
 ## membuat tabel :
 ```
 php artisan make:migration create_produk_table
 ```
 *saran masukan diterminal VSCODE
 ## lalu ubah scriptnya sebagai berikut :
 ```
<?php

use Illuminate\Database\Migrations\Migration;
use Illuminate\Database\Schema\Blueprint;
use Illuminate\Support\Facades\Schema;

return new class extends Migration
{
    /**
     * Run the migrations.
     *
     * @return void
     */
    public function up()
    {
        Schema::create('kategori', function (Blueprint $table) {
            $table->id();
            $table->string('nama');
            $table->timestamps();
        });
    }

    /**
     * Reverse the migrations.
     *
     * @return void
     */
    public function down()
    {
        Schema::dropIfExists('kategori');
    }
};

```
# langkah 2
## buatlah file Seeder pada DataBase :
```
php artisan make:seeder produkTableSeeder
```
*saran masukan diterminal VSCODE
## lalu ubah script sebagai berikut:
```
<?php

namespace Database\Seeders;

use Illuminate\Database\Console\Seeds\WithoutModelEvents;
use Illuminate\Database\Seeder;
use DB;

class kategoriTableSeeder extends Seeder
{
    /**
     * Run the database seeds.
     *
     * @return void
     */
    public function run()
    {
        DB::table('kategori')->insert (array(
        [
            'nama' =>'Perlengkapan Sekolah',
        ],
        [
            'nama' =>'Komputer',
        ],
        [
            'nama' =>'Mouse',
        ],
        [
            'nama' =>'Accesories',
        ],
        [
            'nama' =>'Alat Tulis',
        ]
    ));
    }
}
```
## lalu buka file database/seeds lalu panggil data yang sudah dibuat sebagai berikut :
```
<?php

namespace Database\Seeders;

// use Illuminate\Database\Console\Seeds\WithoutModelEvents;
use Illuminate\Database\Seeder;

class DatabaseSeeder extends Seeder
{
    /**
     * Seed the application's database.
     *
     * @return void
     */
    public function run()
    {
        $this->call(kategoriTableSeeder::class);
       
    }
}
```
## terus cek di fitur terminal VSCODE
```
php artisan db:seed
```
selesailah tugas membuat tabel Kategori tersebut.
# ***SEKIAN TERIMA KASIH :)***
