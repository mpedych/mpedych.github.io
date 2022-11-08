---
layout: post
title: "Як встановити Java на MacOS"
categories: misc
---

З зміною моделі релізів Java в червні 2018 часто виникає необхідність мати декілька версій Java зі змогою швидко переключатись між версіями. В даній статі пропоную розглянути встановлення декількох версій Java та переключання між ними за допомогою змінної `JAVA_HOME`.

Спочатку знайдемо вже встановлені JDK:
``` shell
/usr/libexec/java_home -V
```

Приклад виводу результату команди:
``` shell
Matching Java Virtual Machines (3):
    17.0.5 (x86_64) "Oracle Corporation" - "Java SE 17.0.5" /Library/Java/JavaVirtualMachines/jdk-17.0.5.jdk/Contents/Home
    11.0.16.1 (x86_64) "Oracle Corporation" - "Java SE 11.0.16.1" /Library/Java/JavaVirtualMachines/jdk-11.0.16.1.jdk/Contents/Home
    1.8.0_202 (x86_64) "Oracle Corporation" - "Java SE 8" /Library/Java/JavaVirtualMachines/jdk1.8.0_202.jdk/Contents/Home
/Library/Java/JavaVirtualMachines/jdk-17.0.5.jdk/Contents/Home
```

Тепер треба створити посилання на кожну з вірсій Java для майбутніх аліасів. Для кожної версіх можна взяти тільки унікальні перші символи. Наприклад, для Java 11 можна взяті тільки перші два симовли `11`. Якщо 11-х версій більше ніж одна, треба вказувати таким чином щоб однозначно можна було ідентифікувати потрібну версію.

Для навеленого вище виводу результат буде наступним:
``` shell
/usr/libexec/java_home -v 1.8
/usr/libexec/java_home -v 11
/usr/libexec/java_home -v 17
```

Далі створюємо профіль для командного рядка. Для Bash це буде мати вигляд `~/.bash_profile`: 
``` shell
# aliase commands to enable easy setting of JDK version
alias setJDK8='export JAVA_HOME=`/usr/libexec/java_home -v 1.8`'
alias setJDK11='export JAVA_HOME=`/usr/libexec/java_home -v 11`'
alias setJDK17='export JAVA_HOME=`/usr/libexec/java_home -v 17`'

# set to the default JDK
export JAVA_HOME=`/usr/libexec/java_home -v 1.8`
```
