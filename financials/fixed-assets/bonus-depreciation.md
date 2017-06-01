---
title: "Podwyższenie amortyzacji"
description: "Ten artykuł zawiera omówienie funkcji podwyższania amortyzacji."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBonus
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3621
ms.assetid: 835ec594-744e-461c-a676-1b9abc094173
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 414440332d313cfef72ce65ac3cd842d19390aad
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="bonus-depreciation"></a>Podwyższenie amortyzacji

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera omówienie funkcji podwyższania amortyzacji.

Podwyższenie amortyzacji umożliwia uzyskanie większych lub dodatkowych kwot amortyzacji w pierwszym roku użytkowania i amortyzacji środków. Podwyższenie amortyzacji należy wykonać przed wszelkimi innymi obliczeniami amortyzacji. Z tego względu najlepiej używać podwyższenia amortyzacji z księgami, w których wyłączono funkcję księgowania w księdze głównej. Można użyć opcji **Usuwanie transakcji, które nie zostały zaksięgowane w księdze głównej**, aby usunąć historyczne transakcje dla ksiąg, które nie powodują księgowania w księdze głównej. Następnie można uwzględnić podwyższenie amortyzacji na dalszych etapach cyklu życia środka trwałego poprzez usunięcie transakcji amortyzacji, które zostały wcześniej zaksięgowane. 

Podwyższenie amortyzacji można obliczyć za pomocą propozycji lub tworząc ręczne transakcje podwyższenia amortyzacji. Jeżeli w księdze środków trwałych istnieją transakcje podwyższenia lub transakcje korekty amortyzacji, nie można tworzyć transakcji podwyższenia amortyzacji.

Jeżeli do obliczenia podwyższenia amortyzacji jest stosowany proces propozycji, w obliczeniu podstawy zostaną uwzględnione wszystkie istniejące transakcje podwyższenia amortyzacji. Obliczenie uwzględni również wszystkie poprzednie podwyższenia amortyzacji wprowadzone ręcznie dla składnika aktywów. 

Jeżeli dla danego środka trwałego istnieje więcej niż jedno podwyższenie amortyzacji, jest uwzględniany priorytet. Każde podwyższenie zmniejsza podstawę amortyzacji dla kolejnego podwyższenia. Wartość odzyskana nie jest uwzględniana w podstawie składnika aktywów dla obliczeń podwyższenia amortyzacji, a konwencja amortyzacji nie jest stosowana do podwyższenia amortyzacji. 

Obecnie w Stanach Zjednoczonych niektóre środki trwałe podlegają amortyzacji wg rozdziału 179. Za pomocą potrącenia wg rozdziału 179 można przywrócić całość lub część kosztu niektórych środków do określonego limitu. Można odzyskać koszt, odliczając go w roku, w którym składnik został włączony do eksploatacji.

## <a name="example"></a>Przykład
Następujące podwyższenia amortyzacji są skojarzone z księgą środków trwałych:

-   **Rozdział 179:** 1000,00, priorytet 1
-   **Ulga podatkowa:** 30%, priorytet 2

Koszt nabycia składnika aktywów wynosi 5000,00. Po obliczeniu podwyższenia amortyzacji pierwsza kwota podwyższenia amortyzacji będzie wynosiła 1000,00 zgodnie z amortyzacją wg rozdziału 179. 

Kolejna kwota podwyższenia amortyzacji, zgodnie ze stawką amortyzacji po zastosowaniu ulgi, będzie obliczana w następujący sposób: 

Koszt nabycia – 1000 (amortyzacja wg rozdziału 179) x 30% = 1200 

Jeżeli kwota podwyższenia amortyzacji jest wyższa niż pozostały koszt nabycia, kwota podwyższenia amortyzacji będzie równa obliczonej wartości podwyższenia lub wartości pozostałego kosztu nabycia — w zależności od tego, która kwota jest niższa. 

Jeżeli pozostały koszt nabycia wynosi zero (0) lub mniej, transakcje podwyższenia amortyzacji nie zostaną wygenerowane. 

Jeżeli podwyższenie amortyzacji jest obliczane za pomocą propozycji, zostanie utworzona transakcja podwyższenia dla wszystkich rekordów podwyższenia skojarzonych z księgą środków trwałych. 

Można utworzyć nieograniczoną liczbę rekordów podwyższenia amortyzacji. Po przypisaniu tych rekordów do księgi grupy środków trwałych zostaną one zastosowane do księgi środków trwałych. 

Podwyższenie amortyzacji jest wprowadzane jako wartość procentowa lub jako kwota stała. Po zaksięgowaniu propozycji amortyzacji transakcje podwyższenia amortyzacji są księgowane w księdze jako osobne transakcje obok transakcji amortyzacji.




