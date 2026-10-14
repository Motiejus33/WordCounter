
WordCounter yra Android programėlė sukurta MIPT 2 praktikos darbui. Skaičiuoja sakinius, žodžius, simbolius ir skaičius, generuoja testavimo tekstus ir rodo skaičiavimų istoriją. 

## Kaip naudotis

1. Įrašyk tekstą arba paspausk **Generate example**, kad gautum testavimo tekstą.
2. Paspausk **Calculate**, kad pamatytum rezultatus. Tuščiai arba vien tarpus turinčiai įvesčiai rodomas klaidos pranešimas.
3. Paliesk istorijos įrašą, kad atkurtum tekstą ir jo rezultatus.
4. Paspausk **Clear**, kad išvalytum istoriją.

Istorijoje laikomi paskutiniai 30 įrašų tik vykdymo metu. Įvestis ribojama iki 5000 UTF-16 vienetų. Pasukus ekraną tekstas ir istorija atkuriami.
## Skaičiavimo taisyklės

- Sakinius skiria `.`, `!`, `?` ir `…`. Paskutinė neužbaigta teksto dalis taip pat skaičiuojama. Dešimtainio skaičiaus taškas sakinio neskaido.
- Žodžiai yra raidžių sekos, galinčios turėti vidinį apostrofą ar brūkšnelį. Vien skaitmenys nelaikomi žodžiu.
- Simboliai skaičiuojami su tarpais ir skyryba pagal Unicode kodo taškus.
- Skaičiai gali turėti ženklą ir vieną dešimtainį skirtuką: tašką arba kablelį.

| Tekstas | Sakiniai | Žodžiai | Simboliai | Skaičiai |
| --- | ---: | ---: | ---: | ---: |
| Labas rytas | 1 | 2 | 11 | 0 |
| Rugsėjo 1 prasidėjo karas. Liūdna | 2 | 4 | 33 | 1 |

## Paleidimas

1. Android Studio atidaryk aplanką `WordCounter`.
2. Pasirink JDK 17 arba suderinamą naujesnę versiją. Įdiek Android SDK 35 ir Build Tools 35.0.0.
3. Palauk Gradle sinchronizavimo.
4. Pasirink `app` ir emuliatorių arba Android telefoną, tada paspausk **Run**.

Projektas naudoja Gradle 8.11.1 ir Android Gradle Plugin 8.9.2. Minimali Android versija – 6.0 (API 23).

Surinktas APK: `app/build/outputs/apk/debug/app-debug.apk`.

## Projekto struktūra

- `app` – programėlės sąsaja, testavimo tekstų generatorius ir istorija.
- `core` – atskiras, pernaudojamas metrikų skaičiavimo modulis.
- `app/src/main/res/values/strings.xml` – angliški sąsajos tekstai ir testavimo pavyzdžiai. Tekstai laikomi resursuose, kad būtų lengva juos lokalizuoti.
