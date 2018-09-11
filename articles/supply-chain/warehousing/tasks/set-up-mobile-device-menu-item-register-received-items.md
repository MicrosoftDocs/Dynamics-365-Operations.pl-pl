--- 
title: "Konfigurowanie elementu menu urządzenia przenośnego do rejestrowania towarów przyjętych"
description: "To zadanie jest zorientowane na konfigurowanie elementu menu urządzenia przenośnego."
author: ShylaThompson
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSRFMenuItem, WHSRFMenu
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 7b5d757361c1163bbd0300abd3da4e0a2dd6b0e0
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-a-mobile-device-menu-item-to-register-received-items"></a>Konfigurowanie elementu menu urządzenia przenośnego do rejestrowania towarów przyjętych

[!include [task guide banner](../../includes/task-guide-banner.md)]

To zadanie jest zorientowane na konfigurowanie elementu menu urządzenia przenośnego. Ten element menu służy do rejestrowania przyjęć towarów zamówionych za pośrednictwem zamówień zakupu. 

Zadania z przewodnika można wykonać przy użyciu danych firmy demonstracyjnej USMF. Ta procedura jest przeznaczona dla kierownika magazynu.


## <a name="create-a-mobile-device-menu-item"></a>Tworzenie elementu menu urządzenia przenośnego
1. Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Urządzenie przenośne > Elementy menu urządzenia przenośnego.
2. Kliknij przycisk Nowy.
3. W polu Nazwa elementu menu wpisz wartość.
    * Jest to unikatowy identyfikator tego elementu menu urządzenia przenośnego. Na przykład można wpisać „Moja rejestracja zamówienia zakupu”.  
4. W polu Tytuł wpisz wartość.
    * Jest to tytuł, który będzie wyświetlany użytkownikowi na urządzeniu przenośnym. Na przykład można wpisać „Rejestracja zamówienia zakupu”.  
5. W polu Tryb wybierz opcję „Praca”.
    * Rejestracja dostępnych ilości otrzymanych dla wiersza zamówienia zakupu utworzy pracę dotyczącą przeniesienia towarów z obszaru przyjęcia do magazynu. Praca jest tworzona dopiero po zarejestrowaniu towarów.  W związku z tym w opcji Użyj istniejącej pracy pozostaw wartość Nie.  
6. Rozwiń lub zwiń sekcję Ogólne.
7. W polu Proces tworzenia pracy wybierz opcję „Przyjęcie pozycji z zamówienia zakupu”.
    * Wiersz zamówienia zakupu musi być unikatowo identyfikowany, zanim dostępne zapasy będzie można zarejestrować w magazynie. W tym scenariuszu urządzenie przenośne zarejestruje numer zamówienia zakupu i numer towaru, co pozwoli systemowi na identyfikowanie wiersza zamówienia zakupu. Zostanie utworzona praca odkładania i może ona zostać podjęta przez innego pracownika.    Wybrana metoda tworzenia pracy określa, które pola będą dostępne na skróconej karcie Ogólne.  
    * Jeśli zostanie wybrana opcja Użyj danych domyślnych, jest włączony przycisk Dane domyślne. W wyświetlonym oknie można wybrać pola zawierające dane, które są najbardziej potrzebne pracownikowi w codziennej pracy, dlatego te wartości są wyświetlane na urządzeniu przenośnym.  
    * Parametr Grupowanie numerów identyfikacyjnych działa w połączeniu z grupą sekwencji jednostek przypisaną do towaru, który jest przyjmowany. Można określić, czy przyjęcia mniej niż jednej lub więcej niż jednej palety powinny być grupowane w ramach jednego numeru identyfikacyjnego, czy podzielone na osobne numery identyfikacyjne dla każdej jednostki.  
    * Jeśli zostanie wybrana opcja Generuj numer identyfikacyjny, będzie generowany unikatowy numer identyfikacyjny na podstawie wybranej sekwencji numeracji.   
    * Można wybrać szablon, który będzie używany podczas tworzenia pracy. Na przykład jeśli rejestrujesz towar dla zamówienia zakupu, praca odłożenia zostanie wygenerowana na podstawie szablonu pracy. Jeśli w tym polu nie wybierzesz szablonu pracy, system przypisze szablon na podstawie kryteriów zapytania skojarzonych z szablonami.  
    * Jeśli na urządzeniu przenośnym są wyświetlane kody dyspozycji, pracownicy mogą oceniać stan lub jakości towarów oraz wybrać odpowiedni kod. Reguły kodu dyspozycji określają, czy towary będą dostępne dla innych procesów magazynowych. Reguły określają również, które dyrektywy lokalizacji są używane dla tworzonej pracy.   
    * Jeśli wybierzesz opcję Kody dyspozycji partii, pracownicy mogą oceniać stan lub jakości partii oraz wybrać odpowiedni kod dyspozycji.  Reguły ustawione w kodzie dyspozycji partii określają, czy partia będzie dostępna dla innych procesów magazynu.  
    * Jeśli zostanie wybrana opcja Drukuj etykiety, etykieta z numerem identyfikacyjnym będzie drukowana automatycznie podczas przyjmowania towarów.  
8. Kliknij przycisk Zapisz.
9. Zamknij stronę.

## <a name="add-the-menu-item-to-a-mobile-device-menu"></a>Dodawanie element menu do menu urządzenia przenośnego
1. Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Urządzenie przenośne > Menu urządzeń przenośnych.
2. Użyj szybkiego filtru, aby wyfiltrować pole Nazwa według wartości „przychodzące”.
3. Kliknij przycisk Edytuj.
4. W drzewie w węźle „Dostępne menu i elementy menu” zaznacz utworzony wcześniej element menu.
    * Wybierz utworzony wcześniej element menu.  
5. Kliknij strzałkę wskazującą w prawo.
6. Kliknij przycisk Zapisz.
7. Zamknij stronę.


