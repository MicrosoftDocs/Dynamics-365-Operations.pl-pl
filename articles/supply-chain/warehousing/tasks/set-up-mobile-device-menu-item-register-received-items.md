---
title: Konfigurowanie elementu menu urządzenia przenośnego do rejestrowania towarów przyjętych
description: Ten temat przedstawia konfigurowanie elementu menu urządzenia przenośnego.
author: ShylaThompson
ms.date: 08/16/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItem, WHSRFMenu, WHSRFDefaultData
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d9dc74d51dae4af21679ed71b68286ca29ff6201977242490fb749364a223f64
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6764675"
---
# <a name="set-up-a-mobile-device-menu-item-to-register-received-items"></a>Konfigurowanie elementu menu urządzenia przenośnego do rejestrowania towarów przyjętych

[!include [banner](../../includes/banner.md)]

Ten temat przedstawia konfigurowanie elementu menu urządzenia przenośnego. Ten element menu służy do rejestrowania przyjęć towarów zamówionych za pośrednictwem zamówień zakupu. 

Zadania z przewodnika można wykonać przy użyciu danych firmy demonstracyjnej USMF. Ta procedura jest przeznaczona dla kierownika magazynu.


## <a name="create-a-mobile-device-menu-item"></a>Tworzenie elementu menu urządzenia przenośnego
1. W okienku nawigacji wybierz kolejno opcje **Moduły > Zarządzanie magazynem > Ustawienia > Urządzenie przenośne > Elementy menu urządzenia przenośnego**.
2. Wybierz pozycję **Nowy**.
3. W polu **Nazwa elementu menu** wpisz wartość. Jest to unikatowy identyfikator tego elementu menu urządzenia przenośnego. Na przykład można wpisać `My PO registration`.  
4. W polu **Tytuł** wpisz wartość. Jest to tytuł, który będzie wyświetlany użytkownikowi na urządzeniu przenośnym. Na przykład można wpisać `PO registration`.  
5. W polu **Tryb** wybierz opcję **Praca**. Rejestracja dostępnych ilości otrzymanych dla wiersza zamówienia zakupu utworzy pracę dotyczącą przeniesienia towarów z obszaru przyjęcia do magazynu. Praca jest tworzona dopiero po zarejestrowaniu towarów. W związku z tym w opcji **Użyj istniejącej pracy** pozostaw wartość **Nie**.
6. W polu **Proces tworzenia pracy** w sekcji **Ogólne** wybierz opcję **Przyjęcie pozycji z zamówienia zakupu**.
    - Wiersz zamówienia zakupu musi być unikatowo identyfikowany, zanim dostępne zapasy będzie można zarejestrować w magazynie. W tym scenariuszu urządzenie przenośne zarejestruje numer zamówienia zakupu i numer towaru, co pozwoli systemowi na identyfikowanie wiersza zamówienia zakupu. Zostanie utworzona praca odkładania i może ona zostać podjęta przez innego pracownika. Wybrana metoda tworzenia pracy określa, które pola będą dostępne na skróconej karcie **Ogólne**.  
    - Jeśli zostanie wybrana opcja **Użyj danych domyślnych**, jest włączony przycisk **Dane domyślne**. W wyświetlonym oknie można wybrać pola zawierające dane, które są najbardziej potrzebne pracownikowi w codziennej pracy, dlatego te wartości są wyświetlane na urządzeniu przenośnym.  
    - Parametr **Grupowanie numerów identyfikacyjnych** działa w połączeniu z grupą sekwencji jednostek przypisaną do towaru, który jest przyjmowany. Można określić, czy przyjęcia mniej niż jednej lub więcej niż jednej palety powinny być grupowane w ramach jednego numeru identyfikacyjnego, czy podzielone na osobne numery identyfikacyjne dla każdej jednostki.  
    - Jeśli zostanie wybrana opcja **Generuj numer identyfikacyjny**, będzie generowany unikatowy numer identyfikacyjny na podstawie wybranej numeracji.  
    - Można wybrać szablon, który będzie używany podczas tworzenia pracy. Na przykład jeśli rejestrujesz towar dla zamówienia zakupu, praca odłożenia zostanie wygenerowana na podstawie szablonu pracy. Jeśli w tym polu nie wybierzesz szablonu pracy, system przypisze szablon na podstawie kryteriów zapytania skojarzonych z szablonami.  
    - Jeśli na urządzeniu przenośnym są wyświetlane kody dyspozycji, pracownicy mogą oceniać stan lub jakości towarów oraz wybrać odpowiedni kod. Reguły kodu dyspozycji określają, czy towary będą dostępne dla innych procesów magazynowych. Reguły określają również, które dyrektywy lokalizacji są używane dla tworzonej pracy.   
    - Jeśli wybierzesz opcję **Kody dyspozycji partii**, pracownicy mogą oceniać stan lub jakości partii oraz wybrać odpowiedni kod dyspozycji. Reguły ustawione w kodzie dyspozycji partii określają, czy partia będzie dostępna dla innych procesów magazynu.  
    - Jeśli zostanie wybrana opcja **Drukuj etykiety**, etykieta z numerem identyfikacyjnym będzie drukowana automatycznie podczas przyjmowania towarów.  
7. Wybierz opcję **Zapisz**.
8. Zamknij stronę.

## <a name="add-the-menu-item-to-a-mobile-device-menu"></a>Dodawanie element menu do menu urządzenia przenośnego
1. W okienku nawigacji wybierz kolejno opcje **Moduły > Zarządzanie magazynem > Ustawienia > Urządzenie przenośne > Menu urządzeń przenośnych**.
2. Użyj **szybkiego filtru**, aby filtrować pole **Nazwa** za pomocą wartości `inbound`.
3. Wybierz opcję **Edycja**.
4. W drzewie Dostępne menu i elementy zaznacz utworzony wcześniej element menu.
5. Wybierz strzałkę wskazującą w prawo.
6. Wybierz opcję **Zapisz**.
7. Zamknij stronę.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]