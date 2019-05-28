---
title: Tworzenie nowej umowy handlowej
description: Ta procedura przedstawia sposób tworzenia umowy handlowej, w której jest rejestrowana nowa ceny sprzedaży produktu uzgodniona z określonym odbiorcą.
author: omulvad
manager: AnnBe
ms.date: 11/16/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e132cd20437b7929e81fcaa123d70bb57fb320c8
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1549274"
---
# <a name="create-a-new-trade-agreement"></a>Tworzenie nowej umowy handlowej

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura przedstawia sposób tworzenia umowy handlowej, w której jest rejestrowana nowa ceny sprzedaży produktu uzgodniona z określonym odbiorcą. Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych. Jeśli używasz własnych danych, przed rozpoczęciem czynności z tego przewodnika upewnij się, że istnieje arkusz umów handlowych, w którym relacja domyślna jest ustawiony na „Cena (sprzedaż)”.


## <a name="create-and-post-a-new-trade-agreement-journal"></a>Tworzenie i księgowanie nowego arkusza umów handlowych
1. Wybierz kolejno opcje Sprzedaż i marketing > Ceny i rabaty > Arkusze umów handlowych.
2. Kliknij przycisk Nowy.
3. W polu Nazwa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
4. Na liście znajdź i zaznacz odpowiedni rekord.
5. Na liście kliknij łącze w wybranym wierszu.
6. Kliknij przycisk Wiersze.
7. W polu Kod konta wybierz opcję „Tabela”.
    * W tym przykładzie zaktualizujesz cenę dla określonego odbiorcy, co oznacza, że musisz wybrać opcję Tabela. Cena byłaby aktualizowana cena katalogowa produktu, należałoby zaznaczyć opcję Wszystko, tak aby nowa cena obowiązywała dla wszystkich odbiorców. Zostały ceny byłyby różnicowane między segmentami odbiorców, należałoby wybrać opcję Grupa. Aby można było zaznaczyć opcję Grupa, muszą być skonfigurowane grupy cenowe dla odbiorców.  
8. W polu Wybór konta kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
9. Na liście znajdź i zaznacz odpowiedni rekord.
10. W polu Kod towaru wybierz opcję „Tabela”.
    * Podczas wprowadzania umowy handlowej typu „Cena (sprzedaż)” można w polu Kod towaru zaznaczyć tylko opcję „Tabela”. Jest tak, ponieważ cena jest wartością bezwzględną i nie może być taka sama dla wszystkich produktów lub grupy produktów.  
11. W polu Relacja towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
12. Na liście zaznacz produkt, który chcesz umieścić w umowie.
    * Odnotuj, który produkt został wybrany.  
13. Na liście kliknij łącze w wybranym wierszu.
14. W polu Od wprowadź ilość minimalną.
    * Jeśli odbiorca musi zamówić minimalną ilość, aby uzyskać nową cenę, trzeba w tym miejscu określić tę ilość.  
    * Wprowadź wartość w polu Do, aby określić maksymalną ilość, powyżej której cena umowy nie będzie obowiązywać. Jeśli oferujesz ceny i rabaty oparte na wielu przedziałach ilości, określ każdy przedział ilości za pomocą pary ilości minimalnej i maksymalnej odpowiednio w polach „Od” i „Do”.  
15. W polu Kwota w walucie wpisz cenę.
16. W polu Od dnia wprowadź datę, od kiedy umowa będzie obowiązywać.
17. Kliknij przycisk Zapisz.
18. Kliknij przycisk Sprawdź poprawność.
19. Kliknij przycisk Zweryfikuj zaznaczone wiersze.
20. Kliknij przycisk OK.
21. Kliknij przycisk Księguj.
22. Kliknij przycisk OK.

## <a name="view-trade-agreements-for-a-product"></a>Wyświetlanie umów handlowych na produkt
1. Przejdź do Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty.
2. Na liście znajdź i zaznacz produkt, którego cena została właśnie zaktualizowana.
3. W okienku akcji kliknij pozycję Sprzedaż.
4. Kliknij opcję Wyświetl umowy handlowe.
    * Przejrzyj szczegóły utworzonej właśnie umowy handlowej dotyczącej cen.    
5. Zamknij stronę.

## <a name="additional-resources"></a>Dodatkowe zasoby
### <a name="community-blogs"></a>Blogi społeczności
- [Ceny sprzedaży w Dynamics 365 for Finance and Operations](https://financefunction.tech/2018/11/14/sales-prices-in-dynamics-365-for-finance-and-operations/#sales_price_in_trade_agreements)
