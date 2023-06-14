# Flexi.db: Veritabanınızı Kolayca Yönetin

FlexiDB, verilerinizi farklı formatlarda depolamak ve yönetmek için esnek bir Node.js modülüdür. Bu modül sayesinde JSON, MySQL, BSON ve YAML gibi veritabanı formatlarını destekleyerek projenize uygun veri depolama seçenekleri sunar.

## Özellikler

- JSON, MySQL, BSON ve YAML formatlarını destekler.
- Verilerinizi kolayca kaydetme, getirme ve silme işlemlerini gerçekleştirir.
- Basit ve kullanıcı dostu bir API ile veri erişimi sağlar.
- Hızlı ve güvenilir performans sunar.
- Özelleştirilebilir yapıda olup, modülü ihtiyaçlarınıza göre genişletebilirsiniz.

## Kullanım Örneği

```javascript
const {FlexiDB} = require('flexidb');

// Örnek kullanım
const db = new FlexiDB('mydata.json', 'json'); 

/**
 BSON formatında veritabanı 
 const dbBson = new FlexiDB('mydata.bson', 'bson');
 **/

 /**
 YAML formatında veritabanı
const dbYaml = new FlexiDB('mydata.yaml', 'yaml');
 **/
 
 /**
Mysql formatında veritabanı 
const mysql = require('mysql'); // flexidb nin hemen altına yapıştırcan

const config = {
  host: 'localhost', // MySQL sunucusunun adresi
  port: 3306, // Bağlantı noktası
  user: 'kullaniciadi', // MySQL kullanıcı adı
  password: 'sifre', // MySQL kullanıcı şifresi
  database: 'veritabani', // Bağlanmak istediğiniz veritabanının adı
};

const connection = mysql.createConnection(config);

connection.connect((err) => {
  if (err) {
    console.error('Bağlantı hatası:', err);
  } else {
    console.log('MySQL sunucusuna bağlandı!');
    // Bağlantı başarılı bir şekilde kurulduğunda burada işlemlerinizi yapabilirsiniz.
  }
});
**/


// Veri oluşturma
db.create('name', 'Luppux');
db.create('age', 25);

// Veri okuma
console.log(db.read('name')); // 

// Veri güncelleme
db.update('age', 30);
console.log(db.read('age')); // 30

// Veri silme
db.delete('age');
console.log(db.read('age')); // undefined

// Veri sorgulama
const results = db.query((key, value) => value.includes('J'));
console.log(results); // [['name', 'Luppux']]


// MySQL bağlantısı kapatma
db.closeConnection();

// İndeksleme
db.createIndex('name');
const indexValues = db.getIndexValues();
console.log(indexValues); // ['Luppux']

// Transaksiyonlar
db.startTransaction();
db.set('name', 'Luppux');
db.set('age', 35);
db.commitTransaction();
console.log(db.read('name')); // Jane Smith
console.log(db.read('age')); // 35

// Veritabanı yedekleme ve geri yükleme
db.backup('backup.json');
db.restore('backup.json');
console.log(db.read('name')); // Luppux

// Diğer işlemler
db.createCollection('users'); // Yeni bir koleksiyon oluşturur
db.insert('users', { name: 'Alice', age: 30 }); // Koleksiyona yeni bir belge ekler
db.find('users', { age: { $gt: 25 } }); // Belirli bir koşula göre belgeleri bulur
db.updateOne('users', { name: 'Alice' }, { $set: { age: 31 } }); // Belirli bir belgeyi günceller
db.deleteOne('users', { name: 'Alice' }); // Belirli bir belgeyi siler
db.aggregate('users', [{ $group: { _id: '$age', count: { $sum: 1 } } }]); // Agregasyon işlemi yapar
// ...

```

# Yükleme 

- Modülü projenize eklemek için npm veya yarn paket yöneticisini kullanabilirsiniz.

```bash
npm install flexidb
```
veya
```bash
yarn add flexidb
```

# Daha Fazlası
Daha fazla bilgi için GitHub sayfamızı [!ziyaret edebilirsiniz.](https://github.com/Weatrixcik/FlexiDB)

- FlexiDB ile veritabanı işlemlerini kolaylaştırın ve projenizde verilerinizi güvenle yönetin.
