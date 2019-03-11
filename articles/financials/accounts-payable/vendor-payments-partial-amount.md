---
title: Częściowa płatność dostawcy
description: Czasami płatność dokonywana na rzecz dostawcy jest mniejsza od kwoty faktury. W tym artykule opisano różne opcje postępowania w takiej sytuacji.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14321
ms.assetid: 9a17075e-5325-4d55-a1e5-1791b8c460a0
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2644e0a27eff3e45ddcddb89c9aac9230190788f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "318909"
---
# <a name="vendor-payments-for-a-partial-amount"></a>Częściowe płatności dla dostawcy

[!include [banner](../includes/banner.md)]

Czasami płatność dokonywana na rzecz dostawcy jest mniejsza od kwoty faktury. W tym artykule opisano różne opcje postępowania w takiej sytuacji. Faktycznie dostępne opcje zależą od konkretnych wymagań biznesowych i istniejącej konfiguracji. 

<a name="cash-discount-amounts"></a>Kwoty rabatu gotówkowego
---------------------

Dostawca może zaoferować Ci rabat za rozliczenie faktury przed datą należności. Załóżmy, że wprowadzasz fakturę na kwotę 100,00, na którą odbiorca może uzyskać 2-procentowy rabat gotówkowy, jeśli zapłaci ją w ciągu 10 dni. Okres płatności wynosi 30 dni. Jeśli propozycja płatności rabatu gotówkowego używa jako kryterium wyboru faktury i jeśli propozycja zostanie uruchomiona w dniu lub przed datą rabatu gotówkowego, wybrana faktura do zapłaty i płatność są tworzone na kwotę 98,00. Rabat gotówkowy może być również uwzględniony dla jednorazowej płatności, która została utworzona ręcznie.

## <a name="partial-payments-with-cash-discounts"></a>Płatności częściowe z rabatem gotówkowym
Kiedy dokonujesz płatności częściowej, możesz zaplanować dokonanie dodatkowej zapłaty częściowej, by rozliczyć fakturę w całości. Aby podjąć rabat gotówkowy dla płatności częściowej, musisz ustawić w opcji **Oblicz rabaty gotówkowe dla częściowych zapłat** wartość **Tak** na stronie **Parametry modułu rozrachunków z odbiorcami**. 

Na przykład możesz otrzymać 2-procentowy rabat gotówkowy, jeśli faktura zostanie zapłacona w ciągu 10 dni po wystawieniu. Faktura jest księgowana na wartość 100,00. Jeśli w ciągu 10 dni dokonasz płatności w wysokości 49,00, wpisujesz debet w wysokości 49,00 w arkuszu płatności. Po rozliczeniu płatności częściowej na stronie **Rozliczanie otwartych transakcji** w polu **Kwota rabatu gotówkowego do pobrania** pojawia się wartość **1,00**. 

> [!NOTE] 
> Jeśli wpiszesz częściową płatność i zostawisz pełną wartość faktury w polu **Kwota do rozliczenia**, pole **Kwota rabatu gotówkowego do pobrania** jest automatycznie obliczane ponownie po zaksięgowaniu transakcji.

## <a name="credit-notes-with-cash-discounts"></a>Faktury korygujące z rabatami gotówkowymi
Możesz zwrócić część towarów znajdujących się na fakturze i otrzymać fakturę korygującą. Jeśli dla oryginalnej faktury został podjęty rabat gotówkowy, możesz odjąć wartość rabatu i uzyskać zwrot kosztu na odpowiednią kwotę. Jeśli opcja **Oblicz rabaty gotówkowe dla faktur korygujących**na stronie **Parametry modułu rozrachunków z dostawcami** ma wartość **Tak**, rabat dla faktury korygującej jest automatycznie obliczany. 

Na przykład możesz otrzymać 2-procentowy rabat gotówkowy, jeśli faktura zostanie zapłacona w ciągu 10 dni po wystawieniu. Faktura jest księgowana na wartość 100,00. W przypadku zwrotu towarów i otrzymania faktury korygującej możesz wprowadzić fakturę korygującą dla całej kwoty oryginalnej faktury (100,00) łącznie z 2-procentowym rabatem gotówkowy zdefiniowanym na fakturze korygującej.  Podczas wyświetlania faktury korygującej na stronie **Rozliczanie transakcji** w polu **Kwota do rozliczenia** pojawia się wartość **98,00**, a w polu **Kwota rabaty gotówkowego** pojawia się wartość **-2,00**. Kwota rabatu jest księgowana na koncie rabatu gotówkowego.

## <a name="overpaymentunderpayment-amounts"></a>Kwoty nadpłaty/niedopłaty
Możesz dokonać częściowej płatności, jeśli kwota pozostała do zapłacenia, jest bardzo mała. Na przykład faktura od dostawcy ma wartość 1000,00 i płacisz kwotę 999,90. Jeśli pozostała kwota jest mniejsza od kwoty określonej dla nadpłaty i niedopłaty w na stronie **Parametry modułu rozrachunków z dostawcami**, różnica jest automatycznie księgowana na koncie księgi niedopłaty/nadpłaty.


Aby uzyskać więcej informacji, zobacz [Przegląd płatności dla dostawcy](../cash-bank-management/tasks/vendor-payment-overview.md).
