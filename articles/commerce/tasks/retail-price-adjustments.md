---
title: Korekty ceny detalicznej
description: Ta procedura prowadzi przez proces tworzenia korekty cen sprzedaży.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, RetailDiscountPricingWorkspace, RetailPeriodicDiscount, RetailDiscountPriceGroup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dbd2f818930424313e1d76aea4a257efa7c7b3be
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232792"
---
# <a name="retail-price-adjustments"></a>Korekty ceny detalicznej

[!include [banner](../includes/banner.md)]

Ta procedura prowadzi przez proces tworzenia korekty cen sprzedaży. Korekta ceny sprzedaży może ustawiać cenę sprzedaży bezpośrednio lub modyfikować jej bazową cenę sprzedaży albo cenę sprzedaży z umowy handlowej. Procedura wykorzystuje dane firmy demonstracyjnej USRT.

1. Kliknij opcję Zarządzanie cenami i rabatami.
2. Kliknij kartę Korekta ceny.
3. Kliknij przycisk Nowy.
    * W tym miejscu można tworzyć wszystkie najczęściej używane reguły cen i rabatów, w tym rabaty, korekty cen, arkusze umów handlowych i reguły cen dla kategorii.  
4. Kliknij opcję Korekta ceny.
5. W polu Nazwa wpisz wartość.
6. Rozwiń sekcję Wiersze.
7. Kliknij przycisk Dodaj.
    * W tym przykładzie w polu Produkt wpisz „81126”. Następnie w polu Procent rabatu wpisz „10,0”.  
    * Korekta ceny typu „procent rabatu” zmniejsza bazową cenę sprzedaży lub cenę sprzedaży z umowy handlowej.  
8. Kliknij przycisk Dodaj.
    * W tym przykładzie w polu Produkt wpisz „81125”. Następnie w polu Metoda rabatowania wybierz opcję „Kwota rabatu gotówkowego”.    Na koniec w polu Kwota rabatu gotówkowego wpisz „5,0”.  
    * Typ rabatu Kwota rabatu gotówkowego jest kwotą odjętą od ceny bazowej lub ceny w umowie handlowej.  
9. Kliknij opcję Grupy cenowe.
    * W polu Grupa cenowa wybierz opcję „RP-Houston”.  
    * Spowoduje to skojarzenie korekty ceny ze sklepem w Houston.  
10. Kliknij przycisk Zapisz.
11. Zamknij stronę.
12. W polu Stan wybierz wartość „Włączone”.
13. Kliknij przycisk Zapisz.
14. Zamknij stronę.
15. Odśwież stronę.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]