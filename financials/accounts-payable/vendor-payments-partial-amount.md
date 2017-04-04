---
title: "Częściowa płatność dostawcy"
description: "Czasami płatność dokonywana na rzecz dostawcy jest mniejsza od kwoty faktury. W tym artykule opisano różne opcje postępowania w takiej sytuacji. Faktycznie dostępne opcje zależą od konkretnych wymagań biznesowych i istniejącej konfiguracji."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14321
ms.assetid: 9a17075e-5325-4d55-a1e5-1791b8c460a0
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 2cb439e871d57f74c296697cfc42705fb0121bb7
ms.openlocfilehash: 4d243e6a9a68b69a6b32748344fc606ff3f2d965
ms.lasthandoff: 03/31/2017


---

# <a name="vendor-payments-for-a-partial-amount"></a>Częściowa płatność dostawcy

Czasami płatność dokonywana na rzecz dostawcy jest mniejsza od kwoty faktury. W tym artykule opisano różne opcje postępowania w takiej sytuacji. Faktycznie dostępne opcje zależą od konkretnych wymagań biznesowych i istniejącej konfiguracji. 

<a name="cash-discount-amounts"></a>Kwoty rabatu gotówkowego
---------------------

Dostawca może zaoferować Ci rabat za rozliczenie faktury przed datą należności. Załóżmy, że wprowadzasz fakturę na kwotę 100,00, na którą odbiorca może uzyskać 2-procentowy rabat gotówkowy, jeśli zapłaci ją w ciągu 10 dni. Okres płatności wynosi 30 dni. Jeśli propozycja płatności używa rabatu gotówkowego jako kryterium doboru faktury i propozycji jest uruchamiana na lub przed datą rabatu gotówkowego, faktura jest zaznaczona do zapłaty i płatność jest tworzony 98,00. Rabat gotówkowy może być również uwzględniony jednorazowej płatności, który został utworzony ręcznie.

## <a name="partial-payments-with-cash-discounts"></a>Płatności częściowe z rabatem gotówkowym
Kiedy dokonujesz płatności częściowej, możesz zaplanować dokonanie dodatkowej zapłaty częściowej, by rozliczyć fakturę w całości. Podjęcie rabatu gotówkowego dla płatności częściowej należy ustawić ** Oblicz rabaty gotówkowe dla częściowych zapłat ** opcji w celu **tak** na **parametry płatne konta** strony. 

Na przykład możesz otrzymać 2-procentowy rabat gotówkowy, jeśli faktura zostanie zapłacona w ciągu 10 dni po wystawieniu. Faktura jest księgowana na wartość 100,00. Jeśli dokonasz płatności o 49.00 w ciągu 10 dni, należy wprowadzić Debet 49.00 w dzienniku płatności. Kiedy rozliczyć płatność częściowa na **Rozlicz otwarte transakcje** strony, **1.00** pojawia się w **kwota rabatu gotówkowego do pobrania** pole. 

> [!NOTE] 
> Jeśli wprowadzona płatności częściowej, a pozostawić pełną kwotę faktury w **kwota do rozliczenia** pole, **kwota rabatu gotówkowego do pobrania** pola jest obliczana automatycznie podczas księgowania transakcji.

## <a name="credit-notes-with-cash-discounts"></a>Faktury korygujące z rabatami gotówkowymi
Możesz zwrócić część towarów znajdujących się na fakturze i otrzymać fakturę korygującą. Jeśli dla oryginalnej faktury został podjęty rabat gotówkowy, możesz odjąć wartość rabatu i uzyskać zwrot kosztu na odpowiednią kwotę. Jeśli ** Oblicz rabaty gotówkowe dla faktur korygujących ** opcja jest ustawiona na **tak** na **Rozrachunki z dostawcami Parametry** stronę, rabat jest obliczany automatycznie dla faktury korygującej. 

Na przykład możesz otrzymać 2-procentowy rabat gotówkowy, jeśli faktura zostanie zapłacona w ciągu 10 dni po wystawieniu. Faktura jest księgowana na wartość 100,00. Jeśli zwrotu towaru i otrzymać fakturę korygującą, można wprowadzić faktury korygującej pełna kwota pierwotnej faktury 100,00, wraz z 2 procent rabatu gotówkowego, który również jest zdefiniowany w fakturze korygującej.  Podczas wyświetlania noty kredytowej na **rozliczenia transakcji** strony, **98.00** pojawia się w **kwota do rozliczenia** pole, i **-2.00** pojawia się w **kwota rabatu gotówkowego** pole. Kwota rabatu jest księgowana na koncie rabatu gotówkowego.

## <a name="overpaymentunderpayment-amounts"></a>Kwoty nadpłaty/niedopłaty
Możesz dokonać częściowej płatności, jeśli kwota pozostała do zapłacenia, jest bardzo mała. Na przykład faktura od dostawcy ma wartość 1000,00 i płacisz kwotę 999,90. Jeśli pozostała kwota jest mniejsza od kwoty określonej dla nadpłaty i niedopłaty w na stronie **Parametry modułu rozrachunków z dostawcami**, różnica jest automatycznie księgowana na koncie księgi niedopłaty/nadpłaty.


