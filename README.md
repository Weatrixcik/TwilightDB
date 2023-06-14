# FlexiDB: Veritabanınızı Kolayca Yönetin

FlexiDB, verilerinizi farklı formatlarda depolamak ve yönetmek için esnek bir Node.js modülüdür. Bu modül sayesinde JSON, MySQL, BSON ve YAML gibi veritabanı formatlarını destekleyerek projenize uygun veri depolama seçenekleri sunar.

## Özellikler

- JSON, MySQL, BSON ve YAML formatlarını destekler.
- Verilerinizi kolayca kaydetme, getirme ve silme işlemlerini gerçekleştirir.
- Basit ve kullanıcı dostu bir API ile veri erişimi sağlar.
- Hızlı ve güvenilir performans sunar.
- Özelleştirilebilir yapıda olup, modülü ihtiyaçlarınıza göre genişletebilirsiniz.

## Kullanım Örneği

```javascript
const MyDatabase = require('mydatabase');

// JSON formatında veritabanı
const dbJson = new MyDatabase('mydata.json', 'json');

dbJson.set('name', 'John');
dbJson.set('age', 25);

console.log(dbJson.get('name')); // Çıktı: John
console.log(dbJson.get('age')); // Çıktı: 25
```

# Yükleme 

- Modülü projenize eklemek için npm veya yarn paket yöneticisini kullanabilirsiniz.

```bash
npm install flexi.db
```
veya
```bash
yarn add flexi.db
```

# Daha Fazlası
Daha fazla bilgi için GitHub sayfamızı [![ziyaret edebilirsiniz.](https://github.com/Weatrixcik/FlexiDB)]

- FlexiDB ile veritabanı işlemlerini kolaylaştırın ve projenizde verilerinizi güvenle yönetin.
