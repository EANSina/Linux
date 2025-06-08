បញ្ជា៖

```cpp
cin.ignore();
```

សិស្សជាច្រើនអាចសួរ “តើ `cin.ignore();` មានតួនាទីអ្វី?” — ដូច្នេះ ខាងក្រោមនេះជាការពន្យល់បែបសិស្សយល់បានងាយ:

---

## 🧠 **អត្ថន័យនៃ `cin.ignore();`**

**`cin.ignore();`** ត្រូវបានប្រើដើម្បី **មិនអើពើ** (ignore) អត្ថបទនៅក្នុង input buffer មុនពេលអានបន្ទាត់ថ្មីជាមួយ `getline()`។ វាជាជំហានសំខាន់បំផុតបន្ទាប់ពីប្រើ `cin >>` ហើយចង់បន្តអាន string ជាមួយ `getline()`។

---

## ❗️បញ្ហាដែលកើតឡើង៖

បើសិនអ្នកប្រើ:

```cpp
int age;
string name;
cin >> age;
getline(cin, name); // ❌ បញ្ហា!
```

⛔️ វាមិនអាន `name` ដោយត្រឹមត្រូវទេ។
🛑 ពីព្រោះ `cin >> age;` ទុកសញ្ញា newline `\n` នៅក្នុង buffer → `getline()` ទទួល newline ហើយសន្មត់ថាវា "អានរួចហើយ"។

---

## ✅ **ដំណោះស្រាយ**: ប្រើ `cin.ignore();`

```cpp
int age;
string name;
cin >> age;
cin.ignore(); // ✅ បំបាត់ newline នៅក្នុង buffer
getline(cin, name);
```

---

## 📌 **Syntax ទូទៅ**

```cpp
cin.ignore(numeric_limits<streamsize>::max(), '\n');
```

អត្ថន័យ៖

* `ignore()` បោះបង់ character ចេញពី buffer រហូតដល់:

  * ទំហំលើកិច្ច (`max`)
  * ឬរកឃើញ newline `\n`

**ត្រូវប្រើបញ្ជានេះ** នៅពេលប្រើ `getline()` បន្ទាប់ពី `cin >>`

---

## 📘 ឧទាហរណ៍ពេញលេញ

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    int age;
    string name;

    cout << "បញ្ចូលអាយុ: ";
    cin >> age;

    cin.ignore(); // 💡 បំបាត់ '\n'

    cout << "បញ្ចូលឈ្មោះពេញ: ";
    getline(cin, name);

    cout << "សួស្តី " << name << ", អាយុ " << age << " ឆ្នាំ។" << endl;
    return 0;
}
```

---

### 📚 សេចក្តីសង្ខេបសម្រាប់បង្រៀនសិស្ស៖

| បញ្ជា                     | អត្ថន័យ                              |
| ------------------------- | ------------------------------------ |
| `cin >>`                  | អានតែពាក្យ (មិនអាន space)            |
| `getline(cin, variable);` | អានពេញមួយបន្ទាត់ (អាចមាន space)      |
| `cin.ignore();`           | បំបាត់ '\n' នៅក្នុង buffer មុនអានទៀត |

---

បើអ្នកចង់បាន slide ឬ worksheet សម្រាប់បង្រៀនមេរៀននេះ សូមប្រាប់ខ្ញុំបានគ្រប់ពេល!
