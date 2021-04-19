---
title: Wyszukiwanie odpowiednich cen i rabatów
description: W tej procedurze pokazano sposób wyszukiwania ceny i/lub rabatu na produkt, który jest aktualnie dostępny dla określonego odbiorcy, bez tworzenia zamówienia sprzedaży.
author: omulvad
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 50d7cf7b765c27db5aa9ea50c8593132c68c850a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5824853"
---
# <a name="look-up-applicable-prices-and-discounts"></a>Wyszukiwanie odpowiednich cen i rabatów

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano sposób wyszukiwania ceny i/lub rabatu na produkt, który jest aktualnie dostępny dla określonego odbiorcy, bez tworzenia zamówienia sprzedaży. Procedura prowadzi przez konkretny przykład. W celu wybierania niezbędnych wartości należy wykonać przykład z użyciem danych firmy demonstracyjnej USMF.


## <a name="find-the-applicable-price"></a>Wyszukiwanie odpowiedniej ceny
1. Wybierz kolejno opcje Sprzedaż i marketing > Ceny i rabaty > Znajdź ceny.
2. W polu Konto odbiorcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
3. Na liście znajdź i zaznacz odbiorcę US-001.
4. Na liście kliknij łącze w wybranym wierszu.
5. W polu Numer pozycji wpisz „T0004”.
    * Domyślnie w polu Ilość jest ustawiona wartość 1. Jednak jeśli jest znany rozmiar zamówienia, jakie odbiorca zamierza złożyć na dany produkt, wprowadź tę wartość. Ta informacja jest istotna, jeśli umowy handlowe z odbiorcą zawierają przedziały ilości, tzn. cena produktu zależy od zakupionej ilości minimalnej.  
6. W polu Data wprowadź datę, kiedy odbiorca zamierza złożyć zamówienie. 
    * Data może być datą dzisiejszą lub dowolnym dniem w przyszłości.  
    * Teraz system zwróci cenę, która jest prawidłowa dla wybranego produktu podczas kupowania przez wybranego odbiorcę w wybranym dniu w określonej ilości. W tym przykładzie jeśli US-001 odbiorca kupi 1 jednostkę produktu T0004 dzisiaj, zostanie obciążony kwotą 350 CAD. Ta cena pochodzi z istniejącej i aktywnej umowy handlowej z odbiorcą.      Inne pola na stronie zawierają szczegółowe informacje o cenie produktu i koszcie produktu (jeżeli je skonfigurowano w produkcie głównym) oraz obliczoną rentowność.  
    * Jeśli jest zaznaczona Pokaż pokrewne warianty produktu, oznacza to, że istnieją dodatkowe umowy handlowe na warianty produktu.  
7. Zaznacz pole wyboru Pokaż pokrewne warianty produktu.
    * Jest wyświetlana lista wariantów produktu wraz z informacjami o ich wymiarach.  
8. Na liście zaznacz wiersz reprezentujący kolor biały.
    * Należy zauważyć, że cena produktu jest teraz inna niż wyświetlana poprzednio, gdy nie była określona dla wymiaru.  
9. Kliknij przycisk Wyświetl ceny sprzedaży.
    * Na stronie Cena (sprzedaż) są wyświetlane wszystkie umowy handlowe mające zastosowanie do produktu, w tym jego wariantów.  
10. Zamknij stronę.

## <a name="find-the-applicable-discount"></a>Wyszukiwanie odpowiedniego rabatu
Upewnij się, że pole Konto odbiorcy zawiera numer odbiorcy US-001.    
1. W polu Numer pozycji wpisz „T0012”.
    * Upewnij się, że pole Ilość zawiera wartość 1.  
    * Poniższe szczegóły cen wyświetlane dla produktu T0012 pochodzą z jednej lub kilku umów handlowych: cena jednostkowa wynosi 1000 CAD, a procent rabatu wynosi 5.  
2. W polu Ilość wpisz wartość 20.
    * Zwiększona ilość w zamówieniu powoduje, że rabat wiersza, który będzie oferowany odbiorcy, zmienia się z 5 na 7 procent.  
    * Kwota netto jest obliczana automatycznie na podstawie ceny jednostkowej, rabatu i ilości całkowitej.  
3. Kliknij opcję Wyświetl rabat wiersza.
    * Istnieją dwie umowy rabatu wiersza na produkt T0012, określając 5 procent rabatu za ilość wiersza zamówienia od 1 do 10 oraz 7 procent rabatu dla ilości w zamówieniu powyżej 10. Należy zwrócić uwagę, że rabaty są stosowane do grupy produktów, w tym przykładzie grupy o kodzie 01, do której należy produkt T0012.  
4. Zamknij stronę.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]