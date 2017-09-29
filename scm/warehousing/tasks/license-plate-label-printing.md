--- 
title: "Włączanie drukowania etykiet numeru identyfikacyjnego"
description: "Ta procedura umożliwia automatyczne drukowanie etykiety z numerem seryjnym kontenera wysyłkowego (SSCC) po pobraniu ostatniego towaru z magazynu w procesie pracy pobierania dla sprzedaży."
author: perlynne
manager: AnnBe
ms.date: 11/03/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: c4ca3cd02a43692cfa9510847b460a318855fd24
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="enable-license-plate-label-printing"></a>Włączanie drukowania etykiet numeru identyfikacyjnego

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ta procedura umożliwia automatyczne drukowanie etykiety z numerem seryjnym kontenera wysyłkowego (SSCC) po pobraniu ostatniego towaru z magazynu w procesie pracy pobierania dla sprzedaży. Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF. Jeśli wykonujesz procedurę przy użyciu własnych danych, trzeba mieć zdefiniowaną sekwencję numeracji dla numerów identyfikacyjnych. Przed rozpoczęciem tego zadania należy skonfigurować drukarkę etykiet. Wybierz kolejno opcje Administrowanie organizacją > Ustawienia > Drukarki sieciowe. W okienku akcji kliknij przycisk Opcje, a następnie kliknij przycisk Pobierz instalatora agenta rozsyłania dokumentów. Uruchom instalatora i przed rozpoczęciem procedury upewnij się, że działająca drukarka sieciowa ma ustawiony status Aktywna.


## <a name="set-up-the-gs1-company-prefix"></a>Konfigurowanie prefiksu GS1 firmy
1. Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Parametry zarządzania magazynem.
2. W polu Prefiks GS1 firmy wprowadź 7-cyfrowy numer GS1 firmy.
3. Kliknij przycisk Zapisz.
4. Zamknij stronę.

## <a name="setup-the-sscc-license-plate-number-sequence"></a>Konfigurowanie sekwencji numeracji w numerze identyfikacyjnym SSCC
1. Wybierz kolejno opcje Administrowanie organizacją > Sekwencje numerów > Sekwencje numerów.
2. W polu Obszar wybierz opcję.
3. W polu Odwołanie wybierz opcję.
4. W polu Firma wpisz wartość.
5. Na liście oznacz wybrany wiersz.
6. Na liście kliknij łącze w wybranym wierszu.
7. Rozwiń sekcję Segmenty.
8. Kliknij przycisk Edytuj.
9. W tabeli segmentów zaznacz pierwszy wiersz
10. Kliknij przycisk Usuń.
11. Kliknij przycisk Usuń.
12. Kliknij przycisk Zapisz.
13. Zamknij stronę.

## <a name="create-the-document-route-layout"></a>Tworzenie układu trasy dokumentów
1. Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Wybór trasy dokumentów > Układy wyboru trasy dokumentów.
    * Włącz układ kodu SSCC.  
2. Kliknij przycisk Nowy.
3. W polu Identyfikator układu wpisz wartość.
4. Wypełnij pole Opis.
5. Na liście znajdź i zaznacz odpowiedni rekord.
6. Kliknij przycisk Wstaw na końcu tekstu.
7. Kliknij przycisk Zapisz.
8. Zamknij stronę.

## <a name="set-up-the-document-routing"></a>Konfigurowanie opcji wyboru trasy dokumentów
1. Wybierz kolejno opcje Zarządzanie magazynem > ustawienia > Wybór trasy dokumentów > Wybór trasy dokumentów.
2. W polu Typ zlecenia wybierz opcję.
3. Kliknij przycisk Nowy.
4. W polu Magazyn wpisz wartość.
5. W polu Nazwa wpisz wartość.
6. Kliknij przycisk Nowy.
7. W polu Identyfikator układu wprowadź lub wybierz wartość.
8. W polu Nazwa wpisz nazwę drukarki, której chcesz używać.
9. Kliknij przycisk Zapisz.
10. Zamknij stronę.

## <a name="create-mobile-device-menu"></a>Utwórz menu urządzenia przenośnego
1. Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Urządzenie przenośne > Elementy menu urządzenia przenośnego.
2. Kliknij przycisk Nowy.
3. W polu Nazwa elementu menu wpisz wartość.
4. W polu Tytuł wpisz wartość.
5. W polu Tryb wybierz opcję.
6. W polu Użyj istniejącej pracy zaznacz opcję Tak.
7. W polu Generuj numer identyfikacyjny zaznacz opcję Tak.
8. Rozwiń sekcję Klasy robocze.
9. Kliknij przycisk Nowy.
10. W polu Identyfikator klasy roboczej wpisz wartość.
11. Kliknij przycisk Zapisz.
12. Zamknij stronę.
13. Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Urządzenie przenośne > Menu urządzeń przenośnych.
14. Na liście znajdź i zaznacz odpowiedni rekord.
15. W drzewie zaznacz utworzony wcześniej element menu.
16. Kliknij przycisk Edytuj.
17. Kliknij strzałkę, aby dodać element menu do menu.
18. Kliknij przycisk Zapisz.
19. Zamknij stronę.

## <a name="update-a-work-template"></a>Aktualizacja szablonu pracy
1. Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Praca > Szablony pracy.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. Kliknij przycisk Edytuj.
4. Kliknij przycisk Nowy.
5. Na liście oznacz wybrany wiersz.
6. W polu Typ pracy zaznacz opcję „Drukowanie”.
7. W polu Identyfikator klasy roboczej wprowadź lub wybierz wartość.
8. Na liście kliknij łącze w wybranym wierszu.
9. Kliknij przycisk W górę.
10. Kliknij przycisk Zapisz.
11. Zamknij stronę.

