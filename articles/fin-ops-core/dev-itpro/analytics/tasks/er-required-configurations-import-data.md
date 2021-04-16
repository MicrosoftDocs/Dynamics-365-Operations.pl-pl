---
title: ER Tworzenie wymaganych konfiguracji do importowania danych z pliku zewnętrznego
description: W tym temacie opisano sposób projektowania konfiguracji raportowania elektronicznego w celu importowania danych do aplikacji Microsoft Dynamics 365 Finance z zewnętrznego pliku.
author: NickSelin
ms.date: 03/24/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERSolutionCreateDropDialog, EROperationDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula, Tax1099Summary, VendSettlementTax1099
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2194bdc918035bf3aebe9b90ddc8a30f9937bb0c
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751469"
---
# <a name="er-create-required-configurations-to-import-data-from-an-external-file"></a>ER Tworzenie wymaganych konfiguracji do importowania danych z pliku zewnętrznego

[!include [banner](../../includes/banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może projektować konfiguracje raportowania elektronicznego (ER) w celu importowania danych do aplikacji z zewnętrznego pliku. W tym przykładzie utworzysz wymagane konfiguracje ER dla przykładowej firmy Litware, Inc. Aby wykonać te kroki, najpierw trzeba wykonać kroki wymienione w przewodniku po zadaniu „ER Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”. Kroki można wykonać przy użyciu zestawu danych firmy USMF. Musisz również pobrać i lokalnie zapisać następujące pliki: 

| Opis zawartości                       | Nazwa pliku                                     |
|-------------------------------------------|-----------------------------------------------|
| Konfiguracja modelu danych ER - 1099 | [1099model,xml](https://download.microsoft.com/download/b/d/9/bd9e8373-d558-4ab8-aa9b-31981adc97ea/1099model.xml)                  |
| ER format konfiguracji - 1099    | [1099format.xml](https://download.microsoft.com/download/e/8/7/e87154b0-b53f-431f-8e1e-0b7f7c9805a9/1099format.xml)                  |
| Przykład pliku przychodzącego dokumentu w formacie XML                          | [1099entries.xml](https://download.microsoft.com/download/4/0/3/403a4958-df24-476a-b8b0-6843a9fa7f89/1099entries.xml)        |
| Przykładowy skoroszyt do zarządzania danymi dokumentu przychodzącego                          | [1099entries.xlsx](https://download.microsoft.com/download/6/0/0/6001abab-a331-48db-a939-41851fb0f5d0/1099entries.xlsx) |

Moduł Raportowanie elektroniczne umożliwia użytkownikom biznesowym skonfigurowanie procesu importowania zewnętrznych plików danych do tabel w formacie .XML lub .TXT. Najpierw należy zaprojektować abstrakcyjny model danych i konfigurację modelu danych raportowania elektronicznego, aby reprezentować dane, które mają być importowane. Następnie należy zdefiniować strukturę importowanego pliku oraz metodę, która będzie używana do przeniesienia danych z pliku do abstrakcyjnego modelu danych. Dla abstrakcyjnego modelu danych należy utworzyć ER konfigurację formatu, która jest mapowana na zaprojektowany model danych. Następnie konfiguracja modelu danych musi zostać rozszerzona o mapowanie opisujące, jak importowane dane są utrwalane jako abstrakcyjny model danych i jak są wykorzystywane do aktualizowania tabel.  Do konfiguracji modelu danych raportowania elektronicznego należy dołączyć nowe mapowanie modelu, które opisuje powiązanie modelu danych z miejscami docelowymi aplikacji.  

Poniższy scenariusz pokazuje możliwości funkcji importu danych raportowania elektronicznego. Obejmuje to transakcje z dostawcami, które są śledzone zewnętrznie, a następnie importowane w celu późniejszego zaraportowania w rozliczeniach z dostawcą w deklaracji 1099.   

## <a name="add-a-new-er-model-configuration"></a>Dodawanie nowej konfiguracji modelu ER
1. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.

    Sprawdź, czy dostawca konfiguracji przykładowej firmy „Litware, Inc.” jest dostępny i oznaczony jako aktywny. Jeśli ten dostawca konfiguracji nie jest widoczny, należy najpierw wykonać procedurę „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.   

2. Kliknij opcję Konfiguracje raportowania.

    Zamiast tworzyć nowy model do obsługi importu danych załaduj plik 1099model.xml, który wcześniej pobrano. Ten plik zawiera niestandardowy model danych transakcji z dostawcami. Ten model danych jest mapowany na składniki danych znajdujące się w jednostce danych drzewa obiektów aplikacji.   

3. Kliknij opcję Import/eksport.
4. Kliknij opcję Załaduj z pliku XML.

    Kliknij przycisk Przeglądaj i przejdź do pliku 1099model.xml, który został wcześniej pobrany.  

5. Kliknij przycisk OK.
6. W drzewie zaznacz element „Model płatności 1099”.

## <a name="review-data-model-settings"></a>Przeglądanie ustawień modelu danych
1. Kliknij przycisk Konstruktor.

    Ten model jest przeznaczony do reprezentowania transakcji z dostawcami z perspektywy biznesowej i jest oddzielony od implementacji.   

2. W drzewie rozwiń węzeł „1099-MISC”.
3. W drzewie zaznacz element „1099-MISC\Transakcje”.
4. W drzewie rozwiń węzeł „1099-MISC\Transakcje”.

    W tym modelu element Transakcje reprezentuje poszczególne transakcje. Elementy podrzędne służą do określania wymaganych szczegółów, takich jak konto dostawcy i data transakcji, dla każdej transakcji.   

5. Zamknij stronę.

## <a name="add-a-new-er-format-configuration-that-supports-data-import"></a>Dodawanie nowej konfiguracji formatu ER obsługującej import danych
Kroki opisane w tym podzadaniu pokazują, jak można utworzyć nową konfigurację formatu w celu zarządzania importowaniem danych z plików zewnętrznych.   
1. Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.
2. W polu Nowy wpisz „Format oparty na modelu danych Model płatności 1099”.
3. Wybierz opcję Tak w polu Obsługuje import danych.
4. Naciśnij klawisz ESC, aby zamknąć tę stronę.

    Zamiast tworzyć nowy format do obsługi importu danych załaduj plik 1099format.xml, który wcześniej pobrano. Ten plik zawiera zdefiniowaną strukturę importowanego pliku oraz mapowanie struktury na niestandardowy model danych transakcji z dostawcami.   
5. Kliknij opcję Import/eksport.
6. Kliknij opcję Załaduj z pliku XML.
    Kliknij przycisk Przeglądaj i przejdź do pliku 1099format.xml, który został wcześniej pobrany.  
7. Kliknij przycisk OK.
8. W drzewie rozwiń węzeł „Model płatności 1099”.
9. W drzewie zaznacz element „Model płatności 1099\Format do importowania transakcji z dostawcami”.

## <a name="review-format-settings"></a>Przeglądanie ustawień formatu
1. Kliknij przycisk Konstruktor.
2. Włącz opcję „Pokaż szczegóły”.
3. Kliknij przycisk Rozwiń/zwiń.
4. Kliknij przycisk Rozwiń/zwiń.

    Zaprojektowany format reprezentuje oczekiwaną strukturę pliku zewnętrznego. Ten plik musi być w formacie XML i mieć element główny dotyczący rozliczenia. Każda transakcja z dostawcą jest reprezentowana przez element transakcji zdefiniowany jako posiadający liczebność zero-do-wielu. Oznacza to, że przychodzący plik może zawierać od zera do wielu transakcji. Zagnieżdżone elementy elementu „transakcja” reprezentują atrybuty pojedynczej transakcji. Należy zwrócić uwagę, że wszystkie atrybuty, z wyjątkiem kraju, są oznaczone jako wymagane, co oznacza, że muszą się znajdować w pliku importowania.   

## <a name="review-the-settings-of-the-format-mapping-to-the-data-model"></a>Przeglądanie ustawień mapowania formatu na model danych
1. Kliknij opcję Mapuj format na model.

    Mapowanie „Do importowania transakcji z dostawcami” zawiera reguły przenoszenia danych z przychodzącego pliku XML do wybranej części niestandardowego modelu danych, którą się definiuje przez wybranie definicji 1099-MISC.  

2. Kliknij przycisk Konstruktor.
3. Włącz opcję „Pokaż szczegóły”.
4. W drzewie rozwiń węzeł „format: Rekord”.
5. W drzewie zaznacz element „format: Rekord”.

    Należy zauważyć, że zaprojektowany format jest tutaj prezentowany jako składnik źródła danych.  

6. W drzewie rozwiń węzeł `format: Record\*settlement: XML Element 1..1 (settlement): Record`.
7. W drzewie rozwiń węzeł `format: Record\*settlement: XML Element 1..1 (settlement): Record\transaction: XML Element 0..* (transaction): Record list`.
8. W drzewie rozwiń węzeł `format: Record\*settlement: XML Element 1..1 (settlement): Record\transaction: XML Element 0..* (transaction): Record list\*vendor: XML Element 1..1 (vendor): Record`.
9. W drzewie rozwiń węzeł `format: Record\*settlement: XML Element 1..1 (settlement): Record\transaction: XML Element 0..* (transaction): Record list\country: XML Element 0..1 (country): Record`.
10. W drzewie zaznacz węzeł `format: Record\*settlement: XML Element 1..1 (settlement): Record\transaction: XML Element 0..* (transaction): Record list\*vendor: XML Element 1..1 (vendor): Record`.

    Należy zauważyć, że prezentacja obowiązkowych i opcjonalnych elementów formatu różni się od wstępnie zdefiniowanego składnika „format” źródła danych.  
11. W drzewie rozwiń węzeł „Transakcje: Lista rekordów = format.rozliczenie.'$enumerated'”.

    Należy zwrócić uwagę, że elementy formatu określające strukturę importowanego pliku są powiązane z elementami niestandardowego modelu danych. Na podstawie tych powiązań zawartość importowanego pliku XML będzie zapisywana w czasie wykonywania w istniejącym modelu danych. Należy zwrócić uwagę na powiązanie elementu kraju. Dla każdego elementu transakcji w przychodzącym pliku, który nie zawiera tego elementu, w modelu danych zostanie wpisany domyślnie kod kraju „USA”.  

12. Kliknij kartę Weryfikacje.

    To mapowanie formatu może zawierać logikę zdefiniowaną przez użytkownika służącą do sprawdzania poprawności dokładności zaimportowanych danych z biznesowego punktu widzenia. Na przykład na podstawie ustawienia dla każdej transakcji w importowanym pliku niemającej zdefiniowanego kodu kraju zostanie wygenerowany ostrzegawczy o błędzie w dzienniku informacyjnym. Będzie on informował użytkownika o sprawie i wskazywał numer kolejny transakcji.  

13. Zamknij stronę.

## <a name="run-the-format-mapping-to-the-data-model"></a>Uruchamianie mapowania formatu na model danych
Uruchom to mapowanie formatu w celach testowych. Użyj pobranego wcześniej pliku 1099entries.xml. Ten plik można wyeksportować ze skoroszytu 1099entries.xlsx służącego do zarządzania transakcjami z dostawcami. Wygenerowane dane wyjściowe zostaną zaimportowane z wybranego pliku XML i wypełnią niestandardowy model danych podczas rzeczywistego importowania.  

1. Kliknij przycisk Uruchom.

    Kliknij przycisk Przeglądaj i przejdź do pliku 1099entries.xml, który został wcześniej pobrany.  

2. Kliknij przycisk OK.

    Należy zwrócić uwagę na komunikat ostrzegawczy o braku kodu kraju dla transakcji w importowanym pliku.  
    
    Przejrzyj dane wyjściowe w formacie XML, które reprezentują dane zaimportowane z wybranego pliku i przeniesione do modelu danych.   

3. Zamknij stronę.
4. Zamknij stronę.

## <a name="review-the-settings-for-the-model-mapping-to-the-destinations"></a>Przeglądanie ustawień mapowania modelu na lokalizacje docelowe
1. W drzewie zaznacz element „Model płatności 1099”.
2. Kliknij przycisk Konstruktor.
3. Kliknij opcję Mapuj model na źródło danych.

    Mapowanie „Do ręcznego importu transakcji deklaracji do 1099” zdefiniowano z typem kierunku Do lokalizacji docelowej. Oznacza to, że wprowadzono je w celu obsługi importu danych i zawiera ono ustawienie reguł określających, w jaki sposób zaimportowany zewnętrzny plik i dane utrwalone jako abstrakcyjny model danych są używany do aktualizowania tabeli.  

4. Kliknij przycisk Konstruktor.
5. W drzewie rozwiń węzeł „model: Model danych Model płatności 1099”.
6. W drzewie rozwiń węzeł „model: Model danych Model płatności 1099\Transakcje: Lista rekordów”.

    Należy zauważyć, że zaprojektowany model jest tutaj prezentowany jako element źródła danych. W czasie wykonywania będzie zawierał dane importowane z zewnętrznego pliku. Kilka tabel zostało dodanych jako elementy źródła danych, aby sprawdzić, czy importowane dane są zgodne z danymi w bieżącej aplikacji, w tym czy konto dostawcy importowanych transakcji jest dostępne w systemie, czy istnieje kombinacja kraju importu i kodów stanów/województw, itd.  

7. W drzewie zaznacz element „model: Model danych Model płatności 1099\Transakcje: Lista rekordów\$failed: Pole obliczeniowe = IF(OR(ISEMPTY(model.Transactions.'$refs'.vendor), ISEMPTY(model.Transactions.'$refs'.vendor1099), ISEMPTY(model.Transactions.'$refs'.box1099), ISEMPTY(model.Transactions.'$refs'.country), ISEMPTY(model.Transactions.'$refs'.state), ISEMPTY(model.Transactions.'$refs'.location)), true, false): Boolean”.
8. Kliknij przycisk Edytuj.
9. Kliknij opcję Edytuj formułę.

    W przypadku niepowodzenia co najmniej jednej weryfikacji dla jednej importowanej transakcji transakcja zostanie oznaczona jako zakończona niepowodzeniem przy użyciu atrybutu źródła danych „$failed”.  

10. Zamknij stronę.
11. Kliknij przycisk Anuluj.
12. W drzewie zaznacz element „tax1099trans: Tabela 'VendSettlementTax1099' rekordy = model.Sprawdzono poprawność”.
13. Kliknij opcję Edytuj lokalizację docelową.

    To miejsce docelowe modułu ER zostało dodane w celu określenia, jak importowane dane spowodują zaktualizowanie tabel w aplikacji. W takim przypadku wybrano tabelę danych VendSettlementTax1099. Ponieważ dla rekordu wybrano akcję Wstaw, zaimportowana transakcja zostanie wstawiona do tabeli VendSettlementTax1099. Należy zwrócić uwagę, że mapowanie jednego modelu może zawierać kilka miejsc docelowych. Oznacza to, że importowane dane mogą służyć do aktualizowania wielu tabel aplikacji jednocześnie. Jako miejsc docelowych raportowania elektronicznego można używać tabel, widoków i jednostek danych.   

    Jeśli mapowanie będzie wywoływane z punktu w aplikacji (na przykład przycisku lub elementu menu), który zaprojektowano specjalnie do wykonywania tej akcji, lokalizacja docelowa ER powinna być oznaczona jako punkt integracji. W tym przykładzie jest to punkt ERTableDestination#VendSettlementTax1099.  

14. Kliknij przycisk Anuluj.
15. Kliknij opcję Pokaż wszystko.
16. Kliknij opcję Pokaż tylko zamapowane.
17. W drzewie rozwiń węzeł „tax1099trans: Tabela 'VendSettlementTax1099' rekordy = model.Sprawdzono poprawność”.

    Należy zwrócić uwagę, że z utworzonym miejscem docelowym jest powiązany element źródła danych, który zawiera tylko zweryfikowane transakcje,. Można wyfiltrować zaimportowane transakcje, aby pominąć te, które są niezgodne z danymi aplikacji.  

18. W drzewie zaznacz element „niepowodzenie: Tabela 'VendSettlementTax1099Entity' rekordy = model.Niepowodzenie”.
19. Kliknij kartę Weryfikacje.

    To mapowanie modelu może zawierać logikę zdefiniowaną przez użytkownika służącą do sprawdzania poprawności dokładności zaimportowanych danych z perspektywy istniejących danych aplikacji. Na przykład na podstawie obecnego ustawienia dla każdej transakcji w importowanym pliku mającej konto dostawcy nieistniejące w systemie zostanie wygenerowany komunikat ostrzegawczy. Będzie on informował użytkownika o problemie i wskazywał błędny kod konta dostawcy.  

    Należy zwrócić uwagę, że opcja Akcja po weryfikacji może być używana do każdej weryfikacji w celu określenia, czy proces importowania musi być kontynuowany czy zatrzymany, jak również do wskazania, czy już wykonane operacje wstawiania/aktualizacji można zachować, czy trzeba wycofać.  

20. Kliknij opcję Pokaż tylko zamapowane.
21. Kliknij opcję Pokaż wszystko.
22. Zamknij stronę.

    Uruchom to mapowanie modelu, aby przetestować zaprojektowany format i mapowania modelu. Użyj pliku 1099entries.xml. Dane z wybranego pliku zostaną zaimportowane do systemu.  

23. Kliknij przycisk Uruchom.

    Należy zauważyć, że okno dialogowe nie zawiera żadnych dodatkowych pytań dotyczących mapowania formatu, którego należy użyć do zbadania składni importowanego pliku, a następnie przeniesienia danych do modelu danych. Jest tak, ponieważ obecnie istnieje tylko jeden format korzystający z tego modelu, który jest oznaczony jako przeznaczony do obsługi danych importu.  
    
    Określ identyfikator załącznika w celu odróżnienia importowanych transakcji od innych transakcji, które mogły już zostać wprowadzone ręcznie lub zaimportowane.  

24. W polu Wprowadź identyfikator załącznika wpisz „IMPORT-001”.

    Przejdź do pliku „1099entries.xml” i pobierz go.  

25. Kliknij przycisk OK.

    Lista wygenerowanych ostrzeżeń zawiera informacje dotyczące niepoprawnych kont dostawców, niepoprawnego pola kodu podatku w formularzu 1099, braku kodów krajów itd. Porównaj tę listę ostrzeżeń z treścią pliku XML wykonywania.  

26. Zamknij stronę.
27. Zamknij stronę.
28. Zamknij stronę.
29. Zamknij stronę.
30. Wybierz kolejno opcje Rozrachunki z dostawcami > Zadania okresowe > Podatek 1099 > Rozliczenia dostawcy dotyczące deklaracji 1099.

    Ten formularz pokazuje zbiór wszystkich transakcji w tabeli Tax1099Summary, które zostały utworzone na podstawie zaimportowanych transakcji.  

31. W polu Od dnia ustaw wartość daty równą „2000-01-01”.
32. Kliknij opcję Ręczne transakcje podatku 1099.

    Ten formularz zawiera listę transakcji, które zostały dodane ręcznie, oraz te, które właśnie zostały zaimportowane.  

33. Otwórz filtr kolumny Załącznik.
34. Wprowadź wartość filtru „IMPORT-001” w polu „Załącznik”, używając operatora filtru „zaczyna się od”.

## <a name="review-the-relationship-between-model-and-format-mappings"></a>Przeglądanie relacji między modelem a mapowaniami formatu
1. Zamknij stronę.
2. Zamknij stronę.
3. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.
4. Kliknij opcję Konfiguracje raportowania.
5. W drzewie zaznacz element „Model płatności 1099”.

    Załóżmy, że chcesz umożliwić obsługę importowania tych samych danych, ale w formacie pliku TXT.   

6. Kliknij przycisk Utwórz konfigurację, aby otworzyć okno dialogowe. 
7. W polu Nowy wpisz „Format oparty na modelu danych Model płatności 1099”.
8. W polu Nazwa wpisz „Import danych z pliku TXT”.
9. Wybierz opcję Tak w polu Obsługuje import danych.
10. Kliknij przycisk Utwórz konfigurację.
11. Kliknij przycisk Konstruktor.
12. Kliknij opcję Mapuj format na model.
13. Kliknij przycisk Nowy.
14. W polu Definicja wprowadź lub wybierz wartość.

    Wybierz opcję „1099-MISC”.  

15. W polu Nazwa wpisz „Import danych z pliku TXT”.
16. W polu Opis wpisz „Import danych z pliku TXT”.
17. Kliknij przycisk Zapisz.
18. Zamknij stronę.
19. Zamknij stronę.
20. Kliknij przycisk Edytuj.

    Jeśli została zainstalowana poprawka „KB 4012871 Obsługa mapowań modelu dla Niemiec w osobnych konfiguracjach z możliwością określenia różnych rodzajów warunków wstępnych na potrzeby wdrażania ich w różnych wersjach Dynamics 365 Finance” ([KB 4012871](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871)), wykonaj następny krok „Włączanie flagi „Domyślne dla mapowania modelu”” dla wprowadzonej konfiguracji formatu. W przeciwnym razie pomiń następny krok.  

21. Wybierz opcję Tak w polu Domyślne dla mapowania modelu.
22. W drzewie zaznacz element „Model płatności 1099”.
23. Kliknij przycisk Konstruktor.
24. Kliknij opcję Mapuj model na źródło danych.
25. Kliknij przycisk Uruchom.

    Jeśli została zainstalowana poprawka KB 4012871 Obsługa mapowań modelu dla Niemiec w osobnych konfiguracjach z możliwością określenia różnych rodzajów warunków wstępnych na potrzeby wdrażania ich w różnych wersjach ([KB 4012871](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871)), wybierz preferowane mapowanie modelu w polu wyszukiwania. Jeśli jeszcze nie zainstalowano poprawki, przejdź do następnego kroku, ponieważ mapowanie zostało już wybrane przez definicję domyślnej konfiguracji formatu.  
    
    Jeśli nie zainstalowano poprawki KB 4012871, zwróć uwagę, że okno dialogowe zawiera dodatkowe pytanie o mapowanie modelu, które służy do analizy importowanego pliku. Dane są następnie przenoszone z okna dialogowego do modelu danych. Obecnie można wybrać, które mapowanie formatu ma być używane w zależności od typu pliku planowanego do zaimportowania.  
    
    Jeśli zamierzasz wywołać to mapowanie modelu z punktu w aplikacji, który jest przeznaczony specjalnie dla tej akcji, miejsce docelowe ER i mapowanie formatu muszą być oznaczone jako część integracji.  

26. Kliknij przycisk Anuluj.
27. Zamknij stronę.
28. Zamknij stronę.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
