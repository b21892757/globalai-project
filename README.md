# globalai-project2 (data Pythons) 

## Projenin Genel Özeti

Netflix dizilerinin istatistiksel değerlerini ekrana bastırma ve görselleştirme işlemi 

### 1) Veri setine göre uzun soluklu filmler hangi dilde oluşturulmuştur? Görselleştirme yapınız. / In which language were the long-running films created according to the dataset? Make a visualization.

sort_values methodunu kullanarak Runtime sütununa göre sıralama işlemi yaptık, daha sonra groupby methodu ile dillere göre sınıflandırdık ve bu sütunlarda dillere göre en uzun süreli filmlerin ortalama süresini hesaplamak için mean methodu kullandık.
En son adımda barplot kullanarak önceki adımda oluşturduğumuz değerleri görselleştirdik.

We used the sort_values method to sort by the Runtime column, then we classified them according to the languages with the groupby method, and we used the mean method to calculate the average duration of the longest movies in these columns according to the languages. 
In the last step, we visualized the values ​we created in the previous step using barplot.

### 2) 2019 Ocak ile 2020 Haziran tarihleri arasında 'Documentary' türünde çekilmiş filmlerin IMDB değerlerini bulup görselleştiriniz. / Find and visualize the IMDB values of the movies shot in the 'Documentary' genre between January 2019 and June 2020


Öncelikle veri çerçevesinde tarih sütunumuzun veri türü sayısal olmadığı için tüm tarih bilgilerini sayısal türe çevirme işlemi yaptık. Bu işlemi python pandas kütüphanesinin içerisindeki to_datetime methodu ile gerçekleştirdik. Daha sonra bu sayısal kısımın içinden yıl ve ay bilgisini çekip yeni bir sütunda tuttuk.
Burada klasik bir sorgu gerçekleştirdim ve bu tarihler arasında olup filmin türü documentary olan tüm sütunları yeni bir değişkene atadık. 
En son adımda scatter kullanarak önceki adımda oluşturduğumuz değerleri görselleştirdik.

First of all, since the data type of our date column in the data frame is not numeric, we converted all date information to numeric type. We did this with the to_datetime method in the python pandas library. 
Then we pulled the year and month information from this numeric part and kept it in a new column. Here, I performed a classic query and assigned all the columns between these dates and whose type is documentary to a new variable. In the last step, we visualized the values we created in the previous step using the scatter.

### 3) İngilizce çekilen filmler içerisinde hangi tür en yüksek IMDB puanına sahiptir? / Which genre has the highest IMDB rating among movies shot in English?

Öncelikle dataframe içerisindeki dili ingilizce olan filmleri bir değişkene atadık, daha sonra sort_values kullanarak IMDB puanına göre büyükten küçüğe sıraladık. 
En son adımda head methodu ile en üstteki değeri ekrana yazdırdık.

First, we assigned the English-language movies in the data frame to a variable, then we sorted them from largest to smallest according to their IMDB score using sort_values.

## 4

## 5
## 6
## 7
## 8
## 9


### 10- 'Runtime' değeri en yüksek olan ilk 10 film hangileridir? / Which are the top 10 movies with the highest 'Runtime' value?

Sorunun cevabını bulmak için "highest" runtime adını verdiğim değişkende "nlragest" methodunu kullanıp runtime değeri en yüksek 10 filmi sıraladım ve "matplotlib" kütüphanesini kullanarak görselleştirdim. / To find the answer to the question, I used the "nlragest" method in the variable I named "highest" runtime and ranked the 10 movies with the highest runtime value and visualized them using the "matplotlib" library.

### 11- Hangi yılda en fazla film yayımlanmıştır? / In which year was the most movies released?

Öncelikle veritabanından "Release Year" değerimi bulmak için "Premiere" değişkeninden ayırdım, daha sonra bu "Release Year" değişkenimi veritabanında ayrı bir kolona ayırdım ve tekrar "nlargest" methodunu kullanarak verimi elde ettim. Son olarak "matplotlib" kütüphanesini ve ".plot" fonksiyonunu kullanarak görselleştirdim. / First of all, I sliced my "Release Year" variable from the "Premiere" variable to find my "Release Year" value from the database, then I separated this "Release Year" variable into a slice column in the database and again using the "nlargest" method, I got the yield. Finally I visualized using the "matplotlib" library and the ".plot" function.

### 12- Hangi dilde yayımlanan filmler en düşük ortalama IMBD puanına sahiptir? / Which films released in which language have the lowest average IMBD score?

İlk olarak en düşük IMDB puanına sahip 10 filmi "nsmallest" methodunu kullanarak elde ettim ardından bunları bir değişkene atadım ve yazdırdım. Daha sonra bu 10 filmin "Language" kolonunu ayırıp değerler elde ettim ve bu değerleri dataframe'e çevirdim. Son olarak bu değerleri görselleştirmek için "matplotlib" kütüphanesinden "plot.bar" methodunu kullanarak görselleştirmek adına bir sütun grafiği yaptım. Ayrıca ek olarak aynı kütüphaneden "plot.pie" methodunu kullanıp parametreleri ile görselleştirerek bir pasta grafiği de oluşturdum. / First I got the 10 movies with the lowest IMDB score using the "nsmallest" method, then I assigned them to a variable and printed them. Then I separated the "Language" column of these 10 movies and got values ​​and converted these values ​​to dataframe. Finally, I made a bar chart to visualize these values ​​using the "plot.bar" method from the "matplotlib" library. In addition, I created a pie chart by using the "plot.pie" method from the same library and visualizing it with its parameters.

### 13-Hangi yılın toplam "runtime" süresi en fazladır?/Which year has the most total "runtime" time?

Bunu bulabilmek için df2 adlı bir değişken oluşturup bunu "groupby method" ile yıllara göre filtrelediğimiz zaman
Runtime'ı elde etmiş oluyoruz.
To find this, we create a variable called df2 and filter it by year using the "groupby method" when
We get the Runtime.


### 14-Her bir dilin en fazla kullanıldığı "Genre" nedir?/What is the "Genre" in which each language is used the most?
Her bir dilin kullandığı genre'yi öğrenmek için "groupby" metodu ile çalışmalıyız.Burada Genre içerisinde Language olarak grupladığımız sonuçları tablo şeklinde görüntülememiz mümkün.

In order to learn the genre used by each language, we should work with the "groupby" method.Here it is possible to display the results that we have grouped in Genre as Language in a table form.

### 15-Veri setinde outlier veri var mıdır? Açıklayınız./Is there outlier data in the dataset? Please explain.

Veri setinin doğru bir şekilde yüklendiğini anlamak için ilk ve son 5 satırını head() ve tail() fonksiyonları ile görüntülemeliyiz.Değişkenlere dair daha fazla bilgi edinmek için info() fonksiyonunu kullanarız.
Kutu grafiğini çizmek için Matplotlib (kısaca plt) kütüphanesini kullanmalıyız.Bu çerçevenin 2 adet iç grafik içermesini istediğimiz ve 1 satır, 2 sütun şeklinde yan yana görüntülenmesini istediğimiz için subplots’a 1, 2 parametrelerini veriyoruz.Kutu grafiklerinin daha açıklayıcı olması için “set_title” ile de her kutu grafiğine başlık atıyoruz.
Kutu grafiğinde olduğu gibi aynı yolu izlemeliyiz. Önce çerçeve ve iç grafik yapısını belirlemek gerekir Ardından “hist” fonksiyonu ile 2 farklı değişkenimiz için histogram grafiklerini çizdirmiş olduk.
Çeyrekler açıklığını SciPy kütüphanesinin “iqr()” fonksiyonu ile hesaplayabiliriz.Fonksiyona iqr adını verdik. df ve var adında iki parametre ile çalışmaktadır.Aykırı değerleri belirleyecek sınırlar olan alt ve üst eşik değerlerini hesaplarken 1. çeyrekten 1.5 kat az, 3. çeyrekten de 1.5 kat fazla olan değeri sınır olarak belirledik.Son olarak da işlem yapılan değişkendeki eşik değerlerin altında ve üstünde kalan değerleri filtreleme işlemi yaptık.
Fonksiyonu çalıştırdığımızda, belirlediğimiz kurala göre aykırı olarak bulunan değerleri birer değişkene atadık. Ve aykırı değerlerin 75 ile 9 olduğunu tespit ettik.


In order to understand that the data set is loaded correctly, we need to display the first and last 5 lines with the head() and tail() functions.
To find out more about the variables, we use the info() function.To plot the box graph, we should use the Matplotlib (plt for short) library.Since we want this frame to contain 2 internal graphs and we want it to be displayed side by side in the form of 1 row, 2 columns, we give subplots the parameters 1, 2.In order for the box graphs to be more descriptive, we also assign a title to each box graph with “set_title”.
We need to follow the same path as in the box graph. First, it is necessary to determine the frame and internal graph structure, and then we have drawn histogram graphs for our 2 different variables with the “hist” function.We can calculate the quadrant clearance using the “iqr()” function of the SciPy library.We have named the function iqr. it works with two parameters called df and var.1. When calculating the lower and upper threshold values, which are the limits that will determine the outliers. 
1.5 times less than a quarter, 3. we have set the value as the limit, which is 1.5 times more than a quarter.Finally, we have filtered the values that remain below and above the threshold values in the variable being processed.
When we ran the function, we assigned the values that were found to be contrary to the rule we set to a variable. And we found that the outliers are 75 to 9.


#### 
**Enes Genişyürek**
**Emircan Baki Doğan**
**İren Vera Can**
**Mustafa Faruk Ceylan**
**Esin Kavurmacı**