---
title: "Księgowanie za pomocą ksiąg pochodnych"
description: "W tym artykule opisano sposób korzystania z ksiąg pochodnych."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3421
ms.assetid: f5187c21-eec5-4148-b178-b8a5feff7f23
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3b16ef53f9fb57a6663db0be1f7e0a57471db2fb
ms.openlocfilehash: ca077727910059878fb16a3f78c5b9133c6c741f
ms.lasthandoff: 03/31/2017


---

# <a name="post-with-derived-books"></a>Księgowanie za pomocą ksiąg pochodnych

[!include[banner](../includes/banner.md)]


W tym artykule opisano sposób korzystania z ksiąg pochodnych.

W przypadku księgowania transakcji w księdze, która zawiera księgi pochodne, transakcje w księgach pochodnych są księgowane automatycznie z arkuszy, zamówień zakupu i faktur niezależnych. Jeżeli jednak przygotowujesz transakcje dla księgi podstawowej w arkuszu Środki trwałe, możliwe będzie wyświetlanie i modyfikowanie kwot transakcji pochodnych przed ich zaksięgowaniem.
-   Pewne konta, takie jak konto podatkowe, konto odbiorcy lub konto dostawcy, są aktualizowane tylko raz poprzez księgowanie w księdze podstawowej. Transakcje księgi pochodnej są księgowane na kontach zdefiniowanych dla księgi pochodnej na stronie Profile księgowania środków trwałych.
-   Dla ksiąg pochodnych jako typ transakcji jest zwykle używana opcja Nabycie. Z tej opcji można korzystać, jeżeli księga i księga pochodna mają być stosowane dla środków trwałych od momentu ich nabycia.
-   Możliwe jest także stosowanie innych wartości dla opcji typu transakcji. Na przykład jeżeli w księgach podstawowej i pochodnych są te same okresy dotyczące sprzedaży lub likwidacji, wszystkie typy transakcji na środkach trwałych są dostępne podczas konfigurowania księgi pochodnej.

> [!WARNING]
> Amortyzacja zaksięgowana w księdze pochodnej będzie na tę samą kwotą, co kwota zaksięgowana w księdze podstawowej. Jeżeli metody amortyzacji są różne w obu rodzajach ksiąg, nie należy generować transakcji amortyzacji za pomocą procesu ksiąg pochodnych. |

## <a name="example"></a>Przykład 
Na podstawie poniższych informacji prześledźmy sposób konfigurowania transakcji nabycia przy użyciu funkcji ksiąg pochodnych.

1.  Utwórz księgi na stronie Księgi.
    -   Księga do celów księgowych: VM 1, warstwa księgowania Bieżący
    -   Księga do celów podatkowych: VM 2, warstwa księgowania Podatek

2.  W księdze VM 1 kliknij kartę Księgi pochodne. Wybierz wartość VM 2 w polu Księga i wartość Nabycie w polu Typ transakcji.

Księgi można dołączać do określonych środków trwałych. 

Jeżeli nabycie środka trwałego zostanie zaksięgowane w księdze VM 1, nie zostanie zaksięgowane tylko w księdze VM 1, ale również w księdze pochodnej VM 2. Stan obu ksiąg środków trwałych zmieni się na Otwarty.

> [!NOTE]                                                                                                         
> Jeżeli nie jest używana funkcja ksiąg pochodnych, należy zaksięgować nabycie środka trwałego osobno w księgach VM 1 i VM 2.

Aby uzyskać więcej informacji, zobacz [Księgi pochodne](derived-books.md)




