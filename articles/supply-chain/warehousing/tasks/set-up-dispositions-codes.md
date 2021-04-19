---
title: Ustawianie kodów dyspozycji
description: Ta procedura skupia się na skonfigurowaniu kod dyspozycji, którego można używać na urządzeniu przenośnym do obsługi procesu odbioru w zamówieniu zwrotu.
author: ShylaThompson
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSDispositionTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 16458f709788e538d036cc4d3b3239f4ffa3c42e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830937"
---
# <a name="set-up-dispositions-codes"></a>Ustawianie kodów dyspozycji

[!include [banner](../../includes/banner.md)]

Ta procedura skupia się na skonfigurowaniu kod dyspozycji, którego można używać na urządzeniu przenośnym do obsługi procesu odbioru w zamówieniu zwrotu. Kody dyspozycji to zbiór reguł, których można używać podczas przyjęcia towarów. Na przykład gdy użytkownik pracy używa urządzenia przenośnego do przyjęcia towarów, które zostały uszkodzone, musi zeskanować kod dyspozycji tych towarów. Z zeskanowanego kodu dyspozycji można określić stan zapasów przyjętych towarów, szablon pracy i dyrektywę lokalizacji. Dla procesów przyjęcia w zamówieniu zakupu oraz zgłaszania wyrobów gotowych w zleceniu produkcyjnym używanie kodu dyspozycji jest opcjonalne. W procesie przyjęcia zwrotu w zamówieniu sprzedaży jeśli towary są rejestrowane za pomocą urządzenia przenośnego, użycie kodu dyspozycji jest obowiązkowe.  Przewodnik utworzono przy użyciu danych firmy demonstracyjnej USMF. Ta procedura jest przeznaczona dla kierownika magazynu. 

1. Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Urządzenie przenośne > Kody dyspozycji.
2. Kliknij przycisk Nowy.
    * Utwórz nowy kod dyspozycji do używania w zwrotach od odbiorców.  
3. W polu Kod dyspozycji wpisz wartość.
4. W polu Stan zapasów wybierz stan zapasów tam, gdzie występuje blokowanie zapasów.
    * Jeśli używasz firmy USMF, zaznacz opcję „Blokowanie”. Do kodu dyspozycji można dodać stan zapasów, aby zastąpić domyślny stan w wierszach zamówienia.  
5. W polu Szablon pracy wpisz wartość.
    * Opcjonalnie: Wybierz kod szablonu pracy skojarzony z zamówieniem zwrotu. Jeśli wartość nie zostanie podana, szablon pracy będzie interpretowany przy użyciu standardowych reguł skonfigurowanych w systemie. Wybranie szablonu pracy ograniczy procesy, z którymi można używać tego kodu dyspozycji. Na przykład jeśli kod dyspozycji ma szablon pracy ze zleceniem typu Zamówienie zakupu, nie można go używać do rejestrowania towarów zwracanych przez odbiorców.  
6. W polu Kod dyspozycji zwrotu wpisz wartość.
    * Kod dyspozycji zwrotu określa pozostałą część procesu zamówienia zwrotu dla zarejestrowanych towarów. W tym przykładzie odbiorca powinien otrzymać fakturę korygującą. Dodaj kod dyspozycji zwrotu zawierający akcję Uznanie.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]