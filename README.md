# Typescript

## Typescript Nedir ?

- TypeScript, JavaScript'in üst kümesidir. JavaScript'in sıkıntılı yanlarını önlemek için geliştirilmiştir.
- Typescript, Javascript'in üst kümesidir. *(super set)* **Super Set:** Programlamada "super set", bir veri tipinin veya bir sınıfın başka bir veri tipinin veya sınıfın tüm özelliklerini içerdiği anlamında kullanılır.
- JavaScript yorumlamalıdır ve derleme aşaması yoktur. Bu nedenle, hata tespiti yapılamaz ve hata varsa tüm kodun gözden geçirilmesi gerekir. TypeScript dönüştürücüsü, derleme (compile-time) aşamasında hata denetimi yapar ve bu soruna çözüm getirir. Javascript çalıştırma aşamasında (run-time) hataları gösterir.
- Typescript’in asıl çıkma amacı aslında Javascript’in sıkıntılı yanlarından bizi kurtarak büyük ölçekli uygulamalar geliştirmemizi sağlamaktır.
- Typescript, Javascript'in syntax'ını kullanır buna ek olarakda Tipleri destekler.
- TypeScript JavaScript'e gelecek olan yeni özellikleri şimdiden destekler. Bu da yeni özelliklerin tarayıcılar (ya da diğer ortamlar) tarafından tamamen desteklenmese bile kullanabileceğiniz anlamına gelir.


Typescript browser ‘larda çalışmaz, Typescript ile yazılan kod Typescript Compiler ile javascript diline çevrilir (compiler) ve çalıştırılır.

## TypeScript ve JavaScript Arasında Farklar Nelerdir?

- JavaScript, etkileşimli web sayfaları oluşturmanıza yardımcı olan bir betik dilidir, Typescript ise JavaScript’in bir üst kümesidir.
- TypeScript, nesne yönelimli bir programlama dilidir, JavaScript ise betik dildir.
- TypeScript, statik veri tipine sahip bir programlama dilidir, JavaScript ise dinamik veri tipine sahiptir.

## Typescript ne zaman tercih edilmeli ?

1. **Büyük ve karmaşık projeler:** Özellikle büyük ve karmaşık projelerde, JavaScript ile yazılan kodun yönetimi zorlaşabilir. TypeScript'in statik tür sistemine sahip olması, hataların daha erken keşfedilmesine ve daha sağlam bir kod tabanı oluşturulmasına yardımcı olabilir.
2. **Ekibin büyüklüğü:** Büyük ekiplerle çalışırken, herkesin yazdığı kodu anlamak ve değiştirmek zor olabilir. TypeScript, kod tabanını belgeleme ve daha anlaşılır hale getirme konusunda yardımcı olabilir.
3. **Uzun ömürlü projeler:** Bir projenin uzun ömürlü olması durumunda, projenin zaman içindeki değişikliklerini takip etmek ve güncellemek önemli olabilir. TypeScript, büyük bir proje üzerinde yapılan değişikliklerin sonuçlarını daha iyi anlayabilmeyi sağlar.
4. **Daha fazla güvenlik ihtiyacı:** Özellikle güvenlik açısından hassas uygulamalar veya kritik işlevlere sahip projelerde, TypeScript'in statik tür sistemi, hataların erken aşamalarda tespit edilmesine yardımcı olabilir.
5. **Kütüphaneler ve framework'ler:** TypeScript, bazı popüler kütüphaneler ve framework'ler tarafından doğrudan desteklenmektedir. Örneğin, Angular framework'ü TypeScript üzerine kuruludur ve React ve Vue.js gibi diğer kütüphaneler de TypeScript'i destekler.
6. **Entegrasyon kolaylığı:** TypeScript, JavaScript kodlarına kolayca entegre edilebilir. Mevcut bir JavaScript projesinin TypeScript'e geçirilmesi zaman alsa da, TypeScript dosyalarını yavaş yavaş eklemek ve daha sonra projeyi tamamen TypeScript'e dönüştürmek mümkündür.

## tsconfig.json

**`target`**: Hedef ECMAScript sürümünü belirtir (örn. **`"es5"`**, **`"es6"`**, **`"es2017"`**, vb.). Derlenen çıktı, belirtilen sürümdeki JavaScript'e uygun olacaktır.

```json
"target": "ES6",
```

**`module`**: Hangi modül sisteminin kullanılacağını belirtir (örn. `"CommonJS"`, **`"AMD"`**, **`"ES6"`**, vb.).

```json
"module": "ES6",
```

**`lib`**: Bu ayar, TypeScript derleyicisinin kullanılabilir kütüphane tanımlarını belirler. 
Örneğin, **`"es6"`**, **`"dom"`**, **`"esnext.asynciterable"`** gibi değerlerle kütüphaneleri ekleyebilirsiniz

```json
"lib": ["ES6", "DOM", "DOM.Iterable"],
```

**`exclude`**: Derleme işleminde hariç tutulacak dosya veya dizinleri belirtir. Kod yazarken hata göstermeye devam eder fakat npm run build (derleme) yaparken hataları görmezden gelir, diğer türlü build alırken hata varsa build işlemi gerçekleşmez.

```json
"exclude": ["src/kira.tsx"],
```

**`include`**: Derleme işleminde dahil edilecek dosya veya dizinleri belirtir. Genellikle **`*/*`** kullanarak tüm dosyaları ve alt dizinleri dahil edebilirsiniz.

```json
"include": ["src"],
```

**`skipLibCheck`** Bu ayar, kütüphane tanımlarını (**`.d.ts`** dosyalarını) denetleyip denetlemeyeceğini belirler. Büyük ve karmaşık bir proje çalışıyorsanız veya dışarıdan alınan kütüphaneleri kullanıyorsanız, bu denetimlerin derleme sürecini yavaşlatabileceği ve gereksiz hataların oluşabileceği durumlar olabilir.

```json
"skipLibCheck": true
```

**`strict`** : Katı tür denetimlerini etkinleştirir. Kodun hatasız ve güvenli olmasını sağlar.

```json
"strict": true,
```

**`noImplicitAny`** : Değişken veya fonksiyon dönüş değeri türleri belirtilmediğinde (**`any`** olarak varsayıldığında) hata oluşturur (**`true`**)

```json
"noImplicitAny": true
```

**`strictNullChecks`** : Sadece null ve undefied atamalarını uygun değişkenlere atayabilmeye izin verir. Tip uyumsuzluğundan kaynaklanabilecek olası hataları önlemek içindir. Örneğin, bir değişkenin türü **`number`** olabilirken, bu değişkene **`null`** veya **`undefined`** atamakta bir sorun olmaz.

```json
"strictNullChecks": true
```

**`sourceMap`**: Kaynak haritalarının oluşturulmasını (**`true`**) veya oluşturulmamasını (**`false`**) belirtir. Kaynak haritaları hata ayıklamayı kolaylaştırır.

```json
"sourceMap" : true
```

**`outDir`**: Derlenmiş çıktının nereye konulacağını belirtir.

```json
"outDir": "./dist"
```

**`extends`** Yapılandırma dosyalarını bölümlere ayırabilir ve birbirinden miras (extends) almasını sağlayabilirsiniz.

Temel yapılandırma dosyası: **`tsconfig.base.json`**

```json

{
  "compilerOptions": {
    "target": "es6",
    "module": "commonjs",
    "strict": true}
}
```

Diğer dosya: **`tsconfig.app.json`**

```json

{
  "extends": "./tsconfig.base.json",
  "compilerOptions": {
    "outDir": "./dist"
  },
  "include": ["src"]
}

```

**`files`** : Derleme işlemi sırasında dahil edilecek dosyaları belirler. Bu, projenizin yalnızca belirli dosyaların derlenmesini istediğiniz durumlarda kullanışlı olabilir.

```json
"files": [
    "app.tsx",
    "helpers/utility.tsx"
  ]
```

**`compilerOptions.paths`** : Modül yollarını kısaltmak ve modül tanımlarının yerini belirli kısaltmalara göre eşleştirmek için kullanılır. baseUrl ile birlikte kullanılır.

```json
"compilerOptions": {
    "target": "es6",
    "module": "commonjs",
    "baseUrl": "./src",
    "paths": {
      "@utils/*": ["utils/*"],
      "@models/*": ["app/models/*"]
 }
```

```json
import { add } from "@utils/math";
import { User } from "@models/user";
```

**`allowJs`** :TypeScript derleyicisine JavaScript dosyalarını (**`*.js`** uzantılı dosyaları) derleme işlemine dahil etme izni verir. Default false ‘dir. Özellikle mevcut bir projeyi TypeScript'e geçirirken veya TypeScript ve JavaScript dosyalarını aynı proje içinde kullanırken faydalı olabilir.

```json
"allowJs": false //dahil etmez /dafault)
```

**`checkJs`** : JavaScript dosyalarında (**`.js`** uzantılı dosyalarında) tür denetimi yapma izni verir. Derleme işlemi sırasında tür denetimini kontrol eder. allowJs ise dosyayı derleme işlemini dahil edip etmemeyi sağlar.

```json
"checkJs": false //kontrol etmez (default)
```

**`noEmit`** : Derleme sırasında çıktı dosyalarının üretilip üretilmeyeceğini kontrol eder. Yalnızca tür denetimi yapmak ve derleme sürecinde yalnızca hataları kontrol etmek istediğinizde ve çıktı dosyasına (yani derlenen .js dosyasına) ihtiyaç duymadığınızda kullanışlıdır."noEmit": true

```json
"noEmit": false //çıktı üretir (default)
```

**`noUnusedLocals` :** Kullanılmayan değişkenleri kontrol eder ve hata döndürür.

```json
noUnusedLocals : true //control et ve uyar
```

**`noUnusedParameters` :** Kullanılmayan fonksiyona gönderilen parametreleri kontrol eder.

```json
noUnusedParameters : true //control et ve uyar
```

`**allowImportingTsExtensions` :** Diğer .ts veya .tsx dosyalarını import edebilme izni verir. Genelde componentleri birbirleri arasında sürekli import ettiğimiz için bu ayarı hep true tutmalıyız. Default false.

```json
allowImportingTsExtensions : true //dosyaları import edebilirsin.
```

**`resolveJsonModule` :** Diğer .json dosyalarını import edebilme izni verir. Default false.

```json
resolveJsonModule : true //dosyaları import edebilirsin.
```

**`isolatedModules` :** Tüm .ts veya .tsx dosyaları nasıl parça parça ise o şekilde derlenip çıktı olarak .js dosyalarına dönüştürülür. Default false ‘dir yani componentlerinizi ayırsanız bile tek bir dosyada derler ve çıkarır.

```json
isolatedModules : true //her component kendi adında dosya ile çıkarılır.
```

### Typescript klasör yapısı

Projelerde tip dosyaları oluştururken genellikle dosya ismine “d” ifadesi koyulur. Kalıplaşmış kullanımdır.

```tsx
index.ts //Dosyaları dışarıya çıkarma ve erişim işlemleri.
Person.tsx //Componentin içeriği
person.d.ts //declaration tip dosyası (içerisinde type ve interface kavramları bulunur)
constants.ts //Asla değişmeyecek bazı belirlenmiş değerlerin olduğunu dosya.
```

### Object

```tsx
const person: {
        ad: string,
        yas: number,
        sehir: any,
        tarih: Date,
        check: boolean,
				dersNotlari: {},
        func: Function
    } = {
        ad: "Kaira",
        yas: 20,
        sehir: "Ankara",
        tarih: new Date(),
        check: true,
				dersNotlari: {matematik: 25, turkce: 74},
        func: () => {
            return 5
        }   
    }
```

### Array[]

```tsx
//Sadece string tipinde değer alabilir
const person: string[] = ["Hellow", "World"];

//Sadece string veya number tipinde değer alabilir.
const person: (string | number)[] = ["Hellow", "World",25];
```

### type

```tsx
type persontype = string | number[];
const person: persontype = "kaira"
const person: persontype = [12,44,28]
```

```tsx
type persontype = any[];
const person: persontype = ["john", {name: "kaira"}, [44, 44], () => console.log("okey")]
```

```tsx
type Cat = number;

type Dog = Cat;
let person: Dog = 2;
```

```tsx
type Dog = string;
type Cat = number;
let person: Dog | Cat = 2;
```

```tsx
type Dog = string;
type Cat = number;

type DogCat = Dog | Cat
let person: DogCat = 2;
let person: DogCat = 'John';

```

```tsx
type IPerson = () => number

const Person: IPerson = () => {
		return 25
}

type IPerson = (isim: string, yas: number) => number

const Person: IPerson = (isim,yas) => {
		return yas;
}
```

### interface

```tsx
interface PersonTypes {
        ad: string,
        yas: number,
        sehir: any,
        tarih: Date,
        check: boolean,
        func: Function,
        dersNotlari: {}
    }

const person: PersonTypes = {
        ad: "Kaira",
        yas: 20,
        sehir: "Ankara",
        tarih: new Date(),
        check: true,
        func: () => {
            return 5
        },
        dersNotlari: {matematik: 25, turkce: 74}
    }
```

```tsx
interface Dog {
	name: string
	age: number
}
interface Cat {
	name: string,
	gender: 'male' | 'female'
}
// & operatöründe 2 interface 'de olan değerlerin tümünü kullanmak zorundayız
type DogCat = Dog & Cat;
let person: DogCat = {name: 'Karabaş', age: 4, gender: 'male'};
```

```tsx
// person fonksiyonun geri dönüş değeri IPerson interfacenin isim adlı değeri 
// ile aynı yani string döndürecek.
interface IPerson {
  isim: string;
  yas: number;
}

const person = (): IPerson['isim'] => {
  return 'Kaira
}
```

```tsx
// Array 'lar için index değerlerini number ve key değerlerini string belirledik.
// indexler person[0] , person[1] şeklinde düşünülebilir. artık bu array içerisine
// sadece string değerler kabul edecektir.
interface IPerson {
  [index: number]: string
}

const person: IPerson = ['Kaira', 'katarina']
```

```tsx
interface IPerson {
	(): void
}

const person: IPerson = () => {
	console.log('Hellow');
}

interface IPerson {
	(a: number, b: number): number
}

const person: IPerson = (a,b) => {
	return a + b
}

```

```tsx
//Extends

interface IUser{
	no: number,
	isim: string
}

interface IPerson extends IUser{
	yas: number,
	sehir: string
}

const person1: IPerson = {
	no: 1,
	isim: 'Kaira',
	yas: 19,
	sehir: 'London'
}
```

### as

```tsx
const person: string = "Kaira";
const person = "Kaira" as string;
```

Tür güvenliğini korumak için tür dönüşümlerini ve **`as`** anahtar kelimesini olabildiğince az kullanmanızı, mümkünse tür çıkarımına dayalı bir yaklaşım benimsenmeli. (type, interface)

```tsx
type persontype = number[];

const person = [12, 24, "john"] as persontype // hatalı olduğu halde hata vermez.

const person: persontype = [12, 24, "john"]; // hatalı olduğunu belirtir, sağlıklıdır.
```

### Sabit değerler

```tsx
const sayilar: 25 | 12 | "John" = 12;

type persontype = 25 | 12 | "John"
const person: persontype = 12;
```

```tsx
type  PersonType = [string, string, number];
const person: PersonType = ["Kaira", "Katarina", 24]
```

```tsx
type  PersonType = [string, 25 | 24 | string[], number];
const person: PersonType = ["Kaira", **12**, 24] // error
const person: PersonType = ["Kaira", 24, 24] // true
const person: PersonType = ["Kaira", ["tt", "bb"], 24] // true
const person: PersonType = ["Kaira", ["tt", "bb", 12], 24] // true
```

### Fonksiyonlar

```tsx
// Geriye bir değer döndürmüyor ise tipi void
const func = () => { }
// Aynı şekilde void tipi
const func = () => { console.log("Hello"); }
// Bu fonksiyon geriye bir değer döndürdüğü için tipi otomatik number olur.
const func = () => { return 25; }
```

```tsx
// geriye bir değer döndürmeyeceğini belirtiyorum
function func(): void {
   console.log("Hello")
}

const func = () : void => {
   console.log("Hello")
}
```

```tsx
const func = (): number => {
	return 25
}

// geriye number döndürür veya hiçbir değer döndürmeyebilir
const func = (): void | number => {
	return 25
}

const func = ():(string | number)[] => {
	return [25,12,44,"John"]
}

function func(): [string, string, number] {
  return ["Kaira", "Katarina", 25];
}
```

```tsx
function func(): number {
  return 25;
}

let test: string = func() // error string bir değere number değer atayamazsın.
```

### Parametreler

```tsx
function func(text: string, repeat: number): void {
  for (let i = 1; i <= repeat; i++) {
    console.log(text);
  }
}
func("Hello Wrold", 4);
```

Aşağıdaki kodda 2 hata mevcut. İlki text parametresi aldığımız halde bunu kullanmamamız, ikinci olarak geri dönüş tipini number olarak belirttik fakat return metodu for döngüsü içerisinde yer aldığı için yani ana parantezin içerisinde return değeri olmadığı için geriye bir şey döndürmeme ihtimaline karşı typescript number tipine ek olarak undefined tipinide eklememizi istiyor.

```tsx
function func(text: string, repeat: number): number {
  for (let i = 1; i <= repeat; i++) {
    return 25; // return ifadesi döngüyü 1 kere çalıştırıp sonlandırır.
  }
}

function func(text: string, repeat: number): number {
  for (let i = 1; i <= repeat; i++) {
    console.log(text);
  }
	return 25; //artık geri dönüş tipinin number olduğunu kabul eder.
}
```

```tsx
//obje olarak paremetre almak
function func(parameters: { text: string, repeat: number }): number {
  const {text, repeat} = parameters;
  for (let i = 1; i <= repeat; i++) {
    console.log(text);
  }
  return 25;
}
```

### Opsiyonel parametreler

Opsiyonel parametreler, bir işlevin çağrıldığında isteğe bağlı parametreleri ifade etmek için kullanılır.

```tsx
	const func = (text : string, sayi?: number) => {
	console.log(text)
}

func("Hellow"); //sayi opsiyonel olduğu için belirtmesek 'de hata vermez.
```

### Normal fonksiyon ve arrow fonksiyon tiplendirme farkı

Normal fonksiyonları type ile tiplendiremeyiz çünkü type ‘da fonksiyon tipi tanımlarken arrow function tipinde tanımlıyoruz ve bunu normal fonksiyon kabul etmez. `=> string`

```tsx
type IPerson = (isim: string) => string

function Person(isim): IPerson{
	return isim;
}
```

Bunun çok sağlıklı olmayan bir çözümü vardır, bir fonksiyon tanımlarız ve bu fonksiyon da geriye yeni bir fonksiyon döndürür, en dıştaki fonksiyon parametre almaz, geriye döndürdüğü fonksiyon parametre alır. Typescript ilgili tanımlamaları otomatik yapar. Çağırırken fonksiyonun içerisindeki fonksiyona parametre veririz. `FunctionName()(’parametre’)`

```tsx
type IPerson = (isim: string) => string

function Person(): IPerson{

	return function(isim){
		return isim;
	}

}

Person()('Kaira')
```

Bu şekilde kullanmak zahmetli ve sağlıklı değildir bunun için `interface`  çözümdür.

### Partial (Obsiyonel Obje)

`Partial` metodu tüm değerlerin obsiyonel olacağını belirtir.

```tsx
// Aşağıdaki tanımlamada isim ve yas değerinin belirtilmesi zorunludur.
interface PersonTypes {
    isim: string;
    yas: number;
}
// Partial ile tüm değerlerin obsiyonel olabileceği yeni bir tip oluşturduk.
type OpsionelType = Partial<PersonTypes>;

const Person: OpsionelType {
		isim: 'Kaira'
}
```

```tsx
//key lerin sonuna "?" koyarak hangilerinin obsiyonel olabileceğini belirtilebiliriz.
interface PersonTypes {
    isim: string;
    yas?: number;
}

const Person: PersonTypes {
		isim: 'Kaira'
}
```

### Required

Opsiyonel olan değerlerde dahil tüm tipleri zorunlu kılar.

```tsx
interface IPerson {
	name?: string;
	age?: number;
}

const person: Required<Person> {
	name: 'Kaira',
	age: 24
}
```

### index signature - Objeye belirtilmemiş tip deki değerleri ekleyebilmek

Tip olarak tanımlanmamış değerlerin obje içerisine kabul edilebilmesi için [key: string]: <tip> şeklinde belirtilmesi gerekiyor. Aşağıda any tipinde her değeri kabul edeceğini belirttik.

```tsx
interface PersonTypes {
    isim: string;
    yas: number;

		[key: string]: any;
}

const Person: OpsionelType {
		isim: 'Kaira'
		yas: 25
		sehir: "İstanbul"
		ilce: "Bebek"
}
```

Ek olarak diğer tiplerde değer de kabul edebileceğini belirtebiliriz fakat **`önemli :`** any haricinde tip belirtirken kullanılan diğer tipleride belirtmek zorundayız. Aşağıda boolean bir değer alabileceğini belirttik fakat isim ve yas ‘ın tipinide yanına eklemek zorundayız.

```tsx
interface PersonTypes {
    isim: string;
    yas: number;

		[key: string]: string | number | boolean;
}

const Person: OpsionelType {
		isim: 'Kaira'
		yas: 25
		durum: true
}
```

### Record

Objelerde key ve value şeklinde tip atamaları yapmamızı sağlar. `Record<key , value>`
Herhangi bir özel key ve value belirtmeden sadece tip atamsı yaparak opsiyonel değerler üretebiliriz.

```tsx
const person: Record<string,number> = {
	yas: 25,
	sınıf: 3
}

const person: Record<string, boolean | number> = {
	yas: 25,
	check: true
}

const person: Record<string, {isim: string, yas?: number, check: boolean}> = {
	person1: {
		isim: 'kaira',
		yas: 19,
		check: true
	},
	person2: {
		isim: 'katarina',
		check: false
	},
}
```

### Omit

Belirli bir interfacede kullanmak istemediğimiz tip tanımlamalarını çıkararak geriye bir interface döndürür. `Omit<interfaceName, disableTypeName>`

```tsx
interface IPerson{
	name: string;
	age: number;
	date: Date;
}

const person : Omit<IPerson, 'date'> = {
	name: 'John',
	age: 21
}
```

### Pick

Omit in tersi olarak başka bir interface ‘de ki seçili tip veya tiplerin kullanılmasını ister.
`Omit<interfaceName, enabledTypeName>`

```tsx
interface IPerson {
  name: string;
  age: number;
  date: Date;
}

const person: Pick<IPerson, 'name' | 'age'> = {
  name: 'John',
  age: 21,
}
```

### Parameters

Belirli bir fonksiyonun tipini kopyalamamızı sağlar. Örneğin bir kütüphanede veya sizin başka bir yerde kullandığınız bir fonksiyon var, bu tip export edilmemiş veya nerede olduğunu bulamıyoruz. O zaman Parameters ile o fonksiyonun parametre tiplerini kopyalayabiliriz. 
`Parameters<typeof fonksiyonName>`

```tsx
const person = (isim: string, age: number) => {
	console.log("Hello");
}

type copytype = Parameters<typeof person>;

const person2: copytype = ['Kaira',24]
```

```tsx
//başka bir fonksiyona parametre olarak gönderme
const person = (isim: string, age: number) => {
	console.log("Hello");
}

type copytype = Parameters<typeof person>;

const person2 = (parameters: copytype) => {
	console.log("Hello");
}

person2(['kaira',24])
```

### ReturnType

Bir fonksiyonun geriye döndürdüğü tipi almamızı sağlar. `ReturnType<typeof functionName>`

```tsx
const myFunc = () => {
	return 25
}

const myFunc2 = () : ReturnType<typeof myFunc> => {
	return 12
}

// yeni bir tip oluşuturup kullanabiliriz.
type returnCopy = ReturnType<typeof myFunc>;

const myFunc2 = () : returnCopy  => {
	return 12
}

// bir nesneye atayabiliriz.
const person: returnCopy = 18; 
```

### enum

Sabit değerlere belirli açıklamalar ekleyerek kullanmamızı sağlar. Sabit değerlerin anlamlarını daha anlaşılır hale getirmek ve hatalı kullanımları engellemek için kullanışlıdır.
İnfo : Enum'lar JavaScript'te derlenirken nesne olarak temsil edilir, bu nedenle aşırı kullanımları performans sorunlarına yol açabilir. Büyük enumlar kullanırken dikkatli olunması önemlidir.

```tsx
// bir enum tanımlıyoruz ve ilk değere 1 atıyoruz ve enum otomatik olarak sıraası ile
// sonraki değerleri 2,3,4,5... şeklinde artarak değer atıyor.
enum ENUMdaily {
  Monday = 1,
  Tuesday,
  Wednesday,
  Thursday,
  Friday,
  Saturday,
  Sunday
}

// Bir fonksiyon tanımladık ve parametre olarak enum 'daki yani 1,2,3,4,5... değerleri
// alabileceğini söyledik.
  function getDayTR(day: ENUMdaily) {
    switch (day) {
      case ENUMdaily.Monday:
        return "Pazartesi";
      case ENUMdaily.Tuesday:
        return "Salı";
      case ENUMdaily.Wednesday:
        return "Çarşamba";
      case ENUMdaily.Thursday:
        return "Perşembe";
      case ENUMdaily.Friday:
        return "Cuma";
      case ENUMdaily.Saturday:
        return "Cumartesi";
      case ENUMdaily.Sunday:
        return "Pazar";
    }
  }
// getDay() methodu bize o anki günün değerini Pazartesi ise 1 Salı ise 2.. şeklinde verir
console.log(getDayTR(new Date().getDay()))  //return "Pazartesi"

ENUMdaily.Monday = "yeni bir değer" // ENUMdaily sadece okunabilir, değiştirilemez.

// Burada yapmaya çalıştığımız olay. belirli enumlar tanımlayarak bunları farklı yerlerde
// daha anlaşılır halde kullanabilmek. Örneğin artı ENUMdaily.Monday değerini
// çağırdığımızda karşılığının 1 olacakğını biliyoruz. case 1 mi demek yerine
// case ENUMdaily.Monday ise Pazartesi olacağını anlayabiliriz.
```

```tsx
enum YemekKategorileri {
    Corba = "Çorba",
    AnaYemek = "Ana Yemek",
    Salata = "Salata",
    Tatli = "Tatlı"
  }

  enum Yemekler {
    MercimekCorbasi = "Mercimek Çorbası",
    KuzuKebap = "Kuzu Kebap",
    SezarSalata = "Sezar Salata",
    Baklava = "Baklava"
  }

  function getKategori(secilenYemek: Yemekler) {
    return secilenYemek === Yemekler.MercimekCorbasi ?
      YemekKategorileri.Corba : secilenYemek === Yemekler.SezarSalata ?
        YemekKategorileri.Salata : secilenYemek === Yemekler.Baklava ?
          YemekKategorileri.Tatli : YemekKategorileri.AnaYemek;
  }

console.log(getKategori(Yemekler.Baklava)); // return "Tatlı"
console.log(getKategori(Yemekler.KuzuKebap)); // return "Ana Yemek"
```

### Tip parametreleri (Generics)

**`<T>`** ifadesindeki **`T`**, genel tür parametresini temsil eder. **`T`**'yi istediğiniz herhangi bir harfle veya kelimeyle değiştirebilirsiniz, ancak genellikle **`T`** tercih edilir, çünkü "Type" (Tür) anlamına gelir.

```tsx
// fonksiyonun T adında bir parametre alacağını belirtiyoruz.

function example<T>(param: T) {
  return param
}
// artık fonksiyona parametre olarak hangi değeri gönderirsek giriş ve çıkış
// değerleri otomatik olarak bu tipe göre belirlenir.
console.log(example("Hello")); // giriş değeri "Hello" return "Hello"
console.log(example(24))  // giriş değeri number retrun number
```

```tsx
function example<T extends string>(name: T) {
  return name
}

example("alicabbar")

function example<T extends string[]>(name: T) {
  return name
}

example(["alicabbar", "kaira"])

function example<T extends { name: string }[]>(name: T) {
  return name
}

example([{name: "alicabbar"}, {name: "dasdas"}])

function example<T extends object>(name: T) {
  return name
}

example({name: "dasdas"}); // obje olarak parametre alabilir
example([{name: "alicabbar"}, {name: "dasdas"}])  // veya array içerisinde objeler alabilir
```

### Tip tanımlama yöntemleri

```tsx
interface IPerson {
	name: string,
	age: number
}

// Yöntem 1
const person1 = {name: "Kaira", age: 19} as IPerson
// Yöntem 2
const person2: IPerson = {name: "Kaira", age: 19}
// Yöntem 3
const person1 = <IPerson>{name: "Kaira", age: 19}
// Yöntem 3
const person1 = <>{name: "Kaira", age: 19}
```

as ile tanımlama yapmak sağlıklı değildir çünkü as yöntemi aslında oluşturulan değeri ilk başta boş bir değer olarak kabul eder ve as ile tipini belirtir bu nedenle içerisini ilk başta boş değer olarak kabul ettiği için hataları vurgulamaz, özellikle obje yapılarında.

```tsx
interface IPerson {
	name: string,
	age: number
}

// Hata verir çünkü person1 içerisine name ve age değeri girmek zorunludur.
const person1: IPerson = {}

// Hata vermez çünkü yapıyı oluşturdukttan sonra IPerson tipine çevirir.
const person2 = {} as IPerson
```

****Tuple :**** Belirli bir sayıda öğe içeren ve her öğenin belirli bir türe sahip olduğu bir yapıları tarif etmek için kullanılır. Typescript ‘e özgü bir kavram değildir, genel programlama dillerinde elemen sayısı, sırası ve tipleri kesinleşmiş, belli olan yapılara denir.

```jsx
// tipi ve eleman sayısı belli bu yüzden bu bir tuple öğesi.
const person1 : [string, number] = ["Kaira",19]
```

### Tip doğrulama

```tsx
const person = ["qd", "sad", "ds", 3];
const person2 = 4;
const person3 = {name: "ddsd"}
const person4 = Symbol()

// true
if (Array.isArray(person)) {
  console.log("Bu bir array")
}

console.log(Array.isArray(person2)) //false
console.log(typeof person2)  // number
console.log(typeof person3)  // object
console.log(typeof person4)  // symbol
```

### Array.isArray(…)

Gönderilen parametrenin array olup olmadığını kontrol eder. `typeof <değişken adı>` şeklinde tanımlamalarda eğer bir array değişkeni adı gönderirseniz tip olarak object geriye döndürür çünkü arrayler de object türünde kabul edilir. Bir değişkenin array olup olmadığını anlamak için `Array.isArray` kullanılır, bu geriye `true` veya `false` değer döndürür.

```tsx
function isArray(data: any): boolean {
  if (data instanceof Array) {
    return true
  }
  return false
}

const person = {id: 1, name:"kaira"}
isArray(person); // return false
const person2 = [12,"kedi"];
isArray(person2); // return true
```

Bir fonksiyona parametre olarak gelen bir tip any olmalı. Zaten alacağımız parametrenin tipini belirtmiş isen o zaman bunu tip kontrolü yapmaya gerek yok zaten tipi bellidir.

### extends

Bir değeri başka bir değerden türetmek anlamı taşır.

```tsx
const myArray = [1, 2, "das"];

//person fonksiyonumun alacağı parametre myArray değişkenimin tipinden türetildi.
function person<T extends typeof myArray>(arr: T) {
  console.log(true)
}

person([1, 2]); // true
person("kedi");  // error : person fonksiyonu myArray tipinde olabilir.
```

### Template Literal Types

İlgili değişkene belirli özellikler ile değerler almasını sağlayan tipler oluşturmak için kullanılır.

```tsx
// set kelimesinde sonra herhangi bir string değer eklenmeli
const person: `set${string}` = 'setChance'
// set 'den sonra herhangi bir number değer eklenmeli
const person2: `set${number}` = 'set24'
// dışarıda tip tanımlayıp iletebiliriz
type Tperson = `on${number}`;
const person: Tperson= 'on24';

// set 'den sonra baş harfi büyük string almalı
const person: `set${Capitalize<string>}`= 'setChance';
// set 'den sonra baş harfi küçük string almalı
const person: `set${Uncapitalize<string>}`= 'setchance';
// set 'den sonra tüm harfleri büyük string almalı
const person: `set${Uppercase<string>}`= 'setCHANCE';
// set 'den sonra tüm harfleri küçük string almalı
const person: `set${Lowercase<string>}`= 'setchance';
```

```tsx
type IParams =  `set${Uppercase<'DELETE' | 'UPDATE' | 'ADD'>}`;

function personHandler(params : IParams) {
  switch (params){
      case 'setDELETE':
          console.log("Silme işlemi başarılı");
          break;
      case 'setUPDATE':
          console.log("Güncelleme işlemi başarılı");
          break;
      case 'setADD':
          console.log("Ekleme işlemi başarılı");
          break;
      default :
          alert("İşlem başarısız");
     }
 }

personHandler("setADD") // "Ekleme işlemi başarılı"
```
