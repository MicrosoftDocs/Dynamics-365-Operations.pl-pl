--- 
title: Korekty ceny detalicznej
description: Ta procedura prowadzi przez proces tworzenia korekty ceny detalicznej.
author: josaw1
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: ab13aced30f90c4d7c8b96f30340fff6e3eee927
ms.contentlocale: pl-pl
ms.lasthandoff: 07/28/2017

---
# <a name="retail-price-adjustments"></a>Korekty ceny detalicznej

[!include[task guide banner](../includes/task-guide-banner.md)]

Ta procedura prowadzi przez proces tworzenia korekty ceny detalicznej. Korekta ceny sprzedaży detalicznej może ustawiać cenę sprzedaży bezpośrednio lub modyfikować jej bazową cenę sprzedaży albo cenę sprzedaży z umowy handlowej. Procedura wykorzystuje dane firmy demonstracyjnej USRT.

1. Kliknij opcję Zarządzanie cenami i rabatami.
2. Kliknij kartę Korekta ceny.
3. Kliknij przycisk Nowy.
    * W tym miejscu można tworzyć wszystkie najczęściej używane reguły cen i rabatów, w tym rabaty detaliczne, korekty cen, arkusze umów handlowych i reguły cen dla kategorii.  
4. Kliknij opcję Korekta ceny.
5. W polu Nazwa wpisz wartość.
6. Rozwiń sekcję Wiersze.
7. Kliknij przycisk Dodaj.
    * W tym przykładzie w polu Produkt wpisz „81126”.    Następnie w polu Procent rabatu wpisz „10,0”.  
    * Korekta ceny typu „procent rabatu” zmniejsza bazową cenę sprzedaży lub cenę sprzedaży z umowy handlowej.  
8. Kliknij przycisk Dodaj.
    * W tym przykładzie w polu Produkt wpisz „81125”.    Następnie w polu Metoda rabatowania wybierz opcję „Kwota rabatu gotówkowego”.    Na koniec w polu Kwota rabatu gotówkowego wpisz „5,0”.  
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


