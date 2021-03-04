---
title: Projektowanie wyrażeń ER do wywoływania metod klas aplikacji
description: Ten przewodnik zawiera informacje, jak ponownie użyć istniejącej logiki aplikacji w konfiguracjach elektronicznego raportowania (RE) poprzez wywołanie wymaganych metod klas aplikacji w wyrażeniach ER.
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
ms.openlocfilehash: 3d79d1a4e86731a62de4896a489a13f624ce159f
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682028"
---
# <a name="design-er-expressions-to-call-application-class-methods"></a>Projektowanie wyrażeń ER do wywoływania metod klas aplikacji

[!include [banner](../../includes/banner.md)]

Ten przewodnik zawiera informacje, jak ponownie użyć istniejącej logiki aplikacji w konfiguracjach elektronicznego raportowania (RE) poprzez wywołanie wymaganych metod klas aplikacji w wyrażeniach ER. Wartości argumentów wywołania klas można definiować dynamicznie w czasie wykonywania: na przykład na podstawie informacji w dokumencie analizy w celu zapewnienia jego poprawności. W tym przewodniku po zadaniu utworzysz wymagane konfiguracje ER dla przykładowej firmy Litware, Inc. Ta procedura została utworzona dla użytkowników z przypisaną rola administratora systemu lub dewelopera raportowania elektronicznego. 

Kroki te można wykonać przy użyciu dowolnego zestawu danych. Należy również pobrać i zapisać lokalnie następujący plik: (https://go.microsoft.com/fwlink/?linkid=862266): SampleIncomingMessage.txt.

Aby wykonać te kroki, należy najpierw wykonać kroki zawarte w procedurze „ER Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.

1. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.
    * Sprawdź, czy dostawca konfiguracji przykładowej firmy Litware, Inc. jest dostępny i oznaczony jako aktywny. Jeśli ten dostawca konfiguracji nie jest widoczny, należy najpierw wykonać procedurę „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.   
    * Chcąc zaprojektować proces przetwarzania przychodzących wyciągów bankowych w celu aktualizacji danych aplikacji. Przychodzące wyciągi bankowe będą plikami w formacie TXT zawierającymi kody IBAN. W ramach przetwarzania zaimportowanych wyciągów bankowych należy sprawdzić poprawność tych kodów IBAN za pomocą dostępnej logiki.   

## <a name="import-a-new-er-model-configuration"></a>Importowanie nowej konfiguracji modelu ER
1. Na liście znajdź i zaznacz odpowiedni rekord.
    * Wybierz kafelek dostawcy Microsoft.  
2. Kliknij Repozytoria.
3. Kliknij przycisk Pokaż filtry.
4. Dodaj pole filtru „Nazwa typu”. W polu Nazwa wprowadź wartość „zasoby”, wybierz operator filtra „zawiera” i kliknij przycisk Zastosuj.
5. Kliknij przycisk Otwórz.
6. W drzewie zaznacz element „Model płatności”.
    * Jeśli przycisk Importuj na skróconej karcie Wersje jest wyłączony, oznacza to, że wersja 1 jednej z konfiguracji ER „Model płatności” została już zaimportowana. Możesz pominąć pozostałe kroki w tym podzadaniu.   
7. Kliknij przycisk Importuj.
8. Kliknij przycisk Tak.
9. Zamknij stronę.
10. Zamknij stronę.

## <a name="add-a-new-er-format-configuration"></a>Dodawanie nowej konfiguracji formatu ER
1. Kliknij opcję Konfiguracje raportowania.
    * Dodaj nowy format ER do analizowania przychodzących wyciągów bankowych w formacie TXT.  
2. W drzewie zaznacz element „Model płatności”.
3. Kliknij przycisk Utwórz konfigurację, aby otworzyć menu okna dialogowego.
4. W polu Nowy wpisz „Format oparty na modelu danych PaymentModel”.
5. W polu Nazwa wpisz „Format importu wyciągu bankowego (przykładowy)”.
    * Format importu wyciągu bankowego (przykładowy)  
6. Wybierz opcję Tak w polu Obsługuje import danych.
7. Kliknij przycisk Utwórz konfigurację.

## <a name="design-the-er-format-configuration---format"></a>Projektowanie konfiguracji formatu ER – format
1. Kliknij przycisk Konstruktor.
    * Zaprojektowany format reprezentuje oczekiwaną strukturę pliku zewnętrznego w formacie TXT.  
2. Kliknij przycisk Dodaj element główny, aby otworzyć menu okna dialogowego.
3. W drzewie zaznacz element „Tekst\Sekwencja”.
4. W polu Nazwa wpisz „Element główny”.
    * Główny  
5. W polu Znaki specjalne wybierz opcję „Nowy wiersz — Windows (CR LF)”.
    * W polu „Znaki specjalne” wybrano opcję „Nowy wiersz – Windows (CR LF)”. Na podstawie tego ustawienia każdy wiersz analizy pliku jest traktowany jako oddzielny rekord.  
6. Kliknij przycisk OK.
7. Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.
8. W drzewie zaznacz element „Tekst\Sekwencja”.
9. W polu Nazwa wpisz „Wiersze”.
    * Wiersze  
10. W polu Liczebność zaznacz opcję „Jeden wiele”.
    * W polu „Liczebność” wybrana została opcja „Jeden wiele”. Na podstawie tego ustawienia podczas analizowania składni pliku oczekiwane jest wyświetlenie co najmniej jednego wiersza.  
11. Kliknij przycisk OK.
12. W drzewie wybierz opcje „Główny\Wiersze”.
13. Kliknij przycisk Dodaj sekwencję.
14. W polu Nazwa wpisz „Pola”.
    * Pola  
15. W polu Liczebność zaznacz opcję „Dokładnie jeden”.
16. Kliknij przycisk OK.
17. W drzewie wybierz kolejno „Główny\Wiersze\Pola”.
18. Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.
19. W drzewie zaznacz element „Tekst\Ciąg”.
20. W polu Nazwa wpisz „IBAN”.
    * Numer IBAN  
21. Kliknij przycisk OK.
    * Skonfigurowano, że każdy wiersz w pliku analizy zawiera tylko kod IBAN.  
22. Kliknij przycisk Zapisz.

## <a name="design-the-er-format-configuration--mapping-to-data-model"></a>Projektowanie konfiguracji formatu ER – mapowanie do modelu danych
1. Kliknij opcję Mapuj format na model.
2. Kliknij przycisk Nowy.
3. W polu Definicja wpisz „BankToCustomerDebitCreditNotificationInitiation”.
    * BankToCustomerDebitCreditNotificationInitiation  
4. Rozstrzygnij zmiany w definicji.
5. W polu Nazwa wpisz „Mapowanie do modelu danych”.
    * Mapowanie do modelu danych  
6. Kliknij przycisk Zapisz.
7. Kliknij przycisk Konstruktor.
8. W drzewie wybierz kolejno „Dynamics 365 for Operations\Klasa”.
9. Kliknij opcję Dodaj element główny.
    * Dodaj nowe źródło danych, aby wywołać istniejącą logikę aplikacji do sprawdzenia poprawności kodów IBAN.  
10. W polu Nazwa wpisz „check_codes”.
    * check_codes  
11. W polu Klasa wpisz „ISO7064”.
    * ISO7064  
12. Kliknij przycisk OK.
13. W drzewie rozwiń węzeł „format”.
14. W drzewie rozwiń węzeł „format\Główny: Sequence(Root)”.
15. W drzewie wybierz kolejno „format\Główny: Sequence(Root)\Wiersze: Sequence 1..* (Wiersze)”.
16. Kliknij opcję Powiąż.
17. W drzewie rozwiń węzeł „format\Główny: Sequence(Root)\Wiersze: Sequence 1..* (Wiersze)”.
18. W drzewie rozwiń węzeł „format\Główny: Sequence(Root)\Wiersze: Sequence 1..* (Wiersze)\Pola: Sequence 1..1 (Pola)”.
19. W drzewie wybierz kolejno„format\Główny: Sequence(Root)\Wiersze: Sequence 1..* (Wiersze)\Pola: Sequence 1..1 (Pola)\IBAN: String(IBAN)”.
20. W drzewie rozwiń węzeł „Płatności = format.Root.Rows”.
21. W drzewie rozwiń węzeł „Płatności = format.Root.Rows\Konto wierzyciela(CreditorAccount)”.
22. W drzewie rozwiń węzeł „Płatności = format.Root.Rows\Konto wierzyciela(CreditorAccount)\Identyfikacja”.
23. W drzewie wybierz kolejno „Płatności = format.Root.Rows\Konto wierzyciela(CreditorAccount)\Identyfikacja\IBAN”.
24. Kliknij opcję Powiąż.
25. Kliknij kartę Weryfikacje.
26. Kliknij przycisk Nowy.
    * Dodaj nową regułę sprawdzania poprawności, która spowoduje wyświetlenie błędu dla każdego wiersza w pliku analizy, który zawiera nieprawidłowy kod IBAN.  
27. Kliknij opcję Edytuj warunek.
28. W drzewie rozwiń węzeł „check_codes”.
29. W drzewie wybierz kolejno „check_codes\verifyMOD1271_36”.
30. Kliknij opcję Dodaj źródło danych.
31. W polu Formuła wpisz „check_codes.verifyMOD1271_36(”.
    * check_codes.verifyMOD1271_36(  
32. W drzewie rozwiń węzeł „format”.
33. W drzewie rozwiń węzeł „format\Główny: Sequence(Root)”.
34. W drzewie rozwiń węzeł „format\Główny: Sequence(Root)\Wiersze: Sequence 1..* (Wiersze)”.
35. W drzewie rozwiń węzeł „format\Główny: Sequence(Root)\Wiersze: Sequence 1..* (Wiersze)\Pola: Sequence 1..1 (Pola)”.
36. W drzewie wybierz kolejno„format\Główny: Sequence(Root)\Wiersze: Sequence 1..* (Wiersze)\Pola: Sequence 1..1 (Pola)\IBAN: String(IBAN)”.
37. Kliknij opcję Dodaj źródło danych.
38. W polu Formuła wpisz „check_codes.verifyMOD1271_36(format.Root.Rows.Fields.IBAN)”.
    * check_codes.verifyMOD1271_36(format.Root.Rows.Fields.IBAN)  
39. Kliknij przycisk Zapisz.
40. Zamknij stronę.
    * Warunek sprawdzania poprawności skonfigurowano do zwracania wartości FAŁSZ dla każdego nieprawidłowego kodu IBAN poprzez wywołanie istniejącej metody „verifyMOD1271_36” klasy aplikacji „ISO7064”. Należy zwrócić uwagę, że wartość kodu IBAN zdefiniowano dynamicznie w czasie wykonywania jako argument metody wywoływania na podstawie zawartości analizy pliku TXT.   
41. Kliknij opcję Edytuj wiadomość.
42. W polu Formuła wpisz „CONCATENATE("Znaleziono nieprawidłowy kod IBAN  ", format.Root.Rows.Fields.IBAN)”.
    * CONCATENATE("Znaleziono nieprawidłowy kod IBAN  ", format.Root.Rows.Fields.IBAN)  
43. Kliknij przycisk Zapisz.
44. Zamknij stronę.
45. Kliknij przycisk Zapisz.
46. Zamknij stronę.

## <a name="run-the-format-mapping"></a>Uruchamianie mapowania
W celach testowych wykonaj mapowanie formatu z użyciem pliku SampleIncomingMessage.txt, który został wcześniej pobrany. Wygenerowane dane wyjściowe zawierają dane, które zostaną zaimportowane z wybranego pliku TXT i wypełnią niestandardowy model danych podczas rzeczywistego importowania.   
1. Kliknij przycisk Uruchom.
    * Kliknij przycisk Przeglądaj i przejdź do pliku SampleIncomingMessage.txt, który został wcześniej pobrany.  
2. Kliknij przycisk OK.
    * Przejrzyj dane wyjściowe w formacie XML, które reprezentują dane zaimportowane z wybranego pliku i przeniesione do modelu danych. Należy zauważyć, że tylko 3 wiersze zaimportowanego pliku TXT zostały przetworzone. Nieprawidłowy kod IBAN w wierszu 4 został pominięty, a w dzienniku informacyjnym pojawił się komunikat o błędzie.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]