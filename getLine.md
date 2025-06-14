ពាក្យ៖

```cpp
getline(cin, name);
```

នេះគឺជា **បញ្ជាក្នុងភាសា C++** ដែលត្រូវបានប្រើដើម្បី **អានបញ្ចូលអត្ថបទពេញមួយបន្ទាត់** ពីអ្នកប្រើ (user) ហើយរក្សាទុកទៅក្នុងអថេរ `name`។ ប្រើជាញឹកញាប់នៅពេលដែលអ្នកចង់អាន **ឈ្មោះ**, **អាសយដ្ឋាន**, ឬ **អត្ថបទដែលមានស្លាក់ (space)** ។

---

### ✅ **ការពន្យល់ប្រកបដោយពាក្យសាមញ្ញ (សម្រាប់បង្រៀនសិស្ស)**

| ផ្នែក     | អត្ថន័យ                                                                             |
| --------- | ----------------------------------------------------------------------------------- |
| `getline` | គឺជាអនុគមន៍ (function) ក្នុង C++ ដែលប្រើសម្រាប់អានអត្ថបទមួយបន្ទាត់                  |
| `cin`     | មានន័យថា "character input" — ប្រើសម្រាប់អានទិន្នន័យពីអ្នកប្រើ                       |
| `name`    | ជាអថេរមួយដែលយើងបានបង្កើត (ប្រភេទ `string`) ដើម្បីរក្សាទុកអត្ថបទដែលអ្នកប្រើបានវាយចូល |

---

### 🧠 **សារៈសំខាន់**

ប្រើ `getline(cin, name);` ជំនួស `cin >> name;` នៅពេលដែល:

* អ្នកចង់អានឈ្មោះពេញ (មាន space) ឬអាសយដ្ឋាន
* ឧទាហរណ៍: "Chan Dara" — `cin >> name;` នឹងអានតែ "Chan", ប៉ុន្តែ `getline()` នឹងអានទាំង "Chan Dara"

---

### 🧪 **ឧទាហរណ៍ពេញលេញ**

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string name;
    cout << "សូមបញ្ចូលឈ្មោះរបស់អ្នក: ";
    getline(cin, name);
    cout << "ឈ្មោះដែលអ្នកបានបញ្ចូលគឺ: " << name << endl;
    return 0;
}
```

### 📌 លទ្ធផល

```
សូមបញ្ចូលឈ្មោះរបស់អ្នក: Chan Dara
ឈ្មោះដែលអ្នកបានបញ្ចូលគឺ: Chan Dara
```

---

បើសិស្សមានសំណួរដូចជា "តើអាចប្រើ `cin >> name;` បានទេ?" អ្នកគ្រូអាចប្រាប់ថា៖

* `cin >> name;` អានបានតែមួយពាក្យ។
* `getline(cin, name);` អានបានពេញមួយបន្ទាត់ (ជាមួយ space) — ពិសេសសម្រាប់ឈ្មោះពេញ ឬអាសយដ្ឋាន។

តើអ្នកចង់ឲ្យខ្ញុំសរសេរបង្ហាញជារូបភាព (PowerPoint slide) ឬ worksheet សម្រាប់សិស្សសម្រួលសិក្សា?
