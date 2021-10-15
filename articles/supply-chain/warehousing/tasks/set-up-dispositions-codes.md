---
title: Ustawianie kodów dyspozycji
description: Ta procedura skupia się na skonfigurowaniu kod dyspozycji, którego można używać na urządzeniu przenośnym do obsługi procesu odbioru w zamówieniu zwrotu.
author: Mirzaab
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSDispositionTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fb83108c934e864da0df39ec4ee36a0bc7ba7588
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7574072"
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