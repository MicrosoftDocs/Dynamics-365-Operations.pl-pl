---
title: Projektowanie konfiguracji raportowania elektronicznego do analizowania dokumentów przychodzących
description: Ta procedura przedstawia sposób projektowania konfiguracji raportowania elektronicznego (ER) do analizowania przychodzącego dokumentu elektronicznego.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 446a4676ad00c93d691d3048408c32d7ad373d2d
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682100"
---
# <a name="design-er-configurations-to-parse-incoming-documents"></a>Projektowanie konfiguracji raportowania elektronicznego do analizowania dokumentów przychodzących

[!include [banner](../../includes/banner.md)]

Ta procedura przedstawia sposób projektowania konfiguracji raportowania elektronicznego (ER) do analizowania przychodzącego dokumentu elektronicznego. W tej procedurze zaimportujesz wymaganą konfigurację ER, którą utworzono dla przykładowej firmy Litware, Inc., i będziesz jej używać do analizowania przychodzących dokumentów elektronicznych. Aby wykonać kroki podane w tej procedurze, należy najpierw wykonać procedurę „ER Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.

Ta procedura została utworzona dla użytkowników z przypisaną rola administratora systemu lub dewelopera raportowania elektronicznego.

Kroki te można wykonać przy użyciu dowolnego zestawu danych. Zanim rozpoczniesz, pobierz i zapisz pliki wymienione w temacie „Analizowanie dokumentów przychodzących w celu aktualizacji danych aplikacji” ([Analizowanie dokumentów przychodzących](../parse-incoming-electronic-documents.md)). Są to następujące pliki: EFSTA model.xml, EFSTA format.xml, Response1.xml, Response2.xml, Response3.xml, Response4.xml.

1. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.
    * Upewnij się, że dostawca konfiguracji przykładowej firmy Litware, Inc. jest dostępny i oznaczony jako Aktywny. Jeśli ten dostawca konfiguracji nie jest widoczny, wykonaj procedurę „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.
2. Wybierz Raportowanie konfiguracji.
    * Poniższy scenariusz będzie używany do wyświetlania możliwości analizy przychodzących dokumentów elektronicznych w formacie XML: aplikacja ERP () żąda danych z usługi sieci web (np. usługi obrachunkowej [EFSTA](http://efsta.org/)) i analizuje przychodzące odpowiedzi, aby odpowiednio zaktualizować dane aplikacji. Aby zapewnić najwyższą efektywność analizy, używany jest jeden format ER pomimo różnej struktury oczekiwanych dokumentów przychodzących w formacie XML.

## <a name="import-and-review-er-configurations"></a>Importowanie i przeglądanie konfiguracji ER

Zaimportuj konfigurację modelu ER, która zawiera próbny model danych przeznaczony do zapisywania informacji szczegółowych o pliku przychodzącym.

1. Wybierz Zamień.
2. Wybierz Załaduj z pliku XML.
    * Kliknij przycisk Przeglądaj i wybierz plik EFSTA (model).xml.
3. Kliknij przycisk OK.
4. W drzewie wybierz element „Model EFSTA”.
5. Wybierz opcję Konstruktor.
    * Przejrzyj strukturę zaimportowanego modelu danych. Wyliczenie enumType jest definiowane w celu rozpoznania następujących typów odpowiedzi usługi: potwierdzenia przesłania transakcji, informacji o ostatniej przesłanej transakcji, rozpoznawania nieobsługiwanych typów odpowiedzi.
6. W drzewie rozwiń węzeł „Odpowiedź”.
    * Do określania, jakiego rodzaju dane muszą zostać pobrane z obsługiwanej odpowiedzi usługi w celu aktualizacji danych aplikacji, zdefiniowano element główny „Odpowiedź”.
7. Zamknij stronę.
    * Zaimportowana zostanie konfiguracja formatu ER, która określa sposób analizowania dokumentów przychodzących w celu zapisu danych w modelu danych ER.
8. Wybierz Zamień.
9. Wybierz Załaduj z pliku XML.
    * Kliknij przycisk Przeglądaj i wybierz plik EFSTA format.xml.
10. Kliknij przycisk OK.
11. W drzewie rozwiń węzeł „Model EFSTA”.
12. W drzewie wybierz element „Model EFSTA\Format EFSTA”.
13. Wybierz opcję Konstruktor.
14. Wybierz Rozwiń/zwiń.
    * Element formatu CASE jest używany jako główny i zawiera trzy zagnieżdżone elementy FILE, co oznacza, że ten format został zaprojektowany do analizowania plików przychodzących w kilku formatach.
15. W drzewie wybierz kolejno elementy „Odpowiedzi\Ukończenie transakcji\TraC”.
    * Odpowiedź dotycząca transakcji przesłanych zaczyna się od elementu głównego „TraC”.
16. W drzewie wybierz kolejno elementy „Odpowiedzi\Ostatnie żądanie transakcji\Tra”.
    * Odpowiedź dotycząca ostatniej przesłanej transakcji zaczyna się od elementu głównego „Era”.
17. W drzewie wybierz kolejno „Odpowiedzi\Nieoczekiwana odpowiedź\Tekst”.
    * Trzeci element FILE z zagnieżdżonym elementem TEXT dodano w celu rozpoznawania wszelkich innych typów odpowiedzi, które różnią się od wymienionych powyżej.
18. Wybierz opcję Mapuj format na model.
    * To mapowanie modelu zawiera definicję przepływu danych w celu zapisania szczegółów przeanalizowanego dokumentu przychodzącego przy użyciu elementu modelu danych.
19. Wybierz opcję Konstruktor.
20. W drzewie rozwiń węzeł „format”.
21. W drzewie rozwiń węzeł „format\Odpowiedzi: Case(Responses)”.
    * Przejrzyj strukturę źródła danych „format”. Wszystkie trzy typy odpowiedzi oferowane są oddzielnie.
22. W drzewie wybierz kolejno „format\Odpowiedzi: Case(Responses)\aType”.
    * Element źródła danych „aType” został dodany w celu wskazania typu odpowiedzi i jest on powiązany z elementem modelu danych „Typ”.
23. Kliknij kartę Weryfikacje.
24. W drzewie wybierz opcję „Typ = format.Responses.aType”.
    * Sprawdzanie poprawności ER skonfigurowano tak, aby użytkownik był informowany o sytuacji, gdy struktura odpowiedzi nie pasuje do potwierdzenia przesłania transakcji lub informacji o ostatniej przesłanej transakcji (przypadek nieobsługiwanej odpowiedzi).
25. Zamknij stronę.

## <a name="run-model-mapping-of-er-format-configured-for-parsing-incoming-files"></a>Uruchamianie mapowania modelu formatu ER skonfigurowanego do analizowania plików przychodzących

Utworzone mapowanie modelu zostaje uruchomione w celach testowych, aby zobaczyć, jak skonfigurowany format ER będzie analizował przychodzące odpowiedzi usługi. W tym kroku różne pliki XML są wykorzystywane do symulacji różnych rodzajów odpowiedzi usług sieci web.

1. Otwórz plik Response1.xml w programie do odczytu plików xml, np. w przeglądarce sieci web. Ten plik zawiera szczegółowe informacje na temat potwierdzenia ukończenia transakcji („TraC” jest elementem głównym).
2. Wybierz opcjęUruchom.
    * Kliknij przycisk Przeglądaj i wybierz plik Response1.xml.
3. Kliknij przycisk OK.
    * Przejrzyj wygenerowane dane wyjściowe. Typ odpowiedzi został poprawnie rozpoznany i przeanalizowany (`ERModelEnumDataSourceHandler#EFSTA model#enumType#C` oznacza przypadek ukończonej transakcji).
    * Otwórz plik Response2.xml w programie do odczytu plików XML. Ten plik zawiera informacje na temat ostatniej przesłanej transakcji (`Tra` jest elementem głównym).
4. Wybierz opcjęUruchom.
    * Kliknij przycisk Przeglądaj i wybierz plik Response2.xml.
5. Kliknij przycisk OK.
    * Przejrzyj wygenerowane dane wyjściowe. Typ odpowiedzi został poprawnie rozpoznany i przeanalizowany (`ERModelEnumDataSourceHandler#EFSTA model#enumType#R` oznacza przypadek ponownego uruchomienia systemu).
    * Otwórz plik Response3.xml w programie do odczytu plików XML. Ten plik zaczyna się od elementu głównego TraZ, a ta struktura nie jest skonfigurowana przy użyciu formatu ER.
6. Wybierz opcjęUruchom.
    * Kliknij przycisk Przeglądaj i wybierz plik Response3.xml.
7. Kliknij przycisk OK.
    * Przejrzyj wygenerowane dane wyjściowe. Typ odpowiedzi został poprawnie rozpoznany jako nieobsługiwany (`ERModelEnumDataSourceHandler#EFSTA model#enumType#U`). Odpowiedni komunikat został umieszczony w dzienniku informacyjnym (zgodnie z ustawieniem sprawdzania poprawności ER), a większość modelu danych nie została wypełniona.
    * Otwórz plik Response4.xml w programie do odczytu plików XML. Struktura tego pliku prawie taka sama, jak pomyślnie przeanalizowanego pliku Response1.xml, z wyjątkiem sekwencji elementów zagnieżdżonych głównego elementu „TraC”.
8. Wybierz opcjęUruchom.
    * Kliknij przycisk Przeglądaj i wybierz plik Response4.xml.
9. Kliknij przycisk OK.
    * Przejrzyj wygenerowane dane wyjściowe. Typ odpowiedzi został poprawnie rozpoznany jako nieobsługiwany (`ERModelEnumDataSourceHandler#EFSTA model#enumType#U`). Odpowiedni komunikat został umieszczony w dzienniku informacyjnym, a większość modelu danych nie została wypełniona. Dzieje się tak dlatego, że bieżące ustawienie tego formatu ER zakłada określoną sekwencję elementów zagnieżdżonych elementu głównego pliku przychodzącego.
10. Zamknij stronę.
11. W drzewie wybierz kolejno elementy „Odpowiedzi\Ukończenie transakcji\TraC”.
12. W polu Kolejność analizowania elementów zagnieżdżonych wybierz opcję „Dowolna”.
    * W polu „Kolejność analizowania elementów zagnieżdżonych” wybierz opcję Dowolna, aby zezwolić na dowolną kolejność elementów zagnieżdżonych dla danego głównego elementu XML.
13. Wybierz opcję Zapisz.
14. Wybierz opcję Mapuj format na model.
15. Wybierz opcjęUruchom.
    * Kliknij przycisk Przeglądaj i wybierz plik Response4.xml.
16. Kliknij przycisk OK.
    * Przejrzyj wygenerowane dane wyjściowe. Typ odpowiedzi został teraz poprawnie rozpoznany jako równy dla pliku Response1.xml.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]