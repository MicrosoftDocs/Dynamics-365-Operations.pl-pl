---
title: Definiowanie procesu związanego z wynagrodzeniem i obliczanie wyników
description: Procesy wynagrodzeń służą do określania nowych kwot wynagrodzeń i nagród dla pracowników objętych planami wynagrodzeń stałych i o zmiennej wysokości.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMCompProcess, HRMCompProcessLine, HRMCompEvent, HRMCompEventEmpl, HcmCompensationWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 254eb4f83cc734e43920b912e81c7a9230ca82dd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420095"
---
# <a name="define-compensation-process-and-calculate-results"></a>Definiowanie procesu związanego z wynagrodzeniem i obliczanie wyników

Procesy wynagrodzeń służą do określania nowych kwot wynagrodzeń i nagród dla pracowników objętych planami wynagrodzeń stałych i o zmiennej wysokości. Procesy wynagrodzeń można uruchamiać wiele razy w celu przeprowadzenia analizy „co, jeśli” i zweryfikowania, czy wszystkie zmiany i ustawienia są poprawne. Ta procedura spowoduje utworzenie procesu wynagrodzenia, wykonanie go i wyświetlenie wyników. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.


## <a name="create-a-compensation-process"></a>Tworzenie procesu wynagrodzenia
1. Wybierz kolejno opcje Zasoby ludzkie > Wynagrodzenia > Proces > Procesy związane z wynagrodzeniami.
2. Kliknij przycisk Nowy.
3. W polu Proces wpisz wartość.
4. Wypełnij pole Opis.
5. W polu Typ procesu wybierz opcję.
    * Cykl definiuje okres oceniany w celu określenia wynagrodzenia. Ocena bierze pod uwagę, jakie stanowiska zajmowali pracownicy, które oceny wydajności mają zostać uwzględnione, obliczenia wartości procentowej czasu, przez który pracownik był zatrudniony podczas cyklu, itd. Przykładem data rozpoczęcia cyklu może być pierwszy dzień minionego roku obrachunkowego.  
6. W polu Rozpoczęcie cyklu wprowadź datę.
    * Data zakończenia cyklu jest ważna, ponieważ jest to data używana do określania, którzy pracownicy byli aktywnie zatrudnieni i zarejestrowany w co najmniej jednym planem wynagrodzeń.  
7. W polu Zakończenie cyklu wprowadź datę.
    * Datą aktywacji transakcji jest dzień, od którego nowe stawki wynagrodzeń mają zacząć obowiązywać. Wiele firm stosuje kilka miesięcy przerwy między końcem cyklu a czasem, kiedy nowe stawki wynagrodzeń zaczynają obowiązywać. Dodatkowy czas jest używany do przetwarzania i przeglądania nowych wynagrodzeń.  
8. W polu Data aktywacji transakcji wprowadź datę.
    * Data stałego punktu odniesienia jest używana w planach wynagrodzeń o zmiennej wysokości, które określają kwotę nagrody dla pracownika na podstawie jego stawki wynagrodzenia w tym momencie.  
    * Data określenia stałego wynagrodzenia proporcjonalnie do zatrudnienia jest używana w planach stałych wynagrodzeń z regułą zatrudnienia Procent.  Pracownicy, którzy zostali zatrudnieni między rozpoczęciem cyklu a datą określenia stałego wynagrodzenia proporcjonalnie do zatrudnienia, otrzymają 100% obliczonego wzrostu wynagrodzenia zamiast proporcjonalnego procentu.  
9. W polu Data określenia stałego wynagrodzenia proporcjonalnie do zatrudnienia wprowadź datę.
    * Termin przeglądu to dzień, do którego wszystkie wyniki procesów powinny zostać przejrzane, tak aby można było je załadować do rekordu wynagrodzenia pracownika przed datą aktywacji transakcji. To pole służy wyłącznie do celów informacyjnych.  
10. W polu Termin przeglądu wprowadź datę.
11. Kliknij przycisk Zapisz.

## <a name="setup-the-compensation-plans-and-actions-for-a-compensation-process"></a>Konfigurowanie planów i działań wynagrodzenia dla procesu wynagrodzenia
1. Kliknij przycisk Ustawienia.
    * Strona Ustawienia służy do wybrania, które plany mają być przetwarzane w ramach tego procesu wynagrodzenia, a także które akcje mają zostać wykonane dla każdego planu.  
2. W polu Plan wprowadź lub wybierz wartość.
3. Kliknij przycisk Zapisz.
4. Kliknij przycisk Dodaj.
5. W polu Akcja wybierz akcję typu Kapitał własny.
6. Kliknij przycisk Dodaj.
7. W polu Akcja wybierz akcję typu Wartość.
    * Akcje dotyczące wynagrodzeń mogą być „łączone” z sobą przy użyciu pola Użyj poprzedniego wyniku, aby wskazać, czy wybrana akcja powinna używać podstawowego wynagrodzenia pracowników czy też wyniku poprzedniej akcji jako punktu wyjścia dla obliczeń w tej akcji.  
8. W polu Użyj poprzedniego wyniku zaznacz opcję Tak.
9. Kliknij przycisk Dodaj.
10. W polu Akcja wybierz akcję typu Ogólne.
    * Różne typy akcji dotyczących wynagrodzeń włączają różne pola. Dla typu akcji Ogólne można określić procent podwyżki lub kwotę podwyżki.  
11. Zaznacz opcję Wybierz kwotę podwyżki.
12. W polu Kwota podwyżki wpisz liczbę.
13. Kliknij przycisk Dodaj.
14. W polu Akcja wybierz akcję typu Promocja.
    * Typy akcji Promocja i Inna zmiana poziomu umożliwiają użytkownikom wprowadzanie ręcznych korekt wynagrodzeń pracowników. Dla tych typów akcji można włączyć zalecenia, a także inne typy akcji umożliwiających wprowadzenie nowej rekomendowanej wartości wynagrodzenia dla pracownika.  
15. Kliknij przycisk Dodaj.
16. W polu Typ wybierz opcję.
    * Plany wynagrodzeń stałe i o zmiennej wysokości można przetwarzać w tym samym procesie wynagrodzenia.  
17. W polu Plan wprowadź lub wybierz wartość.
    * Zaznacz pole wyboru Włącz wynagrodzenie za wyniki, aby określić, czy stałe i zmienne kwoty wynagrodzeń mają być korygowane zależnie od oceny wydajności pracownika.  
    * Dźwignia finansowa może być zastępowana w planach wynagrodzeń o zmiennej wysokości.  
18. Kliknij przycisk Zapisz.
19. Kliknij przycisk Dodaj.
20. Zamknij stronę.

## <a name="run-the-compensation-process"></a>Wykonywanie procesu wynagrodzenia
1. Kliknij opcję Uruchom proces.
    * Formant Pokaż wyniki przetwarzania umożliwia przeglądanie komunikatów o przetwarzaniu dla całego procesu wynagrodzenia po zakończeniu przetwarzania.  
2. W polu Pokaż wyniki przetwarzania zaznacz opcję Tak.
3. Kliknij przycisk OK.

## <a name="view-the-results"></a>Wyświetlanie wyników
1. Kliknij opcję Wyniki procesu.
2. Kliknij opcję Wyniki pracownika.
3. Na liście znajdź i zaznacz odpowiedni rekord.
4. Rozwiń sekcję Stałe wynagrodzenie.
    * Rozwiń skrócone karty, aby wyświetlić wyniki procesu. Jeśli dla akcji dotyczącej wynagrodzenia zaznaczono opcję Włącz rekomendacje, pola Propozycja płacowa będą włączone dla tej akcji.  
5. Na liście znajdź i zaznacz odpowiedni rekord.
    * Wyniki dla jednego pracownika można wyświetlić przez kliknięcie przycisku Wyświetl wyniki.  
    * Obliczoną kwotę wynagrodzenia można zastąpić, korygując procent lub kwotę podwyżki w polach Propozycja płacowa.  
6. W polu Proponowany procent wpisz liczbę.
7. Na liście znajdź i zaznacz odpowiedni rekord.
8. W polu Proponowany procent wpisz liczbę.
    * Ponownego obliczania można użyć w celu zignorowania wszelkich zmiany wprowadzonych w istniejącym rekordzie oraz wygenerowania nowego wyniku wynagrodzenia dla wybranego pracownika.  
    * Po wprowadzeniu wszystkich zmian dla pracownika należy zmienić stan na Zatwierdzone.  
9. Kliknij przycisk Zmień stan.
10. Kliknij przycisk Zatwierdzone.
    * Po zatwierdzeniu rekordu można go załadować do oficjalnego rekordu wynagrodzenia pracownika. Nowe wynagrodzenie będzie obowiązywać od dnia transakcji ustawionego w procesie wynagrodzenia.  



[!INCLUDE[footer-include](../includes/footer-banner.md)]