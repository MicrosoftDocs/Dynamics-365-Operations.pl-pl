--- 
title: "Projektowanie konfiguracji do importowania danych z zewnętrznego pliku w formacie CSV (ER)"
description: "Za pomocą tej procedury można zaprojektować konfigurację raportowania elektronicznego (RE) w celu importowania danych do aplikacji Dynamics 365 for Finance and Operations Enterprise Edition z zewnętrznego pliku w formacie CSV."
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 74606b1378e94e8a6945a408520c8b68648970d8
ms.openlocfilehash: 5c1766992531ee272ea156bc33c4c0ea8dfac27a
ms.contentlocale: pl-pl
ms.lasthandoff: 02/07/2018

---
# <a name="design-a-configuration-to-import-data-from-an-external-file-in-csv-format-er"></a>Projektowanie konfiguracji do importowania danych z zewnętrznego pliku w formacie CSV (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Za pomocą tej procedury można zaprojektować konfigurację raportowania elektronicznego (RE) w celu importowania danych do aplikacji Dynamics 365 for Finance and Operations Enterprise Edition z zewnętrznego pliku w formacie CSV. W tej procedurze utworzysz wymagane konfiguracje ER dla przykładowej firmy Litware, Inc. Aby wykonać te kroki, najpierw trzeba wykonać kroki wymienione w procedurze „ER Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”. 

Ta procedura została utworzona dla użytkowników z przypisaną rola administratora systemu lub dewelopera raportowania elektronicznego. Kroki można wykonać przy użyciu zestawu danych firmy USMF. 

Należy również pobrać i zapisać lokalnie następujące pliki: (https://go.microsoft.com/fwlink/?linkid=862266): 1099model.xml, 1099formatcsv.xml, 1099entriescsv.csv.

1. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.
    * Można skonfigurować proces do importowania zewnętrznych plików w formacie XML, TXT lub CSV do tabel w aplikacji Dynamics 365 for Finance and Operations Enterprise Edition. Najpierw należy utworzyć abstrakcyjny model danych reprezentujący zaimportowane dane, z punktu widzenia biznesu – w tym celu tworzy się konfigurację modelu danych ER. Następnie należy zdefiniować strukturę zaimportowanego pliku umożliwiającą mapowanie do zaprojektowanego modelu danych, aby połączyć dane z pliku z abstrakcyjnym modelem danych – w tym celu tworzy się konfigurację w formacie ER. Następnie należy rozszerzyć konfigurację modelu danych ER o mapowanie nowego modelu opisujące, jak dane z zaimportowanego pliku oraz dane utrwalone z abstrakcyjnego modelu danych będą wykorzystywane w celu aktualizacji tabeli aplikacji lub jednostek danych.  
    * Poniższa procedura pokazuje, jak śledzone zewnętrznie transakcje dostawców są importowane z zewnętrznego pliku CSV do późniejszego użytku w rozliczeniu dostawcy dla formularzy deklaracji 1099.   
    * Sprawdź, czy dostawca konfiguracji przykładowej firmy Litware, Inc. jest dostępny i oznaczony jako aktywny. Jeśli ten dostawca konfiguracji nie jest widoczny, należy najpierw wykonać procedurę „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.  
2. Kliknij opcję Konfiguracje raportowania.
3. Zastosuj filtr „Model płatności 1099”. Jeśli procedura „Tworzenie wymaganych konfiguracji do importowania danych z pliku zewnętrznego na potrzeby raportowania elektronicznego (ER)” została już wykonania, a konfiguracja „Model płatności 1099” jest dostępna w drzewie konfiguracji, pomiń wszystkie kroki w kolejnym podzadaniu.   

## <a name="add-a-new-er-model-configuration"></a>Dodawanie nowej konfiguracji modelu ER
1. Zamiast tworzyć nowy model do obsługi importu danych załaduj pobrany wcześniej plik 1099model.xml. Ten plik zawiera niestandardowy model danych transakcji z dostawcami. Ten model danych jest już zmapowany do wymaganych składników danych.  
2. Kliknij opcję Import/eksport.
3. Kliknij opcję Załaduj z pliku XML.
4. Kliknij przycisk Przeglądaj i przejdź do pliku 1099model.xml, który został wcześniej pobrany.  
5. Kliknij przycisk OK.

## <a name="add-a-new-er-format-configuration-that-supports-data-import"></a>Dodawanie nowej konfiguracji formatu ER obsługującej import danych
1. W drzewie zaznacz element „Model płatności 1099”.
2. Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.
3. W polu Nowy wpisz „Format oparty na modelu danych Model płatności 1099”.
4. Wybierz opcję Tak w polu Obsługuje import danych.
5. Naciśnij klawisz ESC, aby zamknąć tę stronę.
    * Zamiast tworzyć nowy format ER do obsługi importu danych, załaduj pobrany wcześniej plik 1099formatcsv.xml. Plik ten zawiera wymagany format ER, który definiuje strukturę importowanego pliku CSV oraz mapowanie tej struktury do modelu danych transakcji dostawców.   
6. Kliknij opcję Import/eksport.
7. Kliknij opcję Załaduj z pliku XML.
    * Kliknij przycisk Przeglądaj i przejdź do pliku 1099formatcsv.xml, który został wcześniej pobrany.  
8. Kliknij przycisk OK.
9. W drzewie rozwiń węzeł „Model płatności 1099”.
10. W drzewie zaznacz element „Model płatności 1099\Do importowania transakcji z dostawcami (CSV)”.

## <a name="review-format-settings"></a>Przeglądanie ustawień formatu
1. Kliknij przycisk Konstruktor.
2. Kliknij przycisk Rozwiń/zwiń.
3. Włącz opcję „Pokaż szczegóły”.
    * Zaprojektowany format reprezentuje oczekiwaną strukturę pliku zewnętrznego w formacie CSV.  
4. W drzewie wybierz opcję „Przychodzący: Plik\Główny: Sekwencja”.
    * Dla elementu głównego typu SEQUENCE wybrano opcję „Nowy wiersz – Windows (CR LF)” w polu „Znaki specjalne”. Na podstawie tego ustawienia każdy wiersz analizy pliku musi być traktowany jako oddzielny rekord.   
5. W drzewie wybierz opcję „Przychodzący: Plik\Główny: Sekwencja\Wiersz: Sequence 1..*”.
    * Dla elementu Główny\Wiersz typu SEQUENCE wybrano w polu „Liczebność” opcję „Jeden wiele”. Na podstawie tego ustawienia co najmniej jeden wiersz zostanie wyświetlony w podczas analizowania składni pliku.   
6. W drzewie wybierz opcję „Przychodzący: Plik\Główny: Sekwencja\Wiersz: Sequence 1..* \Typy: Przypadek”.
    * Należy zauważyć, że element Główny\Wiersz\Typy o typie CASE został dodany jako zagnieżdżony element sekwencji Główny\Wiersz. Element CASE zawiera 3 zagnieżdżone elementy sekwencji, dlatego to ustawienie zakłada, że oczekujemy uzyskania 3 różnych typów wierszy w pliku analizy składni.   
7. W drzewie wybierz opcję „Przychodzący: Plik\Główny: Sekwencja\Wiersz: Sequence 1..* \Typy: Przypadek\Nagłówek: Sequence 1..1 ”.
    * Element Główny\Wiersz\Typy\Nagłówek typu SEQUENCE zawiera zagnieżdżony element STRING, którego wartość została zdefiniowana jako stała wartość ciągu. Ta sekwencja analizuje składnię wiersz nagłówka podczas analizowania składni pliku.   
8. W drzewie wybierz opcję „Przychodzący: Plik\Główny: Sekwencja\Wiersz: Sequence 1..* \Typy: Przypadek\Rekord: Sequence 1..1 (,)”.
    * Element Główny\Wiersz\Typy\Rekord typu SEQUENCE skonfigurowano do analizy składni wierszy transakcji. Należy zauważyć, że jako znak „Ogranicznik niestandardowy” wybrano przecinek. Oznacza to, że przecinek posłuży jako separator pól dla tego typu wiersza w pliku analizy składni.   
    * Należy zauważyć, że dodano kilka zagnieżdżonych elementów różnych typów danych dla elementu Główny\Wiersz\Typy\Rekord, aby podczas analizy składni wiersze transakcji były traktowane jak odrębne pola. Należy zauważyć, że opcja "Wniosek oferty" został skonfigurowany jako "Brak". Oznacza to, że w pliku analizy składni wszystkie pola tego typu będą traktowane tak, jakby nie zawierały znaków w nawiasie.   
9. W drzewie wybierz opcję „Przychodzący: Plik\Główny: Sekwencja\Wiersz: Sequence 1..* \Typy: Przypadek\Rekord: Sequence 1..1 (,)\TransactionDate: DateTime”.
    * Na przykład element Główny\Wiersz\Typy\Rekord\TransactionDate typu DATETIME skonfigurowano tak, aby z pliku analizy składni uzyskiwać wartość daty i godziny transakcji w formacie „m/d/rrrr”.   
10. W drzewie wybierz opcję „Przychodzący: Plik\Główny: Sekwencja\Wiersz: Sequence 1..* \Typy: Przypadek\Rekord: Sequence 1..1 (,)\CountryCode: Ciąg 0..1 ”.
    * Należy zauważyć, że element Główny\Wiersz\Typy\Rekord\CountryCode typu STRING skonfigurowano z uwzględnieniem opcji „Zero jeden” w polu „Liczebność”. To ustawienie bierze pod uwagę wartość pola CountryCode w wierszu analizy składni jako opcjonalną.   
11. W drzewie wybierz opcję „Przychodzący: Plik\Główny: Sekwencja\Wiersz: Sequence 1..* \Typy: Przypadek\Rekord: Sequence 1..1 (,)\Uwaga: Sequence 1..1 (,)”.
    * Należy zauważyć, że element Główny\Wiersz\Typy\Rekord\Uwaga typu SEQUENCE skonfigurowano z uwzględnieniem opcji „Wszystko” w polu „Zgłoszenie oferty” i znakiem podwójnego cudzysłowu w polu „Cudzysłów”. Oznacza to, że wszystkie pola wierszy tego typu w pliku analizy składni (opisane przez zagnieżdżone elementy: Tekst typu STRING) będą uważane za ujęte w znaki podwójnego cudzysłowu.  
12. W drzewie wybierz opcję „Przychodzący: Plik\Główny: Sekwencja\Wiersz: Sequence 1..* \Typy: Przypadek\Nieprzeanalizowane: Sequence 1..1 ”.
    * Element Główny\Wiersz\Typy\Nieprzeanalizowane typu SEQUENCE skonfigurowano do analizy składni wierszy transakcji dla struktury niezgodnej ze strukturą opisaną powyżej w elemencie nadrzędnym typu CASE.   

## <a name="review-the-setting-of-the-format-mapping-to-the-data-model"></a>Przeglądanie ustawień mapowania formatu do modelu danych
1. Kliknij opcję Mapuj format na model.
    * Model mapowania „Mapowanie do modelu z formatu CSV” opisuje przepływ danych przy przenoszeniu danych z importowanego pliku CSV do modelu danych.   
2. Kliknij przycisk Konstruktor.
3. W drzewie rozwiń węzeł „format”.
    * Należy zauważyć, że zaprojektowany format jest tutaj prezentowany jako składnik źródła danych.  
4. W drzewie rozwiń węzeł „format\Przychodzący: File(Incoming)”.
5. W drzewie rozwiń węzeł „format\Przychodzący: File(Incoming)\Główny: Sequence(Root)”.
6. W drzewie rozwiń węzeł „format\Przychodzący: File(Incoming)\Główny: Sequence(Root)\Wiersz: Sequence 1..* (Wiersz)”.
7. W drzewie rozwiń węzeł „format\Przychodzący: File(Incoming)\Główny: Sequence(Root)\Wiersz: Sequence 1..* (Wiersz)\Typy: Case(Types)”.
8. W drzewie rozwiń węzeł „format\Przychodzący: File(Incoming)\Główny: Sequence(Root)\Wiersz: Sequence 1..* (Wiersz)\Typy: Case(Types)\Rekord: Sequence 1..1 (,)(Record)”.
9. W drzewie rozwiń węzeł „format\Przychodzący: File(Incoming)\Główny: Sequence(Root)\Wiersz: Sequence 1..* (Wiersz)\Typy: Case(Types)\Rekord: Sequence 1..1 (,)(Record)\Dane”.
10. W drzewie rozwiń węzeł „format\Przychodzący: File(Incoming)\Główny: Sequence(Root)\Wiersz: Sequence 1..* (Wiersz)\Typy: Case(Types)\Rekord: Sequence 1..1 (,)(Record)\Dane\CountryCode: Ciąg 0..1(CountryCode)”.
11. W drzewie wybierz kolejno „format\Przychodzący: File(Incoming)\Główny: Sequence(Root)\Wiersz: Sequence 1..* (Wiersz)\Typy: Case(Types)\Rekord: Sequence 1..1 (,)(Record)\Dane\TransactionDate: DateTime(TransactionDate)”.
    * Należy zwrócić uwagę, że wymagane i opcjonalne elementy formatu, takie jak TransactionDate i CountryCode, różnią się we wstępnie zdefiniowanym składniku źródła danych „formatu”.   
12. W drzewie rozwiń węzeł „Transakcje = '$both'”.
    * Należy zwrócić uwagę, że elementy formatu określające strukturę importowanego pliku są powiązane z elementami modelu danych. Na podstawie tych powiązań zawartość importowanego pliku CSV będzie zapisywana w czasie wykonywania w istniejącym modelu danych. Należy zwrócić uwagę na powiązanie elementu CountryRegion. Dla każdego elementu transakcji w importowanym pliku, który nie ma określonej wartości kodu kraju, w modelu danych zostanie wpisany domyślnie kod kraju „USA”.   
13. Włącz opcję „Pokaż szczegóły”.
14. Kliknij kartę Weryfikacje.
15. Kliknij przycisk Wyszukaj.
16. W polu Znajdź wpisz „dost”.
17. Kliknij przycisk Znajdź następny.
    * To mapowanie formatu może zawierać logikę zdefiniowaną przez użytkownika służącą do sprawdzania poprawności dokładności zaimportowanych danych z biznesowego punktu widzenia. Przykładowo na podstawie tego ustawienia dla każdego wiersza w pliku importowania, którego struktura nie pasuje do struktury wiersza nagłówka ani wiersza transakcji, w dzienniku informacyjnym zostanie wygenerowany komunikat o błędzie informujący użytkownika tej sytuacji ze wskazaniem numeru sekwencji transakcji w pliku.   
18. Zamknij stronę.

## <a name="run-the-format-mapping"></a>Uruchamianie mapowania
W celach testowych wykonaj mapowanie formatu z użyciem pliku 1099entriescsv.csv, który został wcześniej pobrany. Wygenerowane dane wyjściowe będą przedstawiać dane, które zostaną zaimportowane z wybranego pliku CSV i wypełnią niestandardowy model danych podczas rzeczywistego importowania.   
1. Kliknij przycisk Uruchom.
    * Kliknij przycisk Przeglądaj i przejdź do pliku 1099entriescsv.csv, który został wcześniej pobrany.  
2. Kliknij przycisk OK.
    * Należy zwrócić uwagę na komunikaty ostrzegawcze dotyczące wierszy, które nie są akceptowane. Wiersz 4 zawiera wartość przychodów w niedopuszczalnym formacie, a tekst uwagi do transakcji w wierszu 7 nie jest w podwójnym cudzysłowie.   
    * Przejrzyj dane wyjściowe w formacie XML, które reprezentują dane zaimportowane z wybranego pliku i przeniesione do modelu danych. Należy zauważyć, że wszystkie 7 wierszy zaimportowanego pliku CSV zostało przetworzone. Wiersz 1 zawierający tytuły pól został pominięty, 4 transakcje zostały poprawnie przeanalizowane, a 2 transakcje zostały rozpoznane jako nieprawidłowe.   
3. Zamknij stronę.
4. Zamknij stronę.


