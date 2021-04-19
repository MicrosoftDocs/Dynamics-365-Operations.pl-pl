---
title: Tworzenie nowej umowy handlowej
description: Ta procedura przedstawia sposób tworzenia umowy handlowej, w której jest rejestrowana nowa ceny sprzedaży produktu uzgodniona z określonym odbiorcą.
author: omulvad
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TradeNonStockedConversion, TradeNonStockedConversionChangeWizard, TradeNonStockedConversionCheckWorksheet, TradeNonStockedConversionWizard, TradeNonStockedRegister
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ad1221bb57aea4c93cb60fc29caec2d3b41798f9
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836405"
---
# <a name="create-a-new-trade-agreement"></a>Tworzenie nowej umowy handlowej

[!include [banner](../../includes/banner.md)]

Ta procedura przedstawia sposób tworzenia umowy handlowej, w której jest rejestrowana nowa ceny sprzedaży produktu uzgodniona z określonym odbiorcą. Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych. Jeśli używasz własnych danych, przed rozpoczęciem czynności z tego przewodnika upewnij się, że istnieje arkusz umów handlowych, w którym relacja domyślna jest ustawiony na „Cena (sprzedaż)”.


## <a name="create-and-post-a-new-trade-agreement-journal"></a>Tworzenie i księgowanie nowego arkusza umów handlowych
1. Przejdź do **Okienko nawigacyji > Moduły > Sprzedaż i marketing > Ceny i rabaty > Czasopisma dotyczące umów handlowych**.
2. Kliknij przycisk **Nowy**.
3. W polu **Nazwa** kliknij rozwijany przycisk, aby otworzyć wyszukiwanie.
4. Na liście znajdź i zaznacz odpowiedni rekord.
5. W **okienku akcji** kliknij pozycję **Wiersze**.
6. W polu **Kod konta** wybierz „Tabela”.
    
    W tym przykładzie zaktualizujesz cenę dla określonego odbiorcy, co oznacza, że musisz wybrać opcję Tabela. Jeśli aktualizujesz cenę katalogową produktów, wybierz „Wszystko”, aby nowa cena została zmieniona dla wszystkich klientów. Zostały ceny byłyby różnicowane między segmentami odbiorców, należałoby wybrać opcję Grupa. Aby można było zaznaczyć opcję Grupa, muszą być skonfigurowane grupy cenowe dla odbiorców.  

7. W polu **Wybór konta** kliknij rozwijany przycisk, aby otworzyć wyszukiwanie.
8. Na liście znajdź i zaznacz odpowiedni rekord.
9. W polu **Kod przedmiotu** wybierz „Tabela”.
    
    Podczas zawierania umowy handlowej typu „Cena (sprzedaż)” należy wybrać tylko „Tabela” w polu **Kod przedmiotu**. Jest tak, ponieważ cena jest wartością bezwzględną i nie może być taka sama dla wszystkich produktów lub grupy produktów.
    
10. W polu **Powiązanie produktu** kliknij rozwijany przycisk, aby otworzyć wyszukiwanie.
11. Na liście zaznacz produkt, który chcesz umieścić w umowie. Odnotuj, który produkt został wybrany.  
12. W polu **Od** wpisz minimalną ilość.
    - Jeśli odbiorca musi zamówić minimalną ilość, aby uzyskać nową cenę, trzeba w tym miejscu określić tę ilość.  
    - Wpisz wartość w polu **Do**, żeby ustalić maksymalną ilość powyżej której cena zawarta w umowie nie będzie obowiązywała. Jeśli oferujesz ceny i rabaty na podstawie wielokrotnych podziałów ilościowych, określ każdy przedział ilościowy jako parę minimalnej i maksymalnej ilości odpowiednio w polach **Od** i **Do**.
13. W polu **Ilość w walucie** wprowadź cenę.
14. W sekcji **Szczegóły** w polu **Od daty** wpisz datę, od której ta umowa będzie ważna.
15. Kliknij przycisk **Zapisz**.
16. Kliknij **Potwierdź**.
17. Kliknij **Potwierdź wybrane linie**.
18. Kliknij przycisk **OK**.
19. Kliknij przycisk **Księguj**.
20. Kliknij przycisk **OK**.

## <a name="view-trade-agreements-for-a-product"></a>Wyświetlanie umów handlowych na produkt
1. Otwórz **Okienko nawigacji > Moduły > Informacje o zarządzaniu produktem > Produkty > Wydane produkty**.
2. Na liście znajdź i zaznacz produkt, którego cena została właśnie zaktualizowana.
3. W **Panelu akcji** kliknij **Sprzedaj**.
4. Kliknij **Zobacz umowy handlowe**.
    
    Przejrzyj szczegóły utworzonej właśnie umowy handlowej dotyczącej cen.    

5. Zamknij stronę.

## <a name="additional-resources"></a>Dodatkowe zasoby

### <a name="whitepaper"></a>Oficjalny dokument
Aby uzyskać więcej informacji, pobierz następujący oficjalny dokument (napisany w celu obsługi systemu AX2012, ale nadal dotyczy aplikacji Dynamics 365 Supply Chain Management)
- [Umowy handlowe](https://mbs.microsoft.com/files/public/CS/AX2012R3/TradeagreementsinAX.pdf)

### <a name="community-blogs"></a>Blogi społeczności
- [Ceny sprzedaży w Dynamics 365 for Finance and Operations](https://financefunction.tech/2018/11/14/sales-prices-in-dynamics-365-for-finance-and-operations/#sales_price_in_trade_agreements)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]