# Penjelasan script sampling.sh

Berikut penjelasan tiap baris script sampling.sh

1. wget https://github.com/labusiam/dataset/raw/main/weather_data.xlsx
--> Mengunduh data dari url source

2. in2csv weather_data.xlsx --sheet "weather_2014" > weather_2014.csv
--> Mengubah ekstensi file sheet "weather_2014" pada file weather_data.xlsx menjadi "weather_2014.csv"

3. in2csv weather_data.xlsx --sheet "weather_2015" > weather_2015.csv
--> Mengubah ekstensi file sheet "weather_2015" pada file weather-data.xlsx menjadi "weather_2015.csv"

4. csvstack weather_2014.csv weather_2015.csv > weather.csv
--> Menggabungkan 2 file yaitu weather_2014.csv dan weather_2015.csv menjadi "weather.csv"

5. rm weather_data.xlsx
--> Menghapus source data file "weather_data.xlsx"

6. cat weather.csv | sample -r 0.3 | head > sample_weather.csv
--> Melakukan sampling pada file weather.csv dan menyimpannya ke dalam file "sample_weather.csv"
