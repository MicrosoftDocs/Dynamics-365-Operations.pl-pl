---
title: "Częściowa płatność odbiorcy"
description: "Czasami odbiorcy dokonują płatności na kwoty niższe niż kwota faktury. W tym artykule opisano różne opcje postępowania w takiej sytuacji. Faktycznie dostępne opcje zależą od konkretnych wymagań biznesowych i istniejącej konfiguracji."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13011
ms.assetid: 20423a2d-6997-4e1c-a596-a77016600071
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3b16ef53f9fb57a6663db0be1f7e0a57471db2fb
ms.openlocfilehash: 7025072cd29aac4ceb13b5594c3e321350777cf1
ms.lasthandoff: 03/31/2017


---

# <a name="customer-payments-for-a-partial-amount"></a>Częściowa płatność odbiorcy

Czasami odbiorcy dokonują płatności na kwoty niższe niż kwota faktury. W tym artykule opisano różne opcje postępowania w takiej sytuacji. Faktycznie dostępne opcje zależą od konkretnych wymagań biznesowych i istniejącej konfiguracji.

<a name="partial-payment-with-no-discount"></a>Płatność częściowa bez rabatu
--------------------------------

Odbiorca może dokonać częściowej płatności, ponieważ nie posiada wystarczających środków pieniężnych na rozliczenie faktury w całości lub istnieje spór dotyczący jakiejś pozycji na fakturze. W takiej sytuacji faktura może być rozliczona częściowo poprzez płatności. Faktura pozostanie otwarta i będzie na niej widoczne saldo.

## <a name="discount-amounts"></a>Kwoty rabatu
Można oferować odbiorcy rabat za rozliczenie faktury przed datą należności. Załóżmy, że wprowadzasz fakturę na kwotę 100,00, na którą odbiorca może uzyskać 2-procentowy rabat gotówkowy, jeśli zapłaci ją w ciągu 10 dni. Okres płatności wynosi 30 dni. Jeśli w ciągu 10 dni otrzymasz płatność w wysokości 98,00, wpisujesz płatność kwoty 98,00. Następnie gdy faktura zostanie oznaczona do rozliczenia, rabat gotówkowy jest pobierany automatycznie.

## <a name="partial-payments-with-cash-discounts"></a>Płatności częściowe z rabatem gotówkowym
Kiedy odbiorca dokonuje płatności częściowej, może zaplanować dokonanie dodatkowej zapłaty częściowej, by rozliczyć fakturę w całości. Aby wziąć rabatu gotówkowego dla płatności częściowej, należy ustawić ** Oblicz rabaty gotówkowe dla częściowych zapłat ** opcji w celu **tak** na **rozrachunków z odbiorcami Parametry** strony. 

Na przykład możesz zaoferować 2-procentowy rabat gotówkowy, jeśli faktura zostanie zapłacona w ciągu 10 dni po wystawieniu. Faktura jest księgowana na wartość 100,00. Jeśli w ciągu 10 dni otrzymasz płatność w wysokości 49,00, wpisujesz kredyt w wysokości 49,00 w arkuszu płatności. Po rozliczeniu płatności częściowej na stronie **Rozliczanie transakcji**, w polu **Kwota rabatu gotówkowego do pobrania** pojawia się wartość **1,00**. Kwota rabatu jest księgowana na koncie rabatu gotówkowego. 

> [!NOTE] 
> Jeśli wprowadzona płatności częściowej, a pozostawić pełną kwotę faktury w **kwota do rozliczenia** pole, **kwota rabatu gotówkowego do pobrania** pola jest obliczana automatycznie podczas księgowania transakcji.

## <a name="credit-notes-with-discounts"></a>Faktury korygujące z rabatami
Jeśli odbiorca zwróci część towarów znajdujących się na fakturze, możesz wystawić fakturę korygującą. Jeśli rabat gotówkowy został wykorzystany w przypadku oryginalnej faktury, faktura korygująca dla odbiorcy powinna być kwotą netto rabatu gotówkowego podjętego przez odbiorcę. Jeśli opcja **Oblicz rabaty gotówkowe dla faktur korygujących**na stronie **Parametry modułu rozrachunków z odbiorcami** ma wartość **Tak**, rabat dla faktury korygującej jest automatycznie obliczany. 

Na przykład możesz zaoferować warunki płatności z 2-procentowym rabatem gotówkowym, jeśli faktura zostanie zapłacona w ciągu 10 dni od wystawienia. Zaksięgowano fakturę dla 100,00, a odbiorca podjął rabat gotówkowy. Jeśli odbiorca zwraca towary i wystawiasz fakturę korygującą, można wprowadzić fakturę korygującą na kwotę -100,00. Podczas wyświetlania faktury korygującej na stronie **Rozliczanie otwartych transakcji** w polu **Kwota do rozliczenia** pojawia się wartość **98,00**, a w polu **Kwota rabaty gotówkowego** pojawia się wartość **-2,00**. Kwota rabatu jest księgowana na koncie rabatu gotówkowego.

## <a name="overpaymentunderpayment-amounts"></a>Kwoty nadpłaty/niedopłaty
Jeśli odbiorca dokonuje płatności, może pojawić się bardzo mała kwota, która nadal wymaga rozliczenia. Na przykład gdy wystawisz odbiorcy fakturę na kwotę 1000,00, a on zapłaci 999.90. Jeśli pozostała kwota jest mniejsza od kwoty określonej dla nadpłaty i niedopłaty w na stronie **Parametry modułu rozrachunków z odbiorcami**, różnica jest automatycznie księgowana na koncie księgi niedopłaty/nadpłaty.

## <a name="full-settlement"></a>Pełne rozliczenie
Klienci mogą dokonać płatności częściowej gdzie nie będzie wypłacana kwota pozostała, ale jest większa niż kwota niedopłaty, która jest określona w **parametry płatne konta** strony. Jeśli chcesz oznaczyć jako w pełni rozliczonych faktury, można użyć **Pełne rozliczenie** opcji na **rozliczenia transakcji** strony. (Możesz włączyć funkcję pełnego rozliczania za pomocą klucza konfiguracji). Na przykład faktura jest księgowana na kwotę 1000,00, a odbiorca dokonuje płatności 990.00. Już uzgodnione, że dany klient nie posiada 10,00 pozostała zapłacić. Po oznaczeniu faktury do rozliczenia, można również oznaczyć select **Pełne rozliczenie**. Faktura zostanie następnie uznana za w pełni rozliczoną. Różnica w wysokości 10,00 jest księgowana na koncie rabatu gotówkowego jako kwoty dodatkowa kwota rabatu gotówkowego.


