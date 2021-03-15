---
title: Konfiguracje płatności dla zestawień sieci sprzedaży
description: Ta procedura pokazuje konfiguracje metod płatności dla sklepów komercyjnych, które mają wpływ na sposób tworzenia i księgowana zestawień.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b1fc042bff4d801ae893b0370b67cd8e11ba95f6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4982323"
---
# <a name="payment-configurations-for-retail-statements"></a>Konfiguracje płatności dla zestawień sieci sprzedaży

[!include [banner](../includes/banner.md)]

Ta procedura pokazuje konfiguracje metod płatności dla sklepów komercyjnych, które mają wpływ na sposób tworzenia i księgowana zestawień.

To nagranie wykorzystuje firmę demonstracyjną USRT.

1. Wybierz kolejno opcje Handel detaliczny i inny > Kanały > > Sklepy > Wszystkie sklepy.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. Na liście kliknij łącze w wybranym wierszu.
4. W okienku akcji kliknij pozycję Konfiguracja.
5. Kliknij opcję Metody płatności.
6. Rozwiń lub zwiń sekcję Księgowanie.
7. Kliknij przycisk Edytuj.
    * Określ, czy kwoty otrzymane przy tej metodzie płatności mają być księgowane na koncie księgowym czy koncie bankowym.  
    * Wybierz konto, na którym mają być księgowane kwoty otrzymane w tej metodzie płatności.  
    * Wybierz konto do księgowania ewentualnych różnic między kwotą łącznie otrzymaną z transakcji a kwotą obliczoną dla tej metody płatności.  
    * W tym polu można wpisać kwotę kontrolującą, kiedy kwota różnicy ma być księgowana na innym koncie rozbieżności. Można używać tego pola do śledzenia ponadnormatywnych różnic.  
    * Wybierz konto do księgowania ewentualnych różnic między kwotą łącznie otrzymaną z transakcji a kwotą obliczoną, jeśli przekracza ona wartość zdefiniowaną w polu „Maksymalna kwota różnicy”.  
    * Wybierz opcję „Tak”, aby księgować kwoty przekazywane do banku na oddzielnym koncie.  
    * W tym polu można określić, czy kwoty przekazywane do banku mają być księgowane na koncie księgowym czy koncie bankowym.  
    * Wybierz konto, na którym mają być księgowane kwoty przekazywane do banku.  
    * Wybierz typ transakcji bankowej, który będzie używany przy księgowaniu kwot przekazywanych do banku na konto bankowe.  
    * Wybierz opcję „Tak”, aby księgować kwoty przekazywane do sejfu na oddzielnym koncie.  
    * Określ, czy kwoty przekazywane do sejfu mają być księgowane na koncie księgowym czy koncie bankowym.  
    * Wybierz konto, na którym mają być księgowane kwoty przekazywane do sejfu.  
8. Kliknij przycisk Zapisz.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]