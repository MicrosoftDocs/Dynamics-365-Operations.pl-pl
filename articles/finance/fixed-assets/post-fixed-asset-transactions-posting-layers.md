---
title: Księgowanie transakcji środków trwałych w warstwach księgowania
description: Ten artykuł zawiera omówienie funkcji warstwy księgowania dla transakcji na środkach trwałych.
author: moaamer
ms.date: 04/25/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: kfend
ms.custom: 3001
ms.assetid: 7dabde57-0843-47c3-85ef-f36b6f472e30
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e6361a3bef58bcc06ff01d0aada9ba309f283a83
ms.sourcegitcommit: 602a319f4720b39a56b7660b530236912d484391
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/06/2022
ms.locfileid: "8722360"
---
# <a name="post-fixed-asset-transactions-to-posting-layers"></a>Księgowanie transakcji środków trwałych w warstwach księgowania

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera omówienie funkcji warstwy księgowania dla transakcji na środkach trwałych.

Środek trwały jest często amortyzowany na różne sposoby w zależności od konkretnego celu. Amortyzacja do celów podatkowych jest obliczana na bieżących zasadach podatkowych w celu uzyskania najwyższej możliwej amortyzacji przed opodatkowaniem, natomiast amortyzacja do celów sprawozdawczych jest obliczana na podstawie zasad i norm księgowych. W warstwach księgowania obliczane i rejestrowane są różne rodzaje amortyzacji.

Każda księga dołączana do środka trwałego jest konfigurowany dla konkretnej warstwy księgowania mającej ogólne zamierzenie amortyzacji. Istnieje dziesięć warstw księgowania: Bieżący, Operacje, Podatek i 7 warstw niestandardowych. Można również wyłączyć księgowanie pozycji księgi w księdze głównej, ustawiając w polu Księguj w księdze głównej wartość Nie. Wtedy w polu Warstwa księgowania jest automatycznie ustawiana wartość Brak. Zazwyczaj księgi, które nie powodują księgowania w księdze głównej, są używane na potrzeby sprawozdawczości podatkowej. Zapewnia to dodatkową elastyczność umożliwiającą usuwanie historycznych transakcji z księgi środków trwałych, ponieważ nie zostały one potwierdzone w księdze głównej.

Arkusze środków trwałych są zdefiniowane na stronie Nazwy arkuszy (ścieżka Księga główna > Konfiguracja arkusza > Nazwy arkuszy). Każdy arkusz, w którym można zaksięgować amortyzację, zdefiniowany jest nazwą tylko dla jednej warstwy księgowania. Nie można zmienić warstwy księgowania w arkuszu. To ograniczenie pozwala zagwarantować, że transakcje dla każdej warstwy księgowania są przechowywane oddzielnie. Dla każdej warstwy księgowania konieczne jest utworzenie przynajmniej jednej nazwy arkusza. Jeśli używasz ksiąg, których zapisy nie są księgowanie w księdze głównej, trzeba również utworzyć arkusz z ustawioną warstwą księgowania Brak.

Na stronie Profile księgowania środków trwałych można wskazać konta księgowe dla transakcji na środkach trwałych. Dla każdego profilu księgowania należy wybrać właściwy typ transakcji i księgę, a następnie wskazać konta księgowe. Skonfiguruj rekord profilu księgowania dla każdej księgi, który będzie księgować w księdze głównej.

Środek trwały można wprowadzać w dokumentach obsługujących tylko warstwę księgowania **Bieżąca**, np. **Zamówienie zakupu**, **Oczekująca faktury od dostawcy**, **Zamówienie sprzedaży** lub **Faktura niezależna**. Wybranie identyfikatora środka trwałego w którymkolwiek z tych dokumentów powoduje wyfiltrowanie w księdze składników majątku księgi zawierającej warstwę księgowania **Bieżąca** oraz jej wypełnianie automatycznie podczas księgowania, gdy system zweryfikuje, że warstwą księgowania środków trwałych jest **Bieżąca**. Jeśli nie można ukończyć tej weryfikacji, proces księgowania zostanie zatrzymany. 

> [!NOTE] 
> Używając ksiąg pochodnych, można księgować transakcje jednocześnie w różnych warstwach księgowania. Transakcje księgi podstawowej tworzy się w arkuszu lub dokumencie źródłowym, którego warstwa księgowania odpowiada warstwie księgowania w księdze. Podczas księgowania transakcje księgi pochodnej będą księgowane w odpowiednich warstwach księgowania. 


Aby uzyskać więcej informacji, zobacz [Księgi pochodne](derived-books.md) i [Księgowanie z użyciem ksiąg pochodnych](post-derived-value-models.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
