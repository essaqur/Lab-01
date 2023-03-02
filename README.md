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
![image](https://user-images.githubusercontent.com/109910115/222474914-b9307518-98de-49d4-9f94-0cdfff73c447.png)

## Задание №3
Подсчитайте количество файлов в директории не включая вложенные директории
```
cd boost_1_72_0
tree -L 1
```
![image](https://user-images.githubusercontent.com/109910115/222475563-6c61539b-05d0-43c7-a941-a16e1d6b834c.png)

## Задание №4
Подсчитайте количество файлов в директории включая вложенные директории
```
tree
```
![image](https://user-images.githubusercontent.com/109910115/222475675-53ef771f-16a6-46ab-a992-63f1deb9bacd.png)

## Задание №5
Подсчитайте количество заголовочных файлов, файлов с расширением .cpp, сколько остальных файлов (не заголовочных и не .cpp)
```
find . -name "*.cpp" | wc -l
find . -not -name "*.cpp" | wc -l
```
![image](https://user-images.githubusercontent.com/109910115/222475827-94efbe3c-de0a-4d72-8bb7-6b3b308881e8.png)

## Задание №6
Найдите полный пусть до файла any.hpp внутри библиотеки boost
```
realpath any.hpp
```
![image](https://user-images.githubusercontent.com/109910115/222475934-f80a8e2e-fdf1-4900-a2e2-60bb19c73483.png)

## Задание №7
Выведите в консоль все файлы, где упоминается последовательность boost::asio
```
grep -lr boost::asio
```
![image](https://user-images.githubusercontent.com/109910115/222476525-d75f618e-c938-43ae-8ad6-ce977e4fc7ef.png)

## Задание №8
Скомпилирутйе boost
```
./bootstrap.sh --prefix=boost_output
./b2 install
```
![image](https://user-images.githubusercontent.com/109910115/222478790-19f70591-b1ed-4795-b088-a36c8343e91c.png)

## Задание №9
Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию ~/boost-libs
```
mkdir ~/boost-libs
mv * ~/boost-libs
```
![image](https://user-images.githubusercontent.com/109910115/222479287-cad39d73-dfe8-494a-a0b6-140174a00a10.png)

## Задание №10
Подсчитайте сколько занимает дискового пространства каждый файл в этой директории
```
cd ~/boost-libs/
ls -sh
```
![image](https://user-images.githubusercontent.com/109910115/222479836-3941d64f-db67-411f-8174-fd69b4d30da6.png)

## Задание №11
Найдите топ10 самых "тяжёлых"
```
find . -type f -exec du -h {} +|sort -rh | head -n 10
```
![image](https://user-images.githubusercontent.com/109910115/222480275-01ed5c61-1df5-47db-a123-ea39382c3cab.png)



