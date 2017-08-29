--- 
title: "Definiowanie zależności konfiguracji od innych składników na potrzeby raportowania elektronicznego (ER)"
description: "W celu wykonania tych kroków należy najpierw wykonać kroki w przewodniku po zadaniu ER Zarządzanie konfiguracjami mapowania modelu oraz mieć dostęp do usługi Microsoft Dynamics Lifecycle Services (LCS)."
author: NickSelin
manager: AnnBe
ms.date: 06/23/2017
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
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: be601efd857a0d57210680adcb0b0a1f17ca2f27
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="define-the-dependency-of-configurations-from-othcomponents-for-electronic-reporting-er"></a>Definiowanie zależności konfiguracji od innych składników na potrzeby raportowania elektronicznego (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

W celu wykonania tych kroków należy najpierw wykonać kroki w przewodniku po zadaniu ER Zarządzanie konfiguracjami mapowania modelu oraz mieć dostęp do usługi Microsoft Dynamics Lifecycle Services (LCS).

Ta procedura przedstawia sposób projektowania konfiguracji raportowania elektronicznego (ER) i określania jej zależności od innych składników oprogramowania, tak aby mieć pewność, że konfiguracja jest prawidłowo pobierana dla określonej wersji programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition. W tym przykładzie utworzysz wymagane konfiguracje ER dla przykładowej firmy Litware, Inc. 

Ta procedura jest przeznaczona dla użytkowników z przypisaną rola Administrator systemu lub Deweloper raportowania elektronicznego. Te kroki można wykonać w dowolnej firmie, ponieważ konfiguracje ER są współużytkowane przez wszystkie firmy. 

1. Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.
    * Upewnij się, że w drzewie konfiguracji znajduje się konfiguracja „Przykładowy model danych” i jej elementy podrzędne. W przeciwnym razie wykonaj kroki opisane w przewodniku po zadaniu ER Zarządzanie konfiguracjami mapowania modelu, a następnie ponownie uruchom ten przewodnik.   

## <a name="define-the-dependency-of-er-configurations-from-other-components"></a>Definiowanie zależności konfiguracji ER od innych składników
1. W drzewie rozwiń węzeł „Przykładowy model danych”.
2. W drzewie zaznacz element „Przykładowy model danych\Przykładowe mapowanie”.
    * Wybraliśmy wersję roboczą konfiguracji mapowania modelu „Przykładowe mapowanie”. Teraz zdefiniujemy jej zależność od innych składników oprogramowania. Ten krok jest traktowany jako warunek wstępny kontrolowania pobierania tej wersji konfiguracji z repozytorium ER i dalszego używania tej wersji.   
3. Rozwiń sekcję Wymagania wstępne.
    * Należy zauważyć, że grupa wymagań wstępnych Implementacje została dodana automatycznie na tym etapie. Grupa zawiera wstępnie wymagany składnik, który odwołuje się do konfiguracji modelu danych i ma włączoną flagę Implementacja. Flaga wskazuje, że konfiguracja mapowania „Przykładowe mapowanie” jest uważana za implementację modelu danych „Przykładowy model danych”. Ten składnik zmusi moduł ER do pobierania konfiguracji mapowania Przykładowe mapowanie z repozytorium ER podczas każdego pobierania konfiguracji modelu „Przykładowy model danych”.   
4. Kliknij przycisk Edytuj.
    * Można określić pojedynczą zależność bieżącej wersji konfiguracji od składnika oprogramowania, używając definicji typu składnika oraz alternatywnie wersji składnika lub zakresu wersji składnika.  
    * Żądane zależności mogą być grupowane razem. Jeśli zostanie wybrany typ grupowania „Wszystkie”, warunek zależność tej grupy jest uważany za spełniony, jeżeli jest spełniony każdy warunek zależność z tej grupy i grupy podrzędnej. Jeśli zostanie wybrany typ grupowania „Jeden”, warunek zależność tej grupy jest uważany za spełniony, jeżeli jest spełniony co najmniej jeden warunek zależność z tej grupy.   
5. Kliknij przycisk Nowy.
6. Wybierz wstępnie wymagany składnik Produktu.
7. Zaznacz pozycję Microsoft Dynamics 365 for Operations (1611).
8. W polu Wersja wpisz wartość „(7.1.1541.3036,8)”.
    * (7.1.1541.3036,8)  
    * Wprowadzane zależności będą oceniane podczas pobierania tej konfiguracji z repozytorium modułu Raportowanie elektroniczne. Ta wersja konfiguracji będzie pobierana z repozytorium ER, gdy wersja 1 konfiguracji „Przykładowy model danych” już znajduje się na miejscu albo zostanie pobrana z wyprzedzeniem. Jeśli jest pobierana z wyprzedzeniem, musi zostać wykonana w programie Finance and Operations o wersji 7.1.1541.3036 lub nowszej, ale wersji głównej nie nowszej niż 8.   
9. Kliknij przycisk Zapisz.
10. Zamknij stronę.
11. Kliknij przycisk Zmień stan.
12. Kliknij przycisk Wykonaj.
13. Kliknij przycisk OK.
14. W drzewie zaznacz element „Przykładowy model danych\Przykładowe mapowanie (alternatywne)”.
15. Kliknij przycisk Edytuj.
16. Kliknij przycisk Nowy.
17. Wybierz wstępnie wymagany składnik Produktu.
18. Zaznacz pozycję Microsoft Dynamics AX 7.0 RTW.
19. W polu Wersja wpisz wartość „(7.0.1265.3015,7.1)”.
    * [7.0.1265.3015,7.1)  
    * Zależności będą oceniane podczas pobierania konfiguracji z repozytorium modułu Raportowanie elektroniczne. Ta wersja konfiguracji będzie pobierana z repozytorium ER, gdy wersja 1 konfiguracji „Przykładowy model danych” już znajduje się na miejscu albo zostanie pobrana z wyprzedzeniem. Jeśli jest pobierana z wyprzedzeniem, musi zostać wykonana w programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition o wersji 7.0.1265.3015 lub nowszej, ale wersji pomocniczej nie nowszej niż 1.   
20. Kliknij przycisk Zapisz.
21. Zamknij stronę.
22. Kliknij przycisk Zmień stan.
23. Kliknij przycisk Wykonaj.
24. Kliknij przycisk OK.

## <a name="configure-the-er-repository"></a>Konfigurowanie repozytorium raportowania elektronicznego
1. Zamknij stronę.
2. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.
    * Otwórz listę repozytoriów ER bieżącego dostawcy konfiguracji ER, czyli firmy „Litware, Inc.”.  
3. Na liście oznacz wybrany wiersz.
4. Kliknij Repozytoria.
5. Kliknij przycisk Pokaż filtry.
6. Wprowadź wartość filtru „LCS” w polu „Nazwa typu”, używając operatora filtru „zawiera”.
    * Jeśli repozytorium usługi LCS jest już zarejestrowane dla bieżącego dostawcy ER, możesz pominąć pozostałe kroki w tym zadaniu podrzędnym. Jeśli repozytorium usługi LCS nie jest jeszcze zarejestrowane, wykonaj pozostałe kroki.   
7. Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.
8. W polu Typ repozytorium konfiguracji wpisz „LCS”.
9. Kliknij opcję Utwórz repozytorium.
10. W polu Projekt wprowadź lub wybierz wartość.
    * Wybierz żądany projekt usługi LCS z wyników wyszukiwania w polu „Projekt”.  
11. Kliknij przycisk OK.
12. Zamknij stronę.

## <a name="upload-configurations-to-lcs"></a>Przekazywanie konfiguracji do usługi LCS
1. Kliknij opcję Konfiguracje raportowania.
2. W drzewie zaznacz element „Przykładowy model danych”.
3. Zaznacz ukończoną wersję tej konfiguracji.
4. Kliknij przycisk Zmień stan.
5. Kliknij przycisk Udostępnij.
6. Kliknij przycisk OK.
    * Wersja 1 tej konfiguracji modelu została przekazana do usługi LCS przy użyciu projektu LCS dla repozytorium modułu ER, które zostało uprzednio skonfigurowane.   
7. W drzewie rozwiń węzeł „Przykładowy model danych”.
8. W drzewie zaznacz element „Przykładowy model danych\Przykładowe mapowanie”.
9. Zaznacz ukończoną wersję tej konfiguracji.
10. Kliknij przycisk Zmień stan.
11. Kliknij przycisk Udostępnij.
12. Kliknij przycisk OK.
    * Wersja 1.1 tej konfiguracji mapowania modelu została przekazana do usługi LCS przy użyciu projektu LCS dla repozytorium modułu ER, które zostało uprzednio skonfigurowane.   
13. W drzewie zaznacz element „Przykładowy model danych\Przykładowe mapowanie (alternatywne)”.
14. Zaznacz ukończoną wersję tej konfiguracji.
15. Kliknij przycisk Zmień stan.
16. Kliknij przycisk Udostępnij.
17. Kliknij przycisk OK.
    * Wersja 1.1 tej konfiguracji mapowania modelu została przekazana do usługi LCS przy użyciu projektu LCS dla repozytorium modułu ER, które zostało uprzednio skonfigurowane.   

## <a name="evaluate-er-configuration-dependencies"></a>Ocena zależności konfiguracji raportowania elektronicznego
    * Usuniemy utworzone konfiguracje z systemu i pobierzemy je ponownie z repozytorium usługi LCS.  
1. W drzewie zaznacz element „Przykładowy model danych\Przykładowe mapowanie”.
2. Kliknij przycisk Usuń.
3. Kliknij przycisk Tak.
4. W drzewie zaznacz element „Przykładowy model danych\Przykładowe mapowanie (alternatywne)”.
5. Kliknij przycisk Usuń.
6. Kliknij przycisk Tak.
7. W drzewie zaznacz element „Przykładowy model danych\Przykładowy format”.
8. Kliknij przycisk Usuń.
9. Kliknij przycisk Tak.
10. W drzewie zaznacz element „Przykładowy model danych”.
11. Kliknij przycisk Usuń.
12. Kliknij przycisk Tak.
13. Zamknij stronę.
    * Otwórz listę repozytoriów ER bieżącego dostawcy konfiguracji ER, czyli firmy „Litware, Inc.”.  
14. Kliknij Repozytoria.
15. Kliknij przycisk Pokaż filtry.
16. Wprowadź wartość filtru „LCS” w polu „Nazwa typu”, używając operatora filtru „zawiera”.
17. Kliknij przycisk Otwórz.
18. W drzewie zaznacz element „Przykładowy model danych”.
    * Należy zauważyć, że można wyświetlić ocenę, czy zostały spełnione warunki wstępne dla każdej wersji konfiguracje ER w bieżącym repozytorium. Aby wyświetlić tę ocenę, kliknij opcję Sprawdź wymagania wstępne.   
19. Kliknij opcję Sprawdź wymagania wstępne.
20. Kliknij przycisk Importuj.
21. Kliknij przycisk Tak.
22. Zamknij stronę.
23. Zamknij stronę.
24. Zamknij stronę.
25. Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.
26. W drzewie rozwiń węzeł „Przykładowy model danych”.
    * Należy zauważyć, że konfiguracja mapowania modelu „Przykładowe mapowanie” została pobrana wraz z wybraną konfiguracją modelu danych. Oba pliki są pobierane razem, ponieważ model „Przykładowe mapowanie” został zdefiniowany jako implementujący wybrany model danych i ma zastosowanie do aplikacji Finance and Operations. Konfiguracja „Przykładowe mapowanie (alternatywne)” nie została pobrana, ponieważ nie jest spełniony warunek dla wymaganej wersji aplikacji.   
    * Gdy się zalogujesz do programu Dynamics 365 for Finance and Operations Enterprise Edition, zarejestrujesz tego samego dostawcę, przejdziesz do tego samego projektu usługi LCS i pobierzesz tę samą konfigurację modelu danych, zostanie pobrana konfiguracja „Przykładowe mapowanie (alternatywne)”, natomiast konfiguracja „Przykładowe mapowanie” zostanie pominięta.  


