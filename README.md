# Lab-01 Report
tp-labs 01

## Задание №1
Загрузите boost с помощью утилиты wget
```
wget https://sourceforge.net/projects/boost/files/boost/1.72.0/boost_1_72_0.tar.gz
```
![image](https://user-images.githubusercontent.com/109910115/222474682-8342a836-7eae-4098-8752-f9a1c6c1e1c7.png)

## Задание №2
Разархивируйте скачанный файл в директорию
```
tar -xf boost_1_72_0.tar.gz
```
## Задание №3
Подсчитайте количество файлов в директории не включая вложенные директории
```
cd boost_1_72_0
tree -L1
```
## Задание №4
Подсчитайте количество файлов в директории включая вложенные директории
```
tree
```
## Задание №5
Подсчитайте количество заголовочных файлов, файлов с расширением .cpp, сколько остальных файлов (не заголовочных и не .cpp)
```
find . -name "*.cpp" | wc -l
find . -not -name "*.cpp" | wc -l
```
## Задание №6
Найдите полный пусть до файла any.hpp внутри библиотеки boost
```
realpath any.hpp
```
## Задание №7
Выведите в консоль все файлы, где упоминается последовательность boost::asio
```
grep -lr boost::asio
```
## Задание №8
Скомпилирутйе boost
```
./bootstrap.sh --prefix=boost_output
./b2 install
```
## Задание №9
Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию ~/boost-libs
```
mkdir ~/boost-libs
mv * ~/boost-libs
```

## Задание №10
Подсчитайте сколько занимает дискового пространства каждый файл в этой директории
```
ls -hl
```
## Задание №11
Найдите топ10 самых "тяжёлых"
```
find . -type f -exec du -h {} +|sort -rh | head -n 10
```

