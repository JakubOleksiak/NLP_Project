# NLP_Project
Project done during one of the courses on PJAIT - because of it the text below will be in Polish.

# Projekt NLP - s18728 Jakub Oleksiak

#### Dla wszystkich studentów na roku których będzie kusiło o leciutki plagiat mam uprzejmą przestrogę - nie wyjdzie wam, modyfikacje i hiperparametry poczynione i ustawione w niniejszym projekcie są bardzo specyficzne dla tego projektu - ja wiem dlaczego są tak ustawione, wy nie. Zostaliście ostrzeżeni :)
##### Oczywiście nie dotyczy to pliku z tweetami, ten oczywiście możecie brać jak komuś nie udało się wystarczająco dużego zbioru danych pozyskać.

Instrukcja uruchomienia (tzw. Setup):

0. Jeśli jedyne co jest na celu to przejrzenie projektu, nie uruchomienie go, to wystarczy kliknąć w plik "NLPPRO.ipynb" i wybrać opcję "preview" na GitHubie.
1. Pobrać/sklonować projekt.
2. Plik "NLPPRO.ipynb" jest plikiem notatnika Jupyter, trzeba uruchomić w programie obsługującym ten typ plików (Google Colab, Jupyter Notebook itp.)
3. Pliki w folderze "CSV-data" to pliki z danymi pandas Dataframe zapisanymi do plików csv. Można je wczytać za pomocą metody `pd.read_csv(f'{path_to_file}')`
4. Najważniejszy z plików .csv to plik "tweets45k.csv". Jest to zbiór 45 tysięcy tweetów pozyskanych poprzez użycie api Twittera wraz z biblioteką Tweepy.
![image](https://github.com/JakubOleksiak/NLP_Project/assets/69526785/b58471d4-fc50-4b67-b61c-0558c2d5719e)
Powyższy zrzut ekranu ukazujący konkretny fragment kodu użyty do pozyskania tweetów. Najważniejsze to oczywiście query.
5.   Pliki w folderze "Models" to zapisane modele:
- Modele klasycznego ML można wczytać za pomocą biblioteki pickle, chociaż to trochę na wyrost, bo uczą się super szybko.
- "word2vec.model" można wczytać za pomocą `Word2Vec.load(f'{path_to_file}')`
- Pliki w folderze Keras oraz pliki w folderze BERT są to pliki zarchiwizowane częściowe 7z - trzeba mieć 7zip żeby je odpowiednio wypakować.
- Po wypakowaniu powyżej wspomnianych plików (lub pobrania/użycia ich z załączonego w projekcie linku do Google Drive) można je załadować odpowiednimi metodami.
6. Projekt można tak naprawdę uruchomić od góry do dołu cały (np. opcja "uruchom wszystko" w Google Collab), ale z racji, że niektóre modele (zwłaszcza BERT i Kerasowy) uczą się dosyć długo, modele te można wczytać z załączonych plików.
7. NALEŻY PAMIĘTAĆ O ZMIANIE ŚCIEŻEK DO PLIKÓW NA LOKALNE!
8. Projekt jest podzielony (w notatniku) na same


Wyniki i wnioski

Bawiłem się naprawdę niesamowicie przy tym projekcie, autolabelując na żywym organizmie. 
W modelu kerasowym postanowiłem nie używać LSTMów, zamiast tego po prostu złączyłem wejścia TFIDFowych scores i osadzeń wyrazów - było bardzo ciekawie, nauczyłem się dużo, ale nie wiem, czy jest to najbardziej optymalny sposób (spoiler - zdecydowanie nie).
Użycie BERTA też jest niesamowite, bardzo user-friendly, chociaż tzw. learning curve ma dosyć wysokie.

Co ciekawe klasyczne ML było nawet dosyć niezłe - Regresja Liniowa osiągnęła naprawdę niespodziewane wyniki.

### O osiągnięte wyniki dokładności każdego z modeli proszę zerknąć na ostatni rozdział w pliku projektowym.

Utworzyłem też w trakcie projektu WordCloud:
![wc](https://github.com/JakubOleksiak/NLP_Project/assets/69526785/410a0745-d1ad-43f3-8d4d-b2b9bb0170db)

Jestem dosyć zadowolony ogólnie z wynikowych modeli, chociaż na pewno lepsze wyniki otrzymałbym z użycia jakiejś bardziej zaawansowanej metody autolabellingu, oraz może dodatkowej obróbki tekstu (?).
Na pewno coś mi umknęło przy dostrajaniu BERTa

Bardzo dziękuję za możliwość takiego pobawienia się z NLP - to była przygoda poszerzająca horyzonty umiejętności w dziedzinie przetwarzania języka naturalnego, z której na każdym kroku czerpałem duże dawki przyjemności.
