---
title: Konfigurowanie szablonu pracy dla zamówień zakupu
description: Ta procedura skupia się na konfigurowaniu prostego szablonu pracy, który ma być używany podczas odkładania przyjętych towarów.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkTemplateTable, SysQueryForm
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d737f9dfd1888602266a87853e54407618ae2781
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1558326"
---
# <a name="set-up-a-work-template-for-purchase-orders"></a>Konfigurowanie szablonu pracy dla zamówień zakupu

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura skupia się na konfigurowaniu prostego szablonu pracy, który ma być używany podczas odkładania przyjętych towarów. Szablony pracy decydują o zbiorze instrukcji przedstawianych pracownikowi magazynu na urządzeniu przenośnym w trakcie przenoszenia towarów w obszarze przyjęcia. Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF. Przed rozpoczęciem tego przewodnika należy utworzyć identyfikator puli pracy. W tym przykładzie jest używany identyfikator puli pracy o nazwie w Przychodzące. Ta procedura jest przeznaczona dla kierownika magazynu.

1. Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Praca > Szablony pracy.
2. W polu Typ zlecenia zaznacz opcję „Zamówienia zakupu”.

## <a name="create-a-work-template-header"></a>Tworzenie nagłówka szablonu pracy
1. Kliknij przycisk Nowy.
2. W polu Numer sekwencyjny wpisz liczbę.
    * Jest to kolejność, w jakiej są sprawdzane szablony pracy. Można zmienić taką sekwencję, jeśli trzeba.  
3. W polu Szablon pracy wpisz wartość.
    * Jest to unikatowy identyfikator tego szablonu.  
4. W polu Opis szablonu pracy wpisz wartość.
    * Opcja Prawidłowe zostanie zaznaczona dopiero wtedy, gdy wprowadzisz wszystkie informacje wymagane przez szablon, a następnie klikniesz przycisk Zapisz.  
    * Zlecenie typu Zamówienie zakupu nie może być przetwarzane automatycznie, więc pozostaw w opcji Przetwarzanie automatyczne wartość Nie.  
5. W polu Identyfikator puli pracy wpisz wartość.
    * Identyfikatory pul pracy umożliwiają organizowanie prac w grupy. Wartość ustawiona w tym polu będzie domyślną wartością dla każdej pracy utworzonej na podstawie tego szablonu.  
6. W polu Priorytet pracy wpisz „1”.
    * To wskazuje istotność pracy, a wartość ustawiona w tym polu będzie domyślna dla każdej pracy utworzonej za pomocą tego szablonu.  
7. Kliknij przycisk Zapisz.
    * Zanim przycisk Edytuj kwerendę zostanie uaktywniony, należy zapisać nagłówek szablonu pracy.  

## <a name="set-up-the-query-for-the-work-template"></a>Konfigurowanie zapytania dla szablonu pracy
1. Kliknij opcję Edytuj kwerendę.
    * Ustawimy ograniczenie, że szablon może być używany tylko w ramach określonego magazynu.  
2. Kliknij przycisk Dodaj.
3. Na liście oznacz wybrany wiersz.
4. W polu Pole wpisz wartość „magazyn”.
5. W polu Kryteria wpisz wartość.
6. Kliknij przycisk OK.
7. Kliknij przycisk Tak.

## <a name="set-work-template-details"></a>Konfigurowanie szczegółów szablonu pracy
1. Kliknij przycisk Nowy.
2. W polu Typ pracy zaznacz opcję „Pobranie”.
3. W polu Identyfikator klasy roboczej wpisz „zakup”.
    * Klasa pracy ustawiona w tym miejscu będzie domyślna we wszystkich wierszach pracy typu Pobranie, które są tworzone za pomocą tego szablonu. Klasy pracy nie można zastąpić z poziomu wierszy zamówienia. Klas pracy są używane do kierowania i/lub ograniczania typów wierszy zlecenia, które pracownik magazynu może przetwarzać na urządzeniu przenośnym.  
4. Kliknij przycisk Nowy.
5. W polu Typ pracy zaznacz opcję „Odłożenie”.
6. W polu Identyfikator klasy roboczej wpisz wartość.
    * Instrukcje pobierania i odkładania są zestawem. Każdy zestaw pobrania/odłożenia musi mieć tę samą klasę pracy. Użyj tej samej klasy pracy, jak podana w instrukcji pobrania.  
7. Kliknij przycisk Zapisz.
    * Należy zwrócić uwagę, że pole wyboru Prawidłowe jest teraz zaznaczone.  

