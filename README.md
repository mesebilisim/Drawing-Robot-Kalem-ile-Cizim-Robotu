# Drawing-Robot-Kalem-ile-Cizim-Robotu
Drawing Robot Kalem ile Çizim Robotu


Robot Parçaları
Drawing Robot Kalem ile Çizim Robotu
https://robotparcalari.com
Bu kullanım kılavuzu https://robotparcalari.com/urun/drawgin-robot-kalem-ile-cizim-robotu/ adresindeki çizim robotu içindir.

# Döküman Versiyon : 1.0
# Tarih : 09.01.2021
# GRPL Firmware : https://github.com/robottini/grbl-servo
# GRPL GUI Sender : https://github.com/Denvi/Candle/
# Inkscape : 0.48.0-1

Windows için kurulum adımları:

1- Klasör içerisindeki grbl-servo.zip dosyası Arduino library olarak eklenir. Arduino proğramı arayüzünden File -> Examples menüsünden grbl-servo içerisindeki grblUpload dosyası açılır. Arduino Port numarası seçilir ve Arduino kart ismi Arduino Uno olarak seçilir ve firmware Arduino kartımıza yüklenir. 

2- Klasör içerisindeki Candle_1.1.7.zip dosyası klasöre açılır ve içerisindeki Candle.exe dosyası çalıştırılır. Service -> Settings menüsünden Arduino port numarası seçilir. Ok tuşu ile ana ekrana dönülür.

3- GRBL dosyasının standart ayarları görmek için console veri girişinden $$ komutu verilir. Standart ayarlar aşağıdaki gibidir.
    Grbl 0.9i içindir.
    a- $0=10 (step pulse, usec)
    b- $1=25 (step idle delay, msec)
    c- $2=0 (step port invert mask:00000000)
    d- $3=0 (dir port invert mask:00000000)
    e- $4=0 (step enable invert, bool)
    f- $5=0 (limit pins invert, bool)
    g- $6=0 (probe pin invert, bool)
    h- $10=3 (status report mask:00000011)
    i- $11=0.010 (junction deviation, mm)
    j- $12=0.002 (arc tolerance, mm)
    k- $13=0 (report inches, bool)
    l- $20=0 (soft limits, bool)
    m- $21=0 (hard limits, bool)
    n- $22=0 (homing cycle, bool)
    o- $23=0 (homing dir invert mask:00000000)
    p- $24=25.000 (homing feed, mm/min)
    r- $25=500.000 (homing seek, mm/min)
    s- $26=250 (homing debounce, msec)
    t- $27=1.000 (homing pull-off, mm)
    u- $100=250.000 (x, step/mm)
    v- $101=250.000 (y, step/mm)
    y- $102=250.000 (z, step/mm)
    z- $110=500.000 (x max rate, mm/min)
    aa- $111=500.000 (y max rate, mm/min)
    ab- $112=500.000 (z max rate, mm/min)
    ac- $120=10.000 (x accel, mm/sec^2)
    ad- $121=10.000 (y accel, mm/sec^2)
    ae- $122=10.000 (z accel, mm/sec^2)
    af- $130=200.000 (x max travel, mm)
    ag- $131=200.000 (y max travel, mm)
    ah- $132=200.000 (z max travel, mm)

4- Drawing Robotumuzun çalışma ayarları ise aşağıdaki gibi olmalıdır. Bunun için console veri girişinden aşağıdaki komutlar çalıştırılır. Bu komutlar bir kere çalıştırıldığında ve robotunuzu kapatıp açtığınızda tekrar yapmanıza gerek yoktur. Ayarlar Arduino Uno kartınız tarafından kaydedilmektedir. Aşağıdaki komutlar çalıştırılıp bitirildikten sonra yine $$ komutu ile doğru olduğu test edilmelidir.
    Grbl 0.9i içindir.
    a- $0=30 (step pulse, usec)
    b- $1=25 (step idle delay, msec)
    c- $2=0 (step port invert mask:00000000)
    d- $3=3 (dir port invert mask:00000011)
    e- $4=0 (step enable invert, bool)
    f- $5=0 (limit pins invert, bool)
    g- $6=0 (probe pin invert, bool)
    h- $10=3 (status report mask:00000011)
    i- $11=0.010 (junction deviation, mm)
    j- $12=0.002 (arc tolerance, mm)
    k- $13=0 (report inches, bool)
    l- $20=0 (soft limits, bool)
    m- $21=0 (hard limits, bool)
    n- $22=0 (homing cycle, bool)
    o- $23=0 (homing dir invert mask:00000000)
    p- $24=25.000 (homing feed, mm/min)
    r- $25=500.000 (homing seek, mm/min)
    s- $26=250 (homing debounce, msec)
    t- $27=1.000 (homing pull-off, mm)
    u- $100=80.000 (x, step/mm)
    v- $101=80.000 (y, step/mm)
    y- $102=10.000 (z, step/mm)
    z- $110=5000.000 (x max rate, mm/min)
    aa- $111=5000.000 (y max rate, mm/min)
    ab- $112=500.000 (z max rate, mm/min)
    ac- $120=1000.000 (x accel, mm/sec^2)
    ad- $121=1000.000 (y accel, mm/sec^2)
    ae- $122=10.000 (z accel, mm/sec^2)
    af- $130=200.000 (x max travel, mm)
    ag- $131=200.000 (y max travel, mm)
    ah- $132=200.000 (z max travel, mm)

5- Klasör içerisindeki Inkscape-0.48.0-1.exe isimli programı kuruyoruz. Bizde d:\Program Files (x86)\Inkscape içerisinde kurulu.

6- laser-gcode-exporter-inkscape-plugin-master isimli zip dosyasını açıyoruz ve içerisindeki turnkeylaser.inx ve turnkeylaser.py isimli dosyaları 5. adımda kurduğumuz Inkspace klasörünün içerisindeki D:\Program Files (x86)\Inkscape\share\extensions klasörüne yapıştırıyoruz.

7- Inkscape uygulamasını çalıştırıyoruz. Döküman özellikleri menüsünden (Document Properties) Default units ayarını px olarak ayarlıyoruz. Page Size bölümünden A4 seçiyoruz ve pencereyi kapatıyoruz.

8- Bir yazı yazıp Extensions -> Export menüsünden Turnkeylaser Exporter mnüsüne tıklıyoruz, dosyamıza bir isim veriyoruz ve kaydediyoruz. Klasör adı verilmez ise masaüstüne dosyamız oluşacaktır. Klasörümüzde test-gcode isimli klasörün içerisinde örnek gcode dosyası bulunmaktadır.

9- GRPL GUI Sender Candle isimli programı açıyoruz ve Open butonu ile .gcode dosyamızı seçip gönderiyoruz.




