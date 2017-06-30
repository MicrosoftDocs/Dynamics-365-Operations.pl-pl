---
title: "Rabaty gotówkowe"
description: "Rabaty gotówkowe są skonfigurowane i udostępnione dla modułów Rozrachunki z odbiorcami i Rozrachunki z dostawcami.  Dostępny rabat gotówkowy można zdefiniować na fakturze dla odbiorcy lub fakturze od dostawcy. Zostanie on uwzględniony w przypadku zapłaty faktury w terminie obowiązywania rabatu gotówkowego."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CashDisc
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3741
ms.assetid: c25f9d85-2702-46aa-8e61-0b4886e069b3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 9d581a1d32a0df15e0b63e129d369d90aaa440d2
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="cash-discounts"></a>Rabaty gotówkowe

[!include[banner](../includes/banner.md)]


Rabaty gotówkowe są skonfigurowane i udostępnione dla modułów Rozrachunki z odbiorcami i Rozrachunki z dostawcami.  Dostępny rabat gotówkowy można zdefiniować na fakturze dla odbiorcy lub fakturze od dostawcy. Zostanie on uwzględniony w przypadku zapłaty faktury w terminie obowiązywania rabatu gotówkowego. 

<a name="cash-discounts"></a>Rabaty gotówkowe
--------------

Rabaty gotówkowe, które będą obowiązywały dla odbiorców lub dostawców można tworzyć na stronie Rabaty gotówkowe. Ponadto w polu Następny kod rabatu można zdefiniować serię rabatów gotówkowych następujących po sobie w zależności od terminu faktury. Aby uzyskać więcej informacji, zobacz „Przykład: Seria rabatów gotówkowych” dalej w tym temacie. Jeśli faktura i/lub transakcja kredytowa (płatność lub faktura korygująca) zostały wprowadzone w walucie innej niż waluta rozliczeniowa firmy, rabat gotówkowy jest obliczany według kursu wymiany, na podstawie daty płatności lub faktury korygującej. Jeśli faktura i dokument kredytowy zostały wprowadzone w innych firmach i jeśli waluty księgowania dla firm są różne, kurs wymiany jest brany z firmy na fakturze, począwszy od daty dokumentu faktury. Aby uzyskać więcej informacji, zobacz „Przykład: Kursy wymiany dla rabatów gotówkowych” dalej w tym temacie.
Kolejność domyślności dla rabatów gotówkowych na koncie głównym
----------------------------------------------

Jeśli faktura rozliczana jest w czasie, w którym można uzyskać rabat gotówkowy, rabat ten jest automatycznie księgowany na koncie głównym rabatów gotówkowych zgodnie z następującą kolejnością domyślności:
1.  Konto główne określone w polu Alternatywne konto rabatu gotówkowego na stronie Rozliczanie otwartych transakcji dla odbiorcy lub Rozliczanie otwartych transakcji dla dostawcy.
2.  Konto główne określone w polu Rabat gotówkowy odbiorcy lub w polu Rabat gotówkowy dostawcy grupy księgowania w księdze przypisanej do kodu podatków faktury. Ustaw grupy księgowania na stronie Grupy księgowania księgi i przypisz je do kodów podatku na stronie Kody podatków.
3.  Konto główne księgowania na stronie Rabaty gotówkowe w polu Konto główne rabatów odbiorcy lub Konto główne rabatów dostawcy dla kodu rabatu gotówkowego na rozliczonej fakturze.
4.  Konto główne rabatów gotówkowych według definicji na stronie Konta dla transakcji automatycznych.

## <a name="example-series-of-cash-discounts"></a> Przykład: Seria rabatów gotówkowych
Konfiguruj następujące trzy kody rabatów gotówkowych:
-   Kod 5D10% — 10% rabat gotówkowy przy zapłacie w ciągu 5 dni.
-   Kod 10D5% — 5% rabat gotówkowy przy zapłacie w ciągu 10 dni.
-   Kod 14D2% — 2% rabat gotówkowy przy zapłacie w ciągu 14 dni.

W polu Następny kod rabatu:
-   Dla kodu 5D10% wybierz opcję 10D5%.
-   Dla kodu 10D5% wybierz opcję 14D2%.
-   Dla kodu 14D2% pole Następny kod rabatu należy zostawić puste.

Te trzy rabaty gotówkowe następują po sobie w miarę wygasania poprzednich rabatów gotówkowych na fakturze. Tylko jeden rabat gotówkowy jest przyznawany w momencie zapłacenia faktury według dat ważności w sekwencji kolejnych rabatów gotówkowych.

## <a name="example-exchange-rates-for-cash-discounts"></a> Przykład: Kursy wymiany dla rabatów gotówkowych
Waluta rozliczeniowa firmy to EUR i obowiązuj następujący kurs wymiany do USD:
-   1 lutego = 110
-   1 marca = 80

15 lutego zostanie zaksięgowana faktura za 1000 USD z warunkami rabatu gotówkowego 20D2%. Kwota faktury w walucie rozliczeniowej wynosi 1100 EUR. Płatność na kwotę 980 USD jest rozliczana z fakturą w dniu 1 marca. Kwota rabatu gotówkowego wynosi 20 USD. Kwota płatności w walucie rozliczeniowej wynosi 784 EUR. Kwota rabatu gotówkowego w walucie rozliczeniowej jest obliczana przy użyciu kursu wymiany z dnia 1 marca: 20 \* 80 / 100 = 16 EUR.
| **Uwaga**                                                                                                                                                                                                                             |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Oblicz na stronach Parametry modułu rozrachunków z odbiorcami lub Parametry modułu rozrachunków z dostawcami wybrana jest opcja Oblicz rabaty gotówkowe dla częściowych zapłat, stosowany jest kurs wymiany z dnia dokonania płatności częściowej. |

 
=

 




