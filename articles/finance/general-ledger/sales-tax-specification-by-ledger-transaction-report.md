---
title: Specyfikacja podatku wg transakcji księgi raport
description: W tym temacie objaśniono sposób używania raportu Specyfikacja podatku przez Raport transakcji księgi do wyświetlania i drukowania informacji o transakcjach księgi, dla których jest obliczany podatek
author: ericwang
manager: Ann Beebe
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-19
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: e2aafa90b8dbc6642737fc1834a7c992a9883033
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4975515"
---
# <a name="sales-tax-specification-by-ledger-transaction-report"></a>Specyfikacja podatku wg transakcji księgi raport
[!include [banner](../includes/banner.md)]

W tym temacie objaśniono sposób używania raportu **Specyfikacja podatku przez transakcje księgi** do wyświetlania i drukowania informacji o transakcjach księgi, dla których jest obliczany podatek

## <a name="tax-accounts-vs-non-tax-accounts"></a>Konta podatkowe a konta niepodatkowe

W raporcie **Specyfikacja podatku wg transakcji księgi** są wyświetlane transakcje podatkowe dla kont podatkowych i kont innych niż podatki. Te konta są klasyfikowane w następujący sposób:

- **Konto podatkowe** — konto jest traktowane jako konto podatkowe podczas księgowania transakcji podatkowej, a konto główne w wierszu arkusza **podatkowego** jest kontem podatkowym, takim jak konto podatku należnego lub konto podatku należnego
- **Konto niepodatkowe** — konto jest traktowane jako konto niepodatkowe podczas księgowania transakcji podatkowej, a konto główne w wierszu arkusza podatkowego jest kontem niepodatkowym, takim jak konto przychodu lub konto wydatków.

Dla kont podatku, kolumny **pochodzenie**, **podatek należny** i **podatek naliczony** w raporcie są wyświetlane **0** (zero) W przypadku kont niepodatkowych kolumny te zawierają kwoty.

## <a name="filtering-the-data-on-the-report"></a>filtrowane dane wyświetlane w raporcie,

Podczas generowania tego raportu, wyświetlane są następujące pola domyślne. Możesz używać tych pól filtrowania danych, które będą wyświetlane w raporcie.

| Pole                      | Opis |
|----------------------------|-------------|
| Data                       | Pola w sekcji **od** i **do** służą do definiowania zakresu dat dla transakcji podatkowych. |
| Konto główne               | Pola w sekcji **od** i **do** służą do definiowania zakresu dat dla kont głównych. |
| Kod podatku             | Pola w sekcji **od** i **do** służą do definiowania zakresu dat dla kodów podatków. |
| Grupowanie                   | Umożliwia określenie, czy raport powinien być pogrupowany według kont księgowych czy kodów podatków. |
| Suma częściowa wg kodu podatku | Ustawienie tej opcji na **tak** powoduje wyświetlanie sum częściowych według kodu podatku. |
| Tylko sumy                | Tę opcję należy wybrać **tak**, aby były wyświetlane tylko sumy całkowite. |
| Tylko konta główne         | Ustawienie tej opcji na **tak** powoduje uwzględnienie tylko kont głównych w raporcie. |

## <a name="showing-only-non-tax-accounts-on-the-report"></a>Wyświetlanie w raporcie tylko kont niepodlegających opodatkowaniu

Aby w raporcie były wyświetlane tylko konta niepodatkowe, należy skonfigurować warunek filtru, taki jak gwiazdka (\*), co pokazano na poniższej ilustracji.

![Raport przedstawiający konta niepodatkowe](media/taxspecperledgertrans.png)
