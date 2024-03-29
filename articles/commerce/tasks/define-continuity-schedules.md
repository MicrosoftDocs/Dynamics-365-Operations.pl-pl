---
title: Definiowanie harmonogramów sprzedaży ciągłej
description: Ten artykuł prowadzi przez proces konfigurowania programu sprzedaży ciągłej (znanego również jako zamówienia cykliczne).
author: josaw1
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: MCRContinuitySchedule, EcoResProductDetailsExtended
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: faa55c844c8ee8742fbb0868b55a520cec6686aa
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885091"
---
# <a name="define-continuity-schedules"></a>Definiowanie harmonogramów sprzedaży ciągłej

[!include [banner](../includes/banner.md)]

Ten artykuł prowadzi przez proces konfigurowania programu sprzedaży ciągłej (znanego również jako zamówienia cykliczne). W artykule wykorzystano dane demonstracyjne firmy USRT.


## <a name="create-continuity-program"></a>Tworzenie programu sprzedaży ciągłej
1. Wybierz kolejno opcje Retail i Commerce > Ciągłość > Programy sprzedaży ciągłej.
2. Kliknij przycisk Nowy.
3. W polu Identyfikator harmonogramu wpisz identyfikator harmonogramu programu ciągłości sprzedaży.
4. W polu Początek zamówienia wybierz opcję „Pierwsze zdarzenie”.
    * Jeśli odbiorca złoży nowe zamówienie w programie sprzedaży ciągłej, istnieją dwie opcje wysłania produktu: 1. Pierwsze zdarzenie: zostanie wysłany pierwszy produkt w programie sprzedaży ciągłej.  2. Bieżące zdarzenie: zostanie wysłany bieżący produkt. Na przykład w trzecim miesiącu trwania programu odbiorca otrzyma trzeci produkt przewidziany w programie.  
5. Wybierz opcję „Tak” w monicie o datę początkową zamówienia.
6. Kliknij przycisk Dodaj wiersz.
7. W polu Numer pozycji wpisz numer towaru dla pierwszego produktu („0013”).
8. Wpisz „CP”.
9. Wprowadź datę, kiedy pierwszy produkt będzie dostępny do zamówienia.
10. Kliknij przycisk Dodaj wiersz.
11. W polu Numer towaru wpisz wartość „0014”.
12. W polu Kod zakresu dat wyczyścić wartość, tak aby pole było puste.
    * Do wykonania tej procedury należy wyczyścić przedział dat. Ustawisz datę jako przyrostową od daty początkowej pierwszego towaru.  
13. W tym miejscu wprowadzisz przedział czasu, w jakim produkty są wysłane. Wpisz „30”.
    * Dla programu miesięcznego wprowadzisz interwał 30 dni.  
14. Kliknij przycisk Dodaj wiersz.
15. W polu Numer towaru wpisz wartość „0015”.
16. Wpisz „Koniec”.
17. Kliknij przycisk Zapisz.

## <a name="assign-to-continuity-item"></a>Przypisywanie do pozycji w sprzedaży ciągłej
1. Przejdź do Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty.
2. Wybierz towar „0016”.
    * W tej procedurze wybierzesz numer towaru 0016. Normalnie tworzy się zwolniony produkt, który ma stosowaną dodatkową logikę biznesową ciągłości, gdy jest umieszczany w zamówieniu sprzedaży w biurze obsługi.  
3. Na liście kliknij łącze w wybranym wierszu.
4. Kliknij przycisk Edytuj.
5. Rozwiń lub zwiń sekcję Sprzedaż.
6. W tym miejscu wprowadzisz program ciągłości sprzedaży, który reprezentuje ten towar. Wpisz utworzony wcześniej identyfikator harmonogramu.
    * Gdy ten towar jest sprzedawany przez biuro obsługi, jest do niego stosowana dodatkowa logika biznesowa z wybranego programu sprzedaży ciągłej.  
7. Kliknij przycisk Zapisz.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]